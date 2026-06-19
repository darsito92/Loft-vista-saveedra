# Loft vista Saavedra — Web

> Web premium con animaciones de scroll y reservas por WhatsApp para las cabañas tipo loft en Puerto Saavedra, Chile.

**Instagram:** [@loft.vista.saavedra](https://www.instagram.com/loft.vista.saavedra/)
**WhatsApp:** +56 9 3953 1899
**Generado el:** 19 de junio de 2026

---

## 1. Qué se construyó

Una web de una sola página (`index.html`) totalmente estática, con:

- **Hero a pantalla completa** con la portada real del Airbnb (Loft 1) y efecto **parallax** al hacer scroll.
- **Navegación fija** con efecto blur que se intensifica al desplazar.
- **6 secciones** con animaciones de scroll-reveal (Intersection Observer):
  1. Hero — eyebrow, título, descripción, 3 stats y dos CTAs (WhatsApp + galería).
  2. El proyecto — texto + foto con bordes decorativos.
  3. Experiencia — grid de 6 features con iconos SVG.
  4. **Las cabañas** — dos tarjetas con foto, badge, rating, specs y dos botones (WhatsApp + Airbnb).
  5. Galería — mosaico tipo masonry con hover-zoom.
  6. Ubicación — sección oscura verde-río con lista y parallax suave.
  7. CTA final — fondo con foto difuminada y botón gigante.
  8. Footer oscuro con navegación y datos.
- **Botón flotante de WhatsApp** abajo a la derecha con animación de pulse continua.
- **Mensajes pre-rellenados distintos** en WhatsApp según contexto (general, Loft 1, Loft 2).

---

## 2. Datos reales que se usaron

### Instagram (scrapeado automáticamente)

| Campo | Valor |
|---|---|
| Handle | `loft.vista.saavedra` |
| Nombre | Loft vista Saavedra |
| Bio | "Cabañas tipo loft a orillas del río Imperial, en Puerto Saavedra. Diseño moderno y minimalista, con hermosas vistas." |
| Seguidores | 1.942 |
| Posts | 59 |
| Fotos descargadas | 13 + foto de perfil |

### Airbnb (scrapeado automáticamente)

**Loft 1** — [airbnb.cl/rooms/1322424327355890649](https://www.airbnb.cl/rooms/1322424327355890649)

- ★ **4.55** · 11 reseñas
- 2 huéspedes · 1 habitación · 1 cama matrimonial · 1 baño privado
- Cama matrimonial en el 2º nivel · Estufa a combustión lenta
- WiFi · TV con streaming · Cocina equipada · Estacionamiento privado
- Llegada autónoma · A pasos del mar · Cerca de restaurantes

**Loft 2** — [airbnb.cl/rooms/1408873434525786736](https://www.airbnb.cl/rooms/1408873434525786736)

- ★ **4.67** · 6 reseñas · **Pet friendly**
- 2 huéspedes · 1 habitación · 1 cama matrimonial · 1 baño privado
- Calefacción a combustión lenta · Baño con agua caliente
- WiFi · TV con streaming · Cocina equipada · Estacionamiento privado
- Acceso a la playa · Tranquilo y céntrico

### CTA de reservas

Todos los botones disparan `https://wa.me/56939531899` con mensaje pre-rellenado:

- **Botones generales:** *"Hola! Me gustaría reservar en Loft vista Saavedra. ¿Tienen disponibilidad?"*
- **Botón Loft 1:** *"Hola! Quiero consultar disponibilidad del Loft 1 (Loft vista Saavedra). ¿Me ayudás con las fechas?"*
- **Botón Loft 2:** *"Hola! Quiero consultar disponibilidad del Loft 2 (Loft vista Saavedra). ¿Me ayudás con las fechas?"*

---

## 3. Estructura de archivos

```
Loft-savedra/
├── index.html          ← la web completa (HTML + CSS + JS en un solo archivo)
├── README.md           ← este archivo
└── assets/loft/        ← todas las imágenes
    ├── profile.jpg            (foto de perfil del Instagram)
    ├── loft-1-cover.jpg       (portada Airbnb Loft 1)
    ├── loft-2-cover.png       (portada Airbnb Loft 2)
    └── post-1.jpg … post-13.jpg   (fotos del Instagram)
```

**Tamaño total:** ~1.3 MB. Es 100% estática, sin dependencias.

---

## 4. Cómo usarla

### Abrir localmente

Doble clic en `index.html` — se abre en cualquier navegador.

### Cambiar el número de WhatsApp

Abrí `index.html` con cualquier editor de texto (Notepad, VS Code, lo que tengas) y buscá:

```js
const WHATSAPP_NUMBER = '56939531899';
```

Cambialo por tu número en formato internacional, sin `+` ni espacios.
Ejemplos: Chile `56912345678` · Argentina `5491123456789` · México `5215512345678`.

### Cambiar fotos

Reemplazá cualquier archivo en `assets/loft/` manteniendo el mismo nombre. El HTML las cargará automáticamente. Tamaños recomendados: 1600×1200 px o similares.

### Subirla a internet (gratis)

La carpeta es estática, sirve cualquier hosting:

- **Netlify Drop** — arrastrá la carpeta a [netlify.com/drop](https://app.netlify.com/drop) → URL pública en 10 segundos.
- **Vercel** — [vercel.com](https://vercel.com), import folder.
- **GitHub Pages** — subir a un repo y activar Pages.
- **Cloudflare Pages** — [pages.cloudflare.com](https://pages.cloudflare.com).

---

## 5. Decisiones de diseño

| Elemento | Decisión | Por qué |
|---|---|---|
| Paleta | Crema `#f5f1ea` + verde río `#2f5d4b` + cobre `#b6724a` | Evoca naturaleza, madera y agua sin caer en lo "rústico cabaña" |
| Tipografía títulos | Cormorant Garamond | Aporta sensación premium / boutique |
| Tipografía texto | Inter | Legible y moderna |
| Hero | Imagen real del Airbnb con parallax | Coherencia con lo que verá el huésped al llegar al booking |
| CTA principal | Verde WhatsApp en todos los botones | El usuario pidió reserva por WhatsApp como acción principal |
| Animaciones | Scroll-reveal sutil + parallax suave | Premium sin marear |

---

## 6. Skills y herramientas que se usaron

### Skills del entorno

| Skill | Uso |
|---|---|
| `web-scrolling` (kit-web-scrolling) | Plantilla y guía para webs con animaciones de scroll. Sirvió como base de comportamiento (bienvenida, generar HTML con scroll, abrir en navegador). |
| `instagram-a-web` (kit-instagram-web) | Aportó el scraper de Playwright para Instagram. Se reutilizó su `node_modules` con Playwright instalado. |

### Tecnologías del proyecto final

- **HTML5** semántico (`<header>`, `<nav>`, `<section>`, `<article>`, `<footer>`).
- **CSS puro** — variables CSS para tematización, `grid` + `flex` para layout, `aspect-ratio` para fotos, `backdrop-filter` para el blur del nav.
- **JavaScript vanilla** — Intersection Observer para reveals + scroll listeners para parallax. Sin librerías externas.
- **Google Fonts** — Cormorant Garamond + Inter.
- **wa.me deep links** — links directos a WhatsApp con mensaje pre-rellenado por contexto.

### Herramientas usadas durante el desarrollo

| Herramienta | Para qué |
|---|---|
| **Playwright** (Chromium headless) | Scrapear el perfil de Instagram y los dos listings de Airbnb (Airbnb devuelve 403 a fetch directo). |
| **Node.js** (v24.15) | Correr los scripts de scraping y descarga. |
| **https / fs** (Node nativo) | Descargar las imágenes encontradas (perfil + posts + portadas Airbnb). |
| `scrape-loft.js` | Bajar fotos y metadata del Instagram. |
| `scrape-airbnb.js` | Bajar metadata de los dos listings de Airbnb (título, rating, specs, descripción). |
| `download-covers.js` | Bajar las portadas (`og:image`) de los Airbnb. |

---

## 7. Cronología de lo que hicimos

1. Pediste una web con scroll a partir del Instagram `@loft.vista.saavedra` y reservas por WhatsApp.
2. Scrapeamos el Instagram con Playwright → 13 fotos + datos del perfil.
3. Generamos la primera versión de la web con paleta natural, parallax, galería tipo masonry, botón flotante de WhatsApp y placeholder para el número.
4. Pasaste los dos links de Airbnb y el WhatsApp real `+56 9 3953 1899`.
5. Scrapeamos los dos Airbnb (rating, specs, descripción) y descargamos las portadas.
6. Actualizamos la web:
   - WhatsApp real activo en todos los botones.
   - Hero con la portada real del Loft 1 + parallax + stats reales (★ 4.6, 17 reseñas).
   - Nueva sección **"Las cabañas"** con las dos tarjetas, badges, rating, specs y dos botones cada una (WhatsApp + Airbnb).
   - Mensajes pre-rellenados distintos por loft.
7. Movimos todo a una carpeta limpia `C:\Users\Usuario\Downloads\Loft-savedra` con sólo lo necesario.
8. Generamos este `README.md`.

---

## 8. Próximos pasos sugeridos

- **Subir a Netlify** para tener una URL pública que puedas pegar en el "link in bio" del Instagram.
- **Dominio propio** (ej. `loftvistasaavedra.cl`) — Netlify lo conecta en 5 min.
- **Precios** — cuando quieras mostrar valores, te los integramos en la sección de cabañas.
- **Reseñas reales** — podemos sumar una sección con 2-3 reseñas destacadas de Airbnb.
- **Video en el hero** — si tenés un clip mp4 (10-20s), lo metemos en lugar de la foto fija para más impacto.
- **Pixel de Meta / Google Analytics** — para medir cuánta gente hace click en "Reservar por WhatsApp".

---

*Web generada con Claude Code · Junio 2026*
