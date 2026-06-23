# AMPD — Web nueva

Web rediseñada de la Asociación Madrileña de Psicología del Deporte. Construida con **Astro** (framework estático moderno).

## Estructura

```
ampd-web/
├── src/
│   ├── layouts/Layout.astro       # Header + footer compartidos
│   ├── pages/
│   │   ├── index.astro             # Inicio (hero + agenda + CTA)
│   │   ├── asociate.astro          # Beneficios + planes + formulario
│   │   ├── recursos.astro          # Noticias + recursos profesionales
│   │   ├── equipo.astro            # Junta directiva
│   │   └── contacto.astro          # Email + formulario
│   └── styles/global.css           # Sistema de diseño (variables CSS)
├── package.json
└── astro.config.mjs
```

## Ejecutar en local

```bash
cd ampd-web
npm install
npm run dev
```

Abre `http://localhost:4321`.

## Construir para producción

```bash
npm run build
```

Genera la carpeta `/dist` con los archivos estáticos listos para subir.

## Desplegar (gratis)

### Opción 1 — Vercel (recomendado)
1. Sube el código a un repo en GitHub
2. Entra en vercel.com, "Import Project", conecta el repo
3. Vercel detecta Astro automáticamente, deploy en 30s
4. En settings → Domains, añade `ampd.es`
5. Cambias DNS en SiteGround para apuntar a Vercel

### Opción 2 — Netlify
Mismo flujo. `npm run build`, sube `dist/`, conecta dominio.

### Opción 3 — SiteGround
Sube el contenido de `dist/` por FTP a la carpeta del hosting actual.

## Personalizar

- **Colores y tipografía**: `src/styles/global.css` (variables `--ink`, `--flame`, `--paper`)
- **Logo**: por ahora una "A" tipográfica. Si tienes logo real, sustituye `.logo-mark` en `Layout.astro`
- **Contenido**: cada página es un archivo `.astro` legible
- **Eventos/noticias**: están hardcodeados en `index.astro` y `recursos.astro`. Para gestión dinámica futura: integración con Notion, Sanity o Decap CMS

## Pendientes para producción

1. **Logo real** de la AMPD (SVG)
2. **Backend de formularios** — opciones:
   - Formspree (gratis para empezar)
   - Netlify Forms (gratis si despliegas en Netlify)
   - Tu Apps Script existente (el del registro AMPD)
3. **CMS para noticias** si quieren editar sin tocar código
4. **Páginas legales reales** (privacidad, aviso legal, cookies)
5. **Favicon** personalizado
6. **Imágenes** — actualmente solo tipografía, considera fotos de eventos

## Decisiones de diseño

- Paleta: azul medianoche (`#0A1628`) + naranja eléctrico (`#FF4D1F`) + crema cálida (`#F5F1E8`)
- Tipografías: Fraunces (display, italic personalidad) + Geist (body, técnica) + Geist Mono (acentos)
- Estilo editorial deportivo — números grandes, asimetrías, tarjetas con sombras duras (estilo "newspaper meets sport magazine")
