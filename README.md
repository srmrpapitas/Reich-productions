# Reich Productions — Sitio web

Página one-page premium para **Reich Productions**, productora audiovisual para talento de alto nivel en Antwerp, Bélgica.

🌐 **Live:** [reich-productionss.pages.dev](https://reich-productionss.pages.dev)
📸 **Instagram:** [@nicoreich19](https://instagram.com/nicoreich19)
📱 **WhatsApp:** +32 494 81 45 43
📧 **Email:** Nicholasgondimreich@gmail.com

---

## Stack

- **HTML5** semántico
- **Tailwind CSS** vía CDN (sin build step)
- **JavaScript vanilla** (i18n custom, IntersectionObserver, sticky nav)
- **Google Fonts:** Geist + Geist Mono + Fraunces

Sitio 100% estático. No requiere servidor, Node ni base de datos.

---

## Estructura del proyecto

```
Reich-Productions/
├── README.md                       Este archivo
├── .gitignore                      Archivos a ignorar por Git
├── index.html                      Sitio completo (~2.000 líneas)
└── assets/
    ├── sony-zve10ii.avif           Sony ZV-E10 II
    ├── dji-rs4.jpg                 DJI RS 4
    ├── osmo-action-5.jpg           DJI Osmo Action 5 Pro
    ├── dji-mic3.jpg                DJI Mic 3
    ├── antelope-zen-quadro.jpg     Antelope Zen Quadro
    └── zyxel-nr2301.jpg            ZyXEL NR2301 5G Router
```

---

## Funcionalidades

### Multi-idioma (3 idiomas)
- **Inglés** (default)
- **Holandés** (Nederlands)
- **Español**

Switcher EN/NL/ES en el menú. Detecta el idioma del navegador automáticamente y recuerda la elección del usuario en localStorage.

### Secciones
1. **Hero** cinematográfico con imagen de cámara en movimiento
2. **Marquee** tipográfico
3. **Manifiesto** con stats
4. **Servicios** (4 cards con hover-zoom — IRL incluye vídeo de YouTube embebido)
5. **Equipo técnico** (10 piezas con specs reales y fotos del fabricante)
6. **Precios** (6 servicios con tarifas de tu plan financiero)
7. **Ubicaciones** (estudio / chalés / restaurantes)
8. **Contacto** + footer

### WhatsApp integrado
- Botón flotante verde siempre visible (con animación pulse)
- Botones "Book on WhatsApp" en cada tarjeta de precios
- Mensajes pre-rellenados según el idioma activo y el servicio elegido

### Vídeo IRL
Embebido desde YouTube en la card "IRL for influencers and athletes":
autoplay, muted, loop, sin controles, sin marca de YouTube. Aspect ratio
mantenido con la card.

---

## Despliegue

El sitio está conectado a [Cloudflare Pages](https://pages.cloudflare.com).
Cualquier `git push` a la rama `main` redespliega automáticamente en
30-60 segundos.

URL pública: `https://reich-productionss.pages.dev`

### Actualizar contenido

| Quieres cambiar... | Busca esto en `index.html` |
|---|---|
| Tu número de WhatsApp | `whatsapp: '32494814543'` |
| Tu email | `Nicholasgondimreich@gmail.com` |
| Tu Instagram | `nicoreich19` |
| Idioma por defecto | `defaultLang: 'en'` (cámbialo a `'nl'` o `'es'`) |
| Precios | Búscalos por valor: `€100`, `€350`, `€2.000`, etc. |
| Vídeo de IRL | El ID `03gZ2RvwRVA` aparece dos veces en la sección IRL |

### Sustituir imágenes
Si sustituyes alguna imagen del equipo, mantén el mismo nombre de archivo
en `assets/` y se actualizará sola en la web.

---

## Performance & SEO

- ✅ Imágenes con `loading="lazy"` (excepto hero, que usa `fetchpriority="high"`)
- ✅ AVIF para Sony (mejor compresión que JPG)
- ✅ `prefers-reduced-motion` respetado
- ✅ Meta tags Open Graph
- ✅ HTML semántico
- ✅ Favicon SVG inline
- ✅ Tipografía con `display=swap`

---

## Desarrollo local

Tres formas de previsualizar el sitio antes de subirlo:

**Opción A — Doble click**
Abre `index.html` directamente en el navegador.

**Opción B — Live Server (VS Code)**
Extensión "Live Server" → click derecho en `index.html` → *Open with Live Server*.

**Opción C — Python**
```bash
cd Reich-Productions
python3 -m http.server 8080
# luego abre http://localhost:8080
```

---

## Mejoras futuras posibles

- [ ] Dominio personalizado: `reichproductions.com`
- [ ] Auto-hospedar Tailwind (eliminar dependencia CDN)
- [ ] Cloudflare Web Analytics (RGPD-friendly, sin cookies)
- [ ] Migrar vídeo IRL a Cloudflare Stream (sin marca de YouTube)
- [ ] Formulario de contacto con Cloudflare Workers
- [ ] Más idiomas (francés, italiano, alemán)
- [ ] Sección de "Trabajos pasados" con casos de estudio

---

## Créditos

- Imágenes hero/cards genéricas: [Unsplash](https://unsplash.com/license) (uso comercial libre)
- Imágenes de equipo: fabricantes (Sony, DJI, Antelope, ZyXEL) — uso editorial
- Fuentes: Google Fonts (Open Font License)

---

**Reich Productions** — Crafted with cinematic intent.
