# Profe Ani Edutech — Landing Page

Sitio web personal de **Profe Ani Edutech**, plataforma de recursos pedagógicos con IA para docentes de nivel inicial, primario y secundario.

🌐 **URL:** [www.profeaniedutech.com.ar](https://www.profeaniedutech.com.ar)

---

## 📁 Archivos del proyecto

| Archivo | Descripción |
|---|---|
| `index.html` | Landing page principal (este archivo) |
| `blog_5to_grado_firebase.html` | Blog escolar del 5° Grado Hugo Leonelli |
| `fichas_interactivas_mundial2026.html` | Fichas interactivas del Mundial 2026 |

---

## 🗂️ Estructura de secciones

| ID | Sección | Descripción |
|---|---|---|
| — | Hero / Header | Título animado, subtítulo y botones de acceso rápido |
| — | Beneficios | 4 cards: Ahorra Tiempo, Prompts IA, Innovación, Menos Estrés |
| `#generador` | Generador de Prompts | Genera prompts pedagógicos listos para usar en IA |
| `#recursos-gratis` | Pack Gratuito | Formulario para acceder al Kit de Prompts + Guía |
| `#fichas` | Fichas Mundial 2026 | Enlace a las fichas interactivas del Mundial |
| `#blog-quinto` | Blog de 5° Grado | Enlace al blog escolar Hugo Leonelli |
| `#tienda` | Tienda Premium | 3 productos destacados + botón a la tienda completa |
| `#sobre-mi` | Sobre Mí | Presentación y bio de la Profe Ani |
| `#privacidad` | Política de Privacidad | Cumplimiento Ley 25.326 (Argentina) — en el footer |

---

## ⚙️ Tecnologías utilizadas

| Tecnología | Uso |
|---|---|
| HTML5 / CSS3 | Estructura y estilos base |
| [Tailwind CSS](https://cdn.tailwindcss.com) (CDN) | Utilidades de diseño responsivo |
| [Font Awesome 6.4](https://cdnjs.cloudflare.com) | Iconografía |
| Google Fonts — Inter + Fredoka | Tipografías |
| Google Tag Manager (`GTM-PNP67S35`) | Analítica y seguimiento |
| Google Apps Script | Backend: registro de emails y validación de límite de usos |
| Google Drive | Almacenamiento de recursos gratuitos |
| `localStorage` | Control local del límite de usos del generador |
| Schema.org (JSON-LD) | SEO estructurado (tipo: Person) |

---

## 🎯 Generador de Prompts Pedagógicos

El generador es la funcionalidad principal del sitio. Permite a docentes crear prompts listos para usar en ChatGPT, Gemini u otras IAs.

### Flujo de uso

1. El docente ingresa su **correo electrónico**
2. Selecciona el **grado/nivel** (Inicial, Primario o Secundario)
3. Escribe el **tema** de la clase (máx. 500 caracteres)
4. Elige el **formato** del prompt:
   - Secuencia Didáctica
   - Proyecto ABP
   - Experiencia STEAM
5. El prompt se genera **localmente** (sin llamada a IA externa) y se muestra al instante
6. El uso se registra vía **Google Apps Script** y se guarda en **localStorage**

### Sistema de límites

- Cada correo tiene **3 generaciones gratuitas**
- El control es **doble**: localStorage (cliente) + Apps Script (servidor)
- Al alcanzar el límite se muestra un bloqueo con link a la Tienda Premium
- El contador se muestra al usuario mientras genera

### Anti-spam

Ambos formularios (generador y recursos gratis) incluyen un **honeypot** oculto que descarta envíos automáticos de bots.

---

## 🔐 Seguridad y privacidad

- La URL del Apps Script y la URL de Google Drive están **ofuscadas en base64** mediante las funciones `getSU()` y `getDriveUrl()`, evitando exposición directa en el código fuente
- Los datos de correo electrónico se tratan conforme a la **Ley 25.326 de Protección de Datos Personales** de la República Argentina
- No se ceden ni comercializan datos a terceros
- El titular puede solicitar acceso, rectificación o supresión vía [@profeani.edutech](https://www.instagram.com/profeani.edutech/)

---

## 💎 Tienda — Productos destacados

Los 3 productos de la sección tienda enlazan directamente a cada página de producto en [profeani.empretienda.com.ar](https://profeani.empretienda.com.ar):

| Producto | Precio | URL |
|---|---|---|
| Álbum Mundial 2026 — Archivo Editable | $5.000 ARS | [Ver producto](https://profeani.empretienda.com.ar/plantillas-listas-para-imprimir/album-mundial-2026-archivo-editable) |
| Kit Mundialista 2026 | $3.000 ARS | [Ver producto](https://profeani.empretienda.com.ar/plantillas-listas-para-imprimir/kit-mundialista-2026) |
| Juegos Mundialistas | $3.000 ARS | [Ver producto](https://profeani.empretienda.com.ar/plantillas-listas-para-imprimir/juegos-mundialistas) |

Las imágenes de portada se sirven desde el CDN de empretienda (`d22fxaf9t8d39k.cloudfront.net`).

---

## 🌐 SEO y metadatos

- `<title>` y `<meta description>` configurados
- **Open Graph** completo (título, descripción, imagen, URL) para Facebook/LinkedIn
- **Twitter Cards** (`summary_large_image`)
- `<link rel="canonical">` apuntando a `https://www.profeaniedutech.com.ar`
- `<meta name="robots" content="index, follow">`
- **Schema.org JSON-LD** tipo `Person` con `sameAs` a Instagram, YouTube y TikTok
- Favicon SVG inline

---

## 📱 Diseño responsivo

- **Desktop:** navegación horizontal, grids de 3-4 columnas
- **Mobile:** menú hamburguesa con animación X, grids de 1-2 columnas
- **Floating CTA** (botón "✨ Generar prompt") que aparece al hacer scroll más allá del hero
- **Toast notifications** para feedback de acciones al usuario

---

## 🔗 Redes sociales y comunidad

| Red | URL |
|---|---|
| Instagram | [@profeani.edutech](https://www.instagram.com/profeani.edutech/) |
| YouTube | [@profeani.edutech](https://www.youtube.com/@profeani.edutech) |
| TikTok | [@profeani.edutech](https://www.tiktok.com/@profeani.edutech) |
| WhatsApp (comunidad) | [Grupo gratuito](https://chat.whatsapp.com/JRJ2GajwmmWJJYvMglYzoo) |
| Tienda | [profeani.empretienda.com.ar](https://profeani.empretienda.com.ar) |

---

## 🛠️ Mantenimiento y actualizaciones frecuentes

### Actualizar contraseña / endpoint del Apps Script
Modificar la función `getSU()` en el `<head>` — reemplazar el array de fragmentos base64 con la nueva URL codificada.

### Actualizar URL de Google Drive (recursos gratis)
Modificar la función `getDriveUrl()` con la nueva URL codificada en base64.

### Agregar/cambiar productos en la tienda
Buscar el comentario `<!-- Tarjetas de productos -->` en `#tienda` y editar las tarjetas `<a>` con la nueva URL, imagen, nombre, descripción y precio.

### Cambiar el límite de usos gratuitos
Buscar `3 generaciones gratuitas` en el JS y ajustar la constante `MAX_USOS` (o la lógica equivalente). Coordinar con la validación server-side en el Apps Script.

### Actualizar el link del blog
Buscar `blog_5to_grado_firebase.html` en la sección `#blog-quinto` y reemplazar por el nombre correcto del archivo.

---

## 📄 Licencia

© 2026 **Profe Ani Edutech** — Todos los derechos reservados.
Hecho con 💜 para docentes que quieren enseñar mejor sin trabajar más horas.
