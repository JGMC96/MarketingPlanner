# Mapa de rutas y wireframes textuales (10 pantallas)

## Mapa de rutas (visión general)
- **Login/Equipo**
  - Entrada al sistema, selección de equipo/organización.
  - Navega a **Dashboard** tras autenticación.
- **Dashboard**
  - Vista resumen con KPIs, próximos hitos y accesos rápidos.
  - Navega a **Calendario DnD**, **Kanban**, **Campañas**, **Backlog**, **Tareas**, **Biblioteca**, **Ajustes**.
- **Calendario DnD**
  - Planificación temporal con arrastrar y soltar piezas/campañas.
  - Navega a **Editor de pieza**, **Campañas**, **Backlog**.
- **Editor de pieza**
  - Edición de contenidos individuales (posts, anuncios, emails).
  - Navega a **Calendario DnD**, **Biblioteca**, **Tareas**.
- **Kanban**
  - Flujo de trabajo por estados (Idea → En progreso → Aprobación → Programado → Publicado).
  - Navega a **Editor de pieza**, **Tareas**, **Campañas**.
- **Campañas**
  - Vista y gestión de campañas con objetivos, presupuestos y piezas asociadas.
  - Navega a **Editor de pieza**, **Calendario DnD**, **Dashboard**.
- **Backlog**
  - Banco de ideas/piezas pendientes.
  - Navega a **Editor de pieza**, **Kanban**, **Calendario DnD**.
- **Tareas**
  - Lista de tareas, asignaciones y vencimientos.
  - Navega a **Editor de pieza**, **Kanban**, **Dashboard**.
- **Biblioteca**
  - Recursos multimedia y plantillas.
  - Navega a **Editor de pieza**, **Campañas**.
- **Ajustes**
  - Configuración de equipo, permisos, integraciones.
  - Navega a **Login/Equipo** (cambio de equipo) o **Dashboard**.

---

## Wireframes textuales por pantalla

### 1) Login/Equipo
**Objetivo**: Autenticar usuario y seleccionar equipo/organización.

**Estructura**
- Encabezado: logo + nombre producto.
- Columna izquierda: formulario de acceso.
- Columna derecha: mensajes de valor/beneficio (opcional).

**Campos**
- Email/usuario.
- Contraseña.
- Selector de equipo (lista o autocompletar) tras login.
- Recordarme (checkbox).

**Acciones**
- Iniciar sesión.
- Recuperar contraseña.
- Crear cuenta/solicitar acceso.
- Cambiar equipo (si el usuario pertenece a varios).

**Navegación**
- Al autenticar: **Dashboard**.
- Si requiere seleccionar equipo: permanece en Login/Equipo hasta elegir.

---

### 2) Dashboard
**Objetivo**: Vista resumen con métricas y accesos rápidos.

**Estructura**
- Header: selector de equipo, buscador global, botón “Crear”.
- Panel de KPIs (alcance, engagement, leads, presupuesto consumido).
- Bloque “Próximas piezas” (lista con fecha).
- Bloque “Campañas activas”.
- Accesos rápidos a vistas principales.

**Campos**
- Filtros por rango de fechas.
- Selector de canal (RRSS, email, paid).

**Acciones**
- Crear pieza/campaña/tarea.
- Ir al calendario o kanban.
- Ver detalle de campaña.

**Navegación**
- Enlaces a **Calendario DnD**, **Kanban**, **Campañas**, **Backlog**, **Tareas**, **Biblioteca**, **Ajustes**.

---

### 3) Calendario DnD
**Objetivo**: Planificación temporal con arrastrar y soltar.

**Estructura**
- Header con selector de vista (Mes/Semana/Día).
- Columna lateral con lista de piezas disponibles (drag).
- Grilla calendario con slots por día/hora.

**Campos**
- Filtro por campaña, canal y estado.
- Búsqueda de piezas.

**Acciones**
- Drag & drop de piezas al calendario.
- Reprogramar (arrastrar) o editar pieza.
- Crear nueva pieza desde un slot.

**Navegación**
- Click en pieza: **Editor de pieza**.
- Botón “Ver campaña”: **Campañas**.
- Enlace a **Backlog** para añadir piezas.

---

### 4) Editor de pieza
**Objetivo**: Editar contenido y metadatos de una pieza.

**Estructura**
- Header: título de la pieza + estado.
- Panel central: editor de contenido.
- Panel lateral: metadatos y tareas.

**Campos**
- Título.
- Canal (RRSS, email, blog, paid).
- Estado (Idea, En progreso, Aprobación, Programado, Publicado).
- Fecha/hora de publicación.
- Tags.
- Campaña asociada.
- Brief / objetivos.
- Asignado a.

**Acciones**
- Guardar borrador.
- Enviar a aprobación.
- Programar/publicar.
- Adjuntar recursos desde Biblioteca.
- Crear tarea relacionada.

**Navegación**
- Volver a **Calendario DnD**.
- Abrir **Biblioteca** para adjuntos.
- Ver **Tareas** relacionadas.

---

### 5) Kanban
**Objetivo**: Gestionar flujo de trabajo por estados.

**Estructura**
- Columnas: Idea, En progreso, Aprobación, Programado, Publicado.
- Tarjetas por pieza.
- Panel lateral de filtros.

**Campos**
- Filtros por campaña, canal, responsable.
- Búsqueda de tarjetas.

**Acciones**
- Arrastrar tarjetas entre columnas.
- Editar pieza desde tarjeta.
- Crear pieza en columna.

**Navegación**
- Click tarjeta: **Editor de pieza**.
- Enlace “Ver tareas”: **Tareas**.
- Enlace “Ver campaña”: **Campañas**.

---

### 6) Campañas
**Objetivo**: Gestionar campañas con objetivos y piezas asociadas.

**Estructura**
- Lista de campañas (tabla o cards).
- Panel de detalle de campaña seleccionada.
- Métricas de rendimiento.

**Campos**
- Nombre de campaña.
- Objetivo.
- Presupuesto.
- Fecha inicio/fin.
- Estado.
- Canales.

**Acciones**
- Crear campaña.
- Editar campaña.
- Asociar piezas.
- Exportar reporte.

**Navegación**
- Ir al **Editor de pieza** desde una campaña.
- Abrir **Calendario DnD** filtrado por campaña.
- Volver a **Dashboard**.

---

### 7) Backlog
**Objetivo**: Banco de ideas y piezas pendientes.

**Estructura**
- Lista de ideas con etiquetas.
- Botón “Convertir a pieza”.
- Panel de filtros.

**Campos**
- Título/idea.
- Descripción breve.
- Prioridad.
- Tags.
- Canal sugerido.

**Acciones**
- Crear idea.
- Convertir a pieza.
- Priorizar (drag en lista o select).

**Navegación**
- Convertir a pieza → **Editor de pieza**.
- Enviar a **Kanban**.
- Programar en **Calendario DnD**.

---

### 8) Tareas
**Objetivo**: Gestionar tareas y responsables.

**Estructura**
- Lista de tareas con estados.
- Panel de detalle de tarea.
- Filtros por responsable y estado.

**Campos**
- Título de tarea.
- Descripción.
- Asignado a.
- Vencimiento.
- Estado (Pendiente, En progreso, Hecho).
- Relación con pieza/campaña.

**Acciones**
- Crear tarea.
- Marcar como hecha.
- Reasignar.
- Añadir comentario.

**Navegación**
- Click en pieza relacionada → **Editor de pieza**.
- Volver a **Kanban**.
- Volver a **Dashboard**.

---

### 9) Biblioteca
**Objetivo**: Centralizar recursos y plantillas.

**Estructura**
- Grid de recursos (imágenes, vídeos, docs).
- Panel de filtros y búsqueda.
- Vista de detalle del recurso.

**Campos**
- Nombre del recurso.
- Tipo (imagen, video, documento).
- Tags.
- Tamaño/fecha.

**Acciones**
- Subir recurso.
- Organizar en carpetas.
- Copiar enlace/descargar.

**Navegación**
- Insertar recurso en **Editor de pieza**.
- Asociar recurso a **Campañas**.

---

### 10) Ajustes
**Objetivo**: Configurar la cuenta, equipo y permisos.

**Estructura**
- Menú lateral: Perfil, Equipo, Permisos, Integraciones, Notificaciones.
- Panel principal con formularios.

**Campos**
- Perfil: nombre, email, idioma.
- Equipo: nombre, logo, miembros.
- Permisos: roles, accesos por módulo.
- Integraciones: APIs conectadas.
- Notificaciones: email, push.

**Acciones**
- Guardar cambios.
- Invitar miembro.
- Conectar/desconectar integración.
- Cambiar de equipo.

**Navegación**
- Volver a **Dashboard**.
- Cambiar equipo → **Login/Equipo**.
