# Alcance MVP (MarketingPlanner)

## 10 pantallas objetivo (confirmadas en README)
1. **Login/Equipo**
2. **Dashboard**
3. **Calendario**
4. **Crear/editar pieza de contenido**
5. **Vista Kanban de contenidos**
6. **Campañas (lista + detalle)**
7. **Backlog de ideas**
8. **Tareas (por persona)**
9. **Biblioteca de assets**
10. **Ajustes (canales, estados, roles)**

## Casos de uso mínimos por pantalla
### 1) Login/Equipo
- Iniciar sesión con email/contraseña.
- Invitar usuario y asignar rol.
- Unirse a equipo existente.

### 2) Dashboard
- Ver próximos hitos y tareas bloqueadas.
- Ver contenidos en revisión.
- Ver KPIs rápidos (si hay datos conectados).

### 3) Calendario
- Crear pieza desde el calendario.
- Arrastrar y soltar para cambiar fecha/hora.
- Filtrar por canal y/o colección/tema.

### 4) Crear/editar pieza de contenido
- Crear pieza con canal, formato, objetivo y fecha/hora.
- Asignar responsable y aprobador.
- Subir/vincular assets y copy.
- Cambiar estado (Idea → Publicado).

### 5) Vista Kanban de contenidos
- Ver piezas por estado.
- Mover pieza entre columnas.
- Abrir detalle/editar pieza.

### 6) Campañas (lista + detalle)
- Crear campaña con fechas clave.
- Completar checklist por campaña.
- Consultar estado general y resultados básicos.

### 7) Backlog de ideas
- Registrar idea con tipo, prioridad y temporada.
- Adjuntar inspiración (link/referencia visual).
- Convertir idea en pieza.

### 8) Tareas (por persona)
- Crear tarea y asignar responsable.
- Marcar tarea como bloqueada o completada.
- Vincular tarea a campaña o pieza.

### 9) Biblioteca de assets
- Subir asset con tags.
- Marcar derechos de uso (ads/orgánico).
- Ver versiones disponibles.

### 10) Ajustes (canales, estados, roles)
- Administrar canales y formatos.
- Administrar estados y prioridades.
- Administrar roles y permisos.

## Entidades clave y campos mínimos
### Contenido (pieza)
- id
- título
- canal
- formato
- objetivo
- fecha_hora
- responsable_id
- aprobador_id
- estado
- prioridad
- assets[]
- copy
- etiquetas[]
- campaña_id (opcional)

### Campaña
- id
- nombre
- descripción
- fechas_clave[] (inicio/teaser/lanzamiento/cierre)
- checklist[]
- presupuesto (opcional)
- estado
- resultado (opcional)

### Tarea
- id
- título
- descripción
- responsable_id
- estado
- fecha_limite
- bloqueada (boolean)
- dependencia (texto simple)
- campaña_id (opcional)
- contenido_id (opcional)

### Asset
- id
- nombre
- tipo (imagen/video/documento)
- url
- tags[]
- derechos (ads/orgánico)
- versiones[]
- creado_por
- fecha_creación

### Usuario/Rol
- id
- nombre
- email
- rol (Admin/Marketing Lead/Creador/Operaciones/Viewer)
- equipo_id
- activo

### Canal
- id
- nombre (IG feed, reels, stories, TikTok, Email, Web, Ads)
- formatos[]
- activo

### Estado
- id
- nombre (Idea, Draft, Producción, Revisión, Aprobado, Programado, Publicado, Analizado, Archivado)
- tipo_entidad (contenido/tarea/campaña)
- orden

## Flujos críticos priorizados (Top 3)
1) **Crear contenido → aprobación → programar → publicado**
   - Crear pieza con responsable y aprobador.
   - Pasar a Revisión, aprobación, Programado y Publicado.
   - Validar assets y fecha/hora antes de programar.

2) **Crear campaña → checklist → seguimiento**
   - Crear campaña con fechas clave.
   - Completar checklist y visualizar pendientes.
   - Ver estado general y resultados básicos.

3) **Gestionar tareas por responsable**
   - Crear tareas vinculadas a campaña/pieza.
   - Asignar responsable y fecha límite.
   - Filtrar por persona y estado.

## Dependencias mínimas
- **Auth**: login con email/contraseña.
- **Roles**: control de acceso por rol (Admin/Lead/Creador/Operaciones/Viewer).
- **Calendario**: creación y reprogramación de piezas (drag & drop).

## Fuera de MVP (explícito)
- Integraciones avanzadas (Shopify, Ads, analítica avanzada).
- Automatizaciones completas (alertas múltiples, SLA complejo).
- Post-mortem/Aprendizajes detallado.
- Gestión de presupuestos y resultados avanzados de campañas.
- UGC tracker completo.
- Workflows multi-etapa con dependencias complejas.
