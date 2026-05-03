# Reich Productions — Sitio web

Página one-page premium para **Reich Productions**, productora audiovisual para talento de alto nivel.

Estética: minimalismo corporativo refinado en negro profundo (BlackRock × Palantir × Anthropic), tipografía Geist + Fraunces italic para acentos editoriales, animaciones sutiles activadas por scroll.

---

## Stack

- **HTML5** semántico
- **Tailwind CSS** vía CDN (sin build step)
- **JavaScript vanilla** (IntersectionObserver para reveals, sticky nav, smooth scroll)
- **Google Fonts**: Geist + Geist Mono + Fraunces

> Sitio 100% estático. No requiere servidor, Node ni base de datos.

---

## Estructura del proyecto

```
reich-productions/
├── index.html      ← Sitio completo (1.400+ líneas)
└── README.md       ← Este archivo
```

---

## Personalización rápida

Antes de desplegar, te recomiendo cambiar al menos estos puntos en `index.html`:

| Qué cambiar | Dónde buscar (Ctrl+F) |
|---|---|
| Email de contacto | `hola@reichproductions.com` |
| WhatsApp | `https://wa.me/0000000000` |
| Redes sociales (Instagram, YouTube, etc.) | `<!-- Social -->` en footer |
| Imágenes (si quieres usar las tuyas) | URLs `images.unsplash.com` |
| OG image (preview en redes) | `<meta property="og:image"` |
| Year copyright | Auto, calculado por JS |

### Sobre las imágenes

Actualmente usa imágenes de Unsplash (libres de derechos) vía CDN directo. Cuando tengas tus propias fotos del setup real:

1. Crea una carpeta `assets/` en la raíz.
2. Sube tus imágenes ahí (`assets/hero.jpg`, `assets/sony-zve10.jpg`, etc.).
3. Reemplaza las URLs `https://images.unsplash.com/...` por rutas locales `assets/tu-foto.jpg`.

---

## Despliegue: GitHub + Cloudflare Pages

### Paso 1 — Subir a GitHub

```bash
# Desde la carpeta del proyecto
git init
git add .
git commit -m "Initial commit — Reich Productions"
git branch -M main

# Crea un repo nuevo en github.com (sin README ni .gitignore)
# y luego:
git remote add origin https://github.com/TU_USUARIO/reich-productions.git
git push -u origin main
```

### Paso 2 — Conectar Cloudflare Pages

1. Entra a [dash.cloudflare.com](https://dash.cloudflare.com) → **Workers & Pages** → **Create application** → **Pages** → **Connect to Git**.
2. Autoriza GitHub y selecciona el repo `reich-productions`.
3. En la configuración de build:
   - **Project name**: `reich-productions` (o lo que prefieras)
   - **Production branch**: `main`
   - **Framework preset**: `None`
   - **Build command**: *(déjalo vacío)*
   - **Build output directory**: `/` *(la raíz)*
4. Click en **Save and Deploy**.

En ~30 segundos tu sitio estará en `https://reich-productions.pages.dev`.

### Paso 3 — Dominio personalizado (opcional)

Si tienes un dominio (ej. `reichproductions.com`):

1. En el proyecto de Pages → **Custom domains** → **Set up a custom domain**.
2. Introduce tu dominio.
3. Cloudflare te dará instrucciones para apuntar los DNS:
   - Si el dominio ya está en Cloudflare, se configura automáticamente.
   - Si está en otro registrador, añade el registro CNAME que te indique.
4. SSL se activa automáticamente (gratis, certificado Cloudflare).

### Actualizaciones futuras

Cualquier `git push` a `main` redespliega automáticamente. Cero fricción.

```bash
git add .
git commit -m "Actualización equipo / nuevas imágenes"
git push
```

---

## Desarrollo local

No necesitas ningún servidor especial. Tres opciones:

**Opción A — Doble click**
Abre `index.html` directamente en el navegador.

**Opción B — Live Server (VS Code)**
Instala la extensión [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) → click derecho en `index.html` → *Open with Live Server*.

**Opción C — Python**
```bash
# En la carpeta del proyecto
python3 -m http.server 8080
# Luego abre http://localhost:8080
```

---

## Performance & SEO

- ✅ Imágenes con `loading="lazy"` (excepto hero, que usa `fetchpriority="high"`)
- ✅ `prefers-reduced-motion` respetado
- ✅ Meta tags Open Graph para redes sociales
- ✅ HTML semántico (`<header>`, `<main>`, `<section>`, `<article>`, `<footer>`)
- ✅ Favicon SVG inline (sin requests adicionales)
- ✅ Tipografía con `display=swap` (no FOIT)
- ✅ Selección de texto, scroll y focus states personalizados

### Mejoras de producción recomendadas

Cuando tengas tiempo, considera:

1. **Auto-hospedar Tailwind** (en lugar de CDN) → ahorras ~30 KB y eliminas dependencia externa. Requiere paso de build con `tailwindcss CLI`.
2. **Optimizar imágenes**: convierte a WebP/AVIF y sirve desde tu carpeta `assets/`.
3. **Analytics**: añade [Cloudflare Web Analytics](https://www.cloudflare.com/web-analytics/) (gratis, sin cookies, RGPD-friendly).
4. **Formulario de contacto real**: sustituye el `mailto:` por un endpoint con [Cloudflare Workers](https://workers.cloudflare.com/) o [Formspree](https://formspree.io/).

---

## Secciones del sitio

| # | Sección | ID |
|---|---|---|
| 0 | Hero cinematográfico | `#top` |
| 1 | Marquee tipográfico | — |
| 2 | Manifiesto / intro | — |
| 3 | Servicios (4 cards) | `#servicios` |
| 4 | Equipo técnico (10 piezas) | `#equipo` |
| 5 | Ubicaciones (3 formatos) | `#ubicaciones` |
| 6 | CTA / Contacto | `#contacto` |
| 7 | Footer | — |

---

## Licencia & créditos

- Imágenes hero/cards: [Unsplash](https://unsplash.com/license) (uso comercial libre).
- Fuentes: Google Fonts (Open Font License).
- Código del sitio: úsalo como quieras para tu negocio.

---

**Reich Productions** — Crafted with cinematic intent.
