# Profe Ani Edutech — Landing Page

Sitio web personal de **Profe Ani Edutech**, plataforma de recursos pedagógicos con IA para docentes de nivel inicial, primario y secundario.

🌐 **URL:** [www.profeaniedutech.com.ar](https://www.profeaniedutech.com.ar)
🏠 **Hosting:** GitHub Pages

---

## 📁 Archivos del proyecto

| Archivo | Descripción |
|---|---|
| `index.html` | Landing page principal |
| `fichas_interactivas_mundial2026.html` | Fichas interactivas del Mundial 2026 |
| `blog_5to_grado_firebase.html` | Blog escolar del 5° Grado Hugo Leonelli |

> ⚠️ Los tres archivos deben estar en la **misma carpeta/rama** del repositorio para que los links internos funcionen correctamente.

---

## 🗂️ Estructura de secciones

| ID | Sección | Descripción |
|---|---|---|
| — | Hero / Header | Título animado, subtítulo y botones de acceso rápido |
| — | Beneficios | 4 cards: Ahorra Tiempo, Prompts IA, Innovación, Menos Estrés |
| `#generador` | Generador de Prompts | Genera prompts pedagógicos listos para usar en IA |
| `#recursos-gratis` | Pack Gratuito | Formulario para acceder al Kit de Prompts + Guía |
| `#fichas` | Fichas Mundial 2026 | Enlace a `fichas_interactivas_mundial2026.html` |
| `#blog-quinto` | Blog de 5° Grado | Enlace a `blog_5to_grado_firebase.html` |
| `#tienda` | Tienda Premium | 3 productos destacados + botón a la tienda completa |
| `#sobre-mi` | Sobre Mí | Presentación y bio de la Profe Ani |
| — | Footer | WhatsApp, redes sociales, política de privacidad |

---

## ⚙️ Tecnologías utilizadas

| Tecnología | Uso |
|---|---|
| HTML5 / CSS3 | Estructura y estilos base |
| Tailwind CSS (CDN) | Utilidades de diseño responsivo |
| Font Awesome 6.4 | Iconografía |
| Google Fonts — Inter + Fredoka | Tipografías |
| Google Tag Manager (`GTM-PNP67S35`) | Analítica y seguimiento |
| Google Apps Script | Backend: registro y consulta de usos vía GET |
| Google Sheets | Base de datos de registros |
| Google Drive | Almacenamiento de recursos gratuitos |
| `localStorage` | Control local del límite de usos del generador |
| Schema.org (JSON-LD) | SEO estructurado (tipo: Person) |

---

## 🔗 Integraciones externas

### Apps Script (backend)
**URL del deploy:**
```
https://script.google.com/macros/s/AKfycbyk00zIPh0Z6GgtVAWxe0LSZoVtBZu2q90rnlD00W971iKW_QMFN-7gr60ZAmHk2Gcv/exec
```
La URL está ofuscada en base64 dentro de la función `getSU()` en el `<head>` del HTML.

**Endpoints disponibles:**
| Parámetro | Acción |
|---|---|
| `accion=consultar&email=xxx` | Devuelve `{ usos: N }` para ese email |
| `accion=registrar&sheetName=GENERADOR DE IA&...` | Guarda un uso del generador |
| `accion=registrar&sheetName=RECURSOS GRATUITOS&...` | Guarda un registro de descarga |
| *(sin params)* | Health check — devuelve `{ status: ok, message: "Script activo v5" }` |

### Google Sheets
| Planilla | ID | Hoja |
|---|---|---|
| Generador IA | `1xQZe3IJ6DxadZhtYJf7iO_YLv0QIIfipM9nNWcQ7_fM` | `GENERADOR DE IA` |
| Recursos Gratuitos | `1oOIfXnxzR-vV0wiUmAVmwsseRh5DF_IISdKf1Z4Bo6I` | `RECURSOS GRATUITOS` |

### Google Drive (recursos gratuitos)
```
https://drive.google.com/drive/folders/1mDLV4y7jvr0A_I5xwRlrazBVQJxmbYIA?usp=sharing
```
La URL está ofuscada en base64 dentro de la función `getDriveUrl()`.

---

## 🎯 Generador de Prompts Pedagógicos

### Flujo de uso
1. El docente ingresa su **correo electrónico**
2. Selecciona el **grado/nivel**
3. Escribe el **tema** (máx. 500 caracteres)
4. Elige el **formato**: Secuencia Didáctica / Proyecto ABP / Experiencia STEAM
5. El prompt se genera localmente y se muestra al instante
6. El uso se registra en Google Sheets vía Apps Script (GET con parámetros)

### Sistema de límites
- Cada correo tiene **3 generaciones gratuitas**
- Control doble: `localStorage` (cliente) + Apps Script (servidor)
- Al alcanzar el límite se bloquea con link a la Tienda Premium

### Anti-spam
Ambos formularios incluyen un **campo honeypot** oculto que descarta bots.

---

## 💎 Tienda — Productos destacados

| Producto | Precio | URL |
|---|---|---|
| Álbum Mundial 2026 — Archivo Editable | $5.000 ARS | [Ver producto](https://profeani.empretienda.com.ar/plantillas-listas-para-imprimir/album-mundial-2026-archivo-editable) |
| Kit Mundialista 2026 ⭐ | $3.000 ARS | [Ver producto](https://profeani.empretienda.com.ar/plantillas-listas-para-imprimir/kit-mundialista-2026) |
| Juegos Mundialistas | $3.000 ARS | [Ver producto](https://profeani.empretienda.com.ar/plantillas-listas-para-imprimir/juegos-mundialistas) |

Las imágenes se sirven desde el CDN de empretienda (`d22fxaf9t8d39k.cloudfront.net`). Cada tarjeta es un `<a>` clickeable completo que abre el producto en nueva pestaña.

---

## 🌐 SEO y metadatos

- `<title>` y `<meta description>` configurados
- Open Graph completo para Facebook/LinkedIn
- Twitter Cards (`summary_large_image`)
- `<link rel="canonical">` → `https://www.profeaniedutech.com.ar`
- `<meta name="robots" content="index, follow">`
- Schema.org JSON-LD tipo `Person` con `sameAs` a Instagram, YouTube y TikTok
- Favicon SVG inline

---

## 📱 Diseño responsivo

- Desktop: navegación horizontal, grids de 3-4 columnas
- Mobile: menú hamburguesa con animación X, grids de 1-2 columnas
- Floating CTA que aparece al hacer scroll más allá del hero
- Toast notifications para feedback de acciones

---

## 🔐 Seguridad y privacidad

- URLs del Apps Script y Google Drive **ofuscadas en base64** (`getSU()` y `getDriveUrl()`)
- Datos tratados conforme a la **Ley 25.326** de Protección de Datos Personales (Argentina)
- No se ceden ni comercializan datos a terceros

---

## 🛠️ Guía de mantenimiento

### Actualizar la URL del Apps Script
1. En el `<head>` del HTML, ubicar la función `getSU()`
2. Codificar la nueva URL en base64 y fragmentarla en partes
3. Reemplazar el array `p` con los nuevos fragmentos
4. En el Apps Script: **Implementar → Administrar implementaciones → Nueva versión → Implementar**
5. Configurar: *Ejecutar como: Yo · Quién tiene acceso: Cualquier persona*

### Actualizar la URL del Drive
Modificar `getDriveUrl()` con la nueva URL codificada en base64.

### Agregar/cambiar productos en la tienda
Buscar `<!-- Tarjetas de productos -->` en `#tienda` y editar las tarjetas `<a>` con URL, imagen, nombre, descripción y precio.

### Cambiar el límite de usos gratuitos
Ajustar la constante en el JS del generador y coordinar con la validación server-side en el Apps Script.

### Actualizar nombre del archivo del blog
Buscar `blog_5to_grado_firebase.html` en la sección `#blog-quinto` y reemplazar por el nombre correcto.

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

## 📄 Licencia

© 2026 **Profe Ani Edutech** — Todos los derechos reservados.
Hecho con 💜 para docentes que quieren enseñar mejor sin trabajar más horas.
