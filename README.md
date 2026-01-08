# MarketingPlanner

Un tablero central donde se ve qué hay que publicar/preparar/lanzar, cuándo, quién lo hace y en qué estado está, con un calendario que manda.

## Estructura recomendada

### 1) Dashboard “Hoy / Esta semana”
- Próximos hitos (lanzamientos, shootings, rebajas, reposiciones, ferias, envíos, etc.).
- Tareas bloqueadas (esperando foto, stock, aprobación, proveedor).
- Contenidos en revisión (copys, creatividades, emails).
- KPIs rápidos: ventas web, ROAS, tráfico, conversión, captación email (si hay datos conectados).

### 2) Calendario editorial (la joya)
Vistas:
- Mes / Semana.
- Por canal (IG feed, reels, stories, TikTok, Email, Web, Ads).
- Por colección (Bolonia, Cullera, etc.) o por tema (invierno, boda, rebajas).

Cada item del calendario es una pieza con:
- Canal, formato, objetivo (awareness/venta/retención), fecha/hora.
- Responsable + aprobador.
- Estado: Idea → En proceso → En revisión → Programado → Publicado → Reciclable.
- Assets: foto/video, copy, hashtags, link UTM, producto asociado (SKU/Shopify).

### 3) Campañas (pipeline tipo CRM)
- Una campaña = “Rebajas enero”, “Nueva tira pelo vino”, “San Valentín”, “Colección SS”.
- Fechas clave (inicio, teaser, lanzamiento, cierre).
- Checklist por campaña (creatividades, landing, email, ads, stock, logística).
- Presupuesto (si hay ads).
- Resultado final (ventas atribuidas, CAC, aprendizajes).

### 4) Ideas / Backlog (la granja de oro)
Captura rápida:
- Idea, tipo (reel, post, collab, blog, email), prioridad, temporada.
- Inspiración (link), ejemplo, referencia visual.
- “¿Qué producto empuja?” y “¿Qué objeción responde?”.

### 5) Biblioteca de contenidos y assets
- Tags: modelo, color, temporada, UGC, producto, lifestyle, fabricación.
- Derechos: “OK para ads / solo orgánico”.
- Versiones: vertical 9:16, cuadrado, stories, etc.

### 6) Tareas y responsables (sin volverse Jira)
- Tareas vinculadas a campaña o a pieza de contenido.
- Dependencias simples (“necesita fotos”).
- SLA/fecha límite y recordatorios.

### 7) Post-mortem / Aprendizajes
- Qué funcionó / qué no.
- Creatividad ganadora.
- Hipótesis para la próxima.
- Reutilizable (plantilla de reel, copy, email).

## Campos y estados estándar
- Estados: Idea → Draft → Producción → Revisión → Aprobado → Programado → Publicado → Analizado → Archivado.
- Prioridad: Baja / Media / Alta / “Fecha fija sí o sí”.
- Etiquetas útiles: modelo, material, evento, objetivo, audiencia.

## Roles y permisos
- Admin (estructura, settings).
- Marketing Lead (aprueba).
- Creador (sube assets, edita drafts).
- Operaciones (marca “stock ok / logística ok”).
- Viewer (solo lectura).

## Automatizaciones mínimas
- Si un contenido pasa a Revisión, notifica al aprobador.
- Si una campaña está a 7 días y falta checklist, alerta.
- Si está Programado pero sin asset/link, bloqueo rojo.
- Plantillas por tipo: Reel, Email, Lanzamiento, Reposición.

## Stack recomendado
- Frontend: React + TypeScript (Next.js).
- DB + Auth: Supabase.
- Storage: Supabase Storage.
- Calendario: FullCalendar o similar.
- Editor/notas: Markdown sencillo + adjuntos.
- Notificaciones: email/Slack.

## MVP en 10 pantallas
- Login/Equipo.
- Dashboard.
- Calendario (arrastrar y soltar).
- Crear/editar pieza de contenido.
- Vista Kanban de contenidos.
- Campañas (lista + detalle).
- Backlog de ideas.
- Tareas (por persona).
- Biblioteca de assets.
- Ajustes (canales, estados, roles).

## Diferenciales para Tuilus
- Vincular contenido a producto Shopify (SKU/URL) + UTM automático.
- Campo “Stock confirmado” (sí/no) antes de lanzar.
- “Repost / reciclable” como etiqueta.
- UGC tracker: quién envió, permiso, fecha, uso permitido.
