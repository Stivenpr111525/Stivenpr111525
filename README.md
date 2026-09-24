# Hola, soy Stiven 👋

**Ingeniero de automatización.** Construyo agentes con LLMs, integraciones por API y
automatizaciones que hoy están en producción atendiendo clientes reales.

La mayor parte de lo que hago vive en repositorios privados —es de clientes o es producto
propio— así que aquí está lo que construí, cómo está hecho y dónde se puede ver funcionando.

📍 Barranquilla, Colombia · Disponible para trabajo remoto
✉️ stivendavidperezrivera@gmail.com · [LinkedIn](https://linkedin.com/in/stiven-perez-544754404)

---

## Viantaris — CRM multi-tenant con agente de IA
🔗 [viantaris.com](https://viantaris.com) · en producción con clientes reales · *código privado*
📄 **[Case study completo: arquitectura, barreras y qué garantiza](casos/viantaris.md)**

Un agente responde por WhatsApp Business, califica al cliente y escala a una persona cuando
hace falta.

Lo que lo diferencia no son las funciones, es lo que **el modelo no puede hacer**: hay
barreras comprobadas en código contra la base de datos, no pedidas en el prompt. El agente
no puede agendar sin que el cliente lo confirme, no puede reservar un horario que no
ofreció, no puede usar un nombre que el cliente nunca dio, y no puede decir un precio que
no esté registrado. Cada una existe porque el modelo, en algún momento, ignoró una
instrucción explícita.

`TypeScript` · `PostgreSQL` con Row Level Security · `Supabase` · `Claude API` y cualquier
API compatible con OpenAI · Meta Cloud API · cola de trabajos en Postgres · `Next.js`

Y lo que sostiene que esté vivo: CI/CD que revierte solo si fallan las comprobaciones de
salud, vigilancia cada 2 minutos desde dos máquinas independientes, y una **prueba semanal
de restauración del respaldo** — porque un respaldo que nunca se restauró es una suposición.

---

## Job Flash — búsqueda de empleo automatizada
🔗 [digitraffic-jobs.vercel.app](https://digitraffic-jobs.vercel.app) · plataforma propia con usuarios reales

Captura ofertas de LinkedIn con un scraper en Playwright, las clasifica con Claude a través
de un servicio en Express, y ofrece un editor donde cada usuario adapta su CV y su carta de
presentación a la vacante antes de postular.

`Playwright` · `Claude API` · `Express` · `Supabase` · `Next.js` · VPS Linux con procesos
gestionados

---

## Pipeline de prospección B2B
*código privado (cliente)* · 📄 **[Case study completo](casos/prospeccion-b2b.md)**

Busca prospectos en LinkedIn y, **cuando LinkedIn no tiene los datos, va al sitio web del
negocio a completarlos**. Deduplicación por perfil único, ejecución programada dos veces al
día, y un tablero con autenticación donde el equipo comercial filtra y marca contactados.

`Playwright` · `Supabase` · `Next.js` · cron sobre VPS Linux

---

## Auto Export — plugin de Figma
*herramienta interna*

Detecta desde qué ángulo está tomada una foto de producto —por el nombre de la capa o, si
no hay pista, por las proporciones del contenido— y decide su encuadre dentro del frame.
Redujo el armado de una ficha **de 6 minutos a unos segundos**, y el equipo dedicado a esa
tarea pasó **de 3 a 1 persona**.

`TypeScript` · Figma Plugin API · sin bundler y sin acceso a red

---

## Cómo trabajo

Diseño la solución, la construyo, la despliego y la opero — incluidas las comprobaciones
que impiden que falle en silencio, que suele ser la parte que nadie hace.

Desarrollo apoyándome en agentes de IA, y mi trabajo ahí es el de siempre: decidir la
arquitectura, revisar lo que producen y responder por lo que llega a producción. En la
última revisión de código que hice encontré dos defectos con consecuencia real —uno podía
borrar la cuenta del dueño de otro cliente— antes de que se desplegaran.

**Python** (intermedio) · **SQL** (intermedio) · **JavaScript/TypeScript** · PostgreSQL ·
Playwright · REST APIs y webhooks · Linux/VPS · Nginx · Docker · n8n
