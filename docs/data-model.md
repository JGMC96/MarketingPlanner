# Esquema de datos

Este documento define el modelo lógico de datos para MarketingPlanner. Incluye entidades, relaciones, enums y reglas de validación clave.

## Tablas

### usuarios
- **id** (PK)
- **email** (único, requerido)
- **nombre**
- **rol** (enum `roles`)
- **estado** (activo/inactivo)
- **created_at**, **updated_at**

### equipos
- **id** (PK)
- **nombre** (único por organización)
- **descripcion**
- **created_at**, **updated_at**

### equipos_usuarios
- **id** (PK)
- **equipo_id** (FK → equipos.id)
- **usuario_id** (FK → usuarios.id)
- **rol_en_equipo** (enum `roles` o rol específico de equipo)
- **created_at**

### contenidos
- **id** (PK)
- **titulo**
- **tipo** (post, email, landing, anuncio, etc.)
- **estado_id** (FK → estados.id)
- **prioridad** (enum `prioridades`)
- **campaña_id** (FK → campañas.id, nullable)
- **equipo_id** (FK → equipos.id)
- **producto_id** (FK → productos.id, nullable)
- **owner_id** (FK → usuarios.id)
- **fecha_publicacion** (nullable)
- **utm_source**, **utm_medium**, **utm_campaign** (nullable)
- **created_at**, **updated_at**

### campañas
- **id** (PK)
- **nombre**
- **objetivo**
- **estado_id** (FK → estados.id)
- **equipo_id** (FK → equipos.id)
- **fecha_inicio**, **fecha_fin**
- **presupuesto**
- **created_at**, **updated_at**

### ideas
- **id** (PK)
- **titulo**
- **descripcion**
- **estado_id** (FK → estados.id)
- **prioridad** (enum `prioridades`)
- **equipo_id** (FK → equipos.id)
- **owner_id** (FK → usuarios.id)
- **campaña_id** (FK → campañas.id, nullable)
- **created_at**, **updated_at**

### tareas
- **id** (PK)
- **titulo**
- **descripcion**
- **estado_id** (FK → estados.id)
- **prioridad** (enum `prioridades`)
- **asignado_a** (FK → usuarios.id)
- **contenido_id** (FK → contenidos.id, nullable)
- **idea_id** (FK → ideas.id, nullable)
- **fecha_vencimiento**
- **created_at**, **updated_at**

### assets
- **id** (PK)
- **nombre**
- **tipo** (imagen, video, doc, link)
- **url**
- **contenido_id** (FK → contenidos.id, nullable)
- **idea_id** (FK → ideas.id, nullable)
- **producto_id** (FK → productos.id, nullable)
- **created_at**, **updated_at**

### estados
- **id** (PK)
- **nombre** (enum `estados`) 
- **tipo_entidad** (idea, contenido, campaña, tarea)
- **orden** (int, para flujos)

### etiquetas
- **id** (PK)
- **nombre** (único por equipo)
- **color**
- **equipo_id** (FK → equipos.id)

### etiquetas_rel
- **id** (PK)
- **etiqueta_id** (FK → etiquetas.id)
- **contenido_id** (FK → contenidos.id, nullable)
- **idea_id** (FK → ideas.id, nullable)
- **campaña_id** (FK → campañas.id, nullable)
- **tarea_id** (FK → tareas.id, nullable)

### aprobaciones
- **id** (PK)
- **entidad_tipo** (contenido, campaña, asset)
- **entidad_id** (FK polimórfica)
- **estado** (pendiente, aprobado, rechazado)
- **aprobador_id** (FK → usuarios.id)
- **comentarios**
- **created_at**, **updated_at**

### productos
- **id** (PK)
- **sku** (único)
- **shopify_id** (único)
- **nombre**
- **estado** (activo/inactivo)
- **precio**
- **created_at**, **updated_at**

## Relaciones clave
- **usuarios** ↔ **equipos**: N:M vía `equipos_usuarios`.
- **equipos** → **campañas**, **contenidos**, **ideas**, **etiquetas**: 1:N.
- **campañas** → **contenidos**, **ideas**: 1:N.
- **contenidos** → **tareas**, **assets**, **aprobaciones**: 1:N.
- **ideas** → **tareas**, **assets**: 1:N.
- **productos** → **contenidos** y **assets**: 1:N.
- **etiquetas** ↔ **contenidos/ideas/campañas/tareas**: N:M vía `etiquetas_rel`.

## Enums

### estados (flujo general)
1. **Idea**
2. **En revisión**
3. **Aprobado**
4. **En producción**
5. **Programado**
6. **Publicado**
7. **Archivado**

> Nota: `estados.tipo_entidad` puede restringir subconjuntos por entidad (p. ej., `tarea` usa *Idea*, *En producción*, *Archivado*).

### prioridades
- **Baja**
- **Media**
- **Alta**
- **Crítica**

### roles
- **Admin**
- **Marketing Lead**
- **Content Strategist**
- **Designer**
- **Copywriter**
- **Analyst**
- **Approver**
- **Viewer**

## Reglas de validación
- **Contenidos en estado Programado** requieren:
  - al menos **un asset** asociado, y
  - **UTM completos** (`utm_source`, `utm_medium`, `utm_campaign`).
- **Campañas** no pueden marcarse como **Programado/Publicado** si no tienen al menos **un contenido** asociado.
- **Aprobaciones**:
  - si `entidad_tipo = contenido`, se requiere **aprobación** antes de pasar a **Programado**.
  - si `entidad_tipo = asset`, se requiere aprobación para assets marcados como **finales** (si aplica flag en metadata).
- **Ideas** no pueden avanzar a **En producción** sin **owner_id** asignado.
- **Tareas** deben tener **asignado_a** y **fecha_vencimiento** para estados distintos de **Idea**.
- **Productos**: `sku` y `shopify_id` son obligatorios y únicos.
