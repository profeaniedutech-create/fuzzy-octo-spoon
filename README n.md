# ✨ Profe Ani Edutech — Landing Page

> Sitio web oficial de **Profe Ani Edutech**: IA y recursos pedagógicos para docentes argentinos.  
> Hosteado en GitHub Pages · [profeaniedutech.com.ar](https://www.profeaniedutech.com.ar)

---

## 🗂️ Estructura del repositorio

```
/
├── index.html                        # Landing page principal
├── avatar.png                        # Avatar ilustrado (usado en previews de redes sociales)
├── fichas_interactivas_mundial2026.html   # Fichas del Mundial FIFA 2026 (recurso gratuito)
└── README.md
```

---

## 🚀 Secciones del sitio

| Sección | Descripción |
|---|---|
| **Generador de Prompts** | Genera prompts pedagógicos personalizados (Secuencia Didáctica, ABP, STEAM) según grado y tema |
| **Recursos Gratis** | Acceso a carpeta de Drive con Kit de Prompts y Guía + Plantillas |
| **Fichas del Mundial** | Actividades lúdicas interactivas para nivel inicial y primario |
| **Tienda** | Productos premium en Empretienda (Álbum Mundial, Kit Mundialista, Juegos) |
| **Sobre Mí** | Presentación de la Profe Ani |
| **Contacto** | Acceso directo a profenaiedutech@gmail.com |

---

## ⚙️ Stack técnico

| Tecnología | Uso |
|---|---|
| HTML5 + CSS3 | Estructura y estilos base |
| [Tailwind CSS v3.4.1](https://tailwindcss.com) | Utilidades de diseño (CDN fijo) |
| [Font Awesome 6.4](https://fontawesome.com) | Íconos |
| Google Fonts — Inter + Fredoka | Tipografías |
| Google Tag Manager (`GTM-PNP67S35`) | Analítica y seguimiento |
| Google Apps Script | Backend serverless para registro de usos en Google Sheets |
| ImgBB | Hosting de imagen de preview social |

---

## 🔌 Integraciones

### Google Apps Script (v5)
Endpoint serverless que conecta el formulario del Generador y el formulario de Recursos Gratis con dos Google Sheets independientes.

**Flujos disponibles:**

| `accion` | Destino | Columnas registradas |
|---|---|---|
| `consultar` | Hoja `GENERADOR DE IA` | Cuenta usos por email |
| `registrar` (generador) | Hoja `GENERADOR DE IA` | fecha · email · grado · tema · formato · tipo |
| `registrar` (recursos) | Hoja `RECURSOS GRATUITOS` | fecha · email · tipo |

### Google Tag Manager
Cargado en el `<head>` con el contenedor `GTM-PNP67S35`. Gestiona tags de analítica desde el panel de GTM sin modificar el código.

---

## 🔒 Seguridad y privacidad

- La URL del Apps Script está ofuscada con Base64 en el cliente. **La seguridad real vive en el script server-side**, que valida cada request.
- Los emails se registran exclusivamente para contabilizar el uso del generador gratuito, conforme a la **Ley 25.326 de Protección de Datos Personales** (Argentina).
- No se ceden ni comercializan datos a terceros.
- Los logs de debug (`console.log`, `console.warn`) están condicionados a `window.__DEBUG = true` y no se ejecutan en producción.

---

## 🛡️ Rate limiting del generador gratuito

El sistema usa una **estrategia de doble capa** para limitar a 3 generaciones gratuitas por email:

1. **`localStorage`** — verificación instantánea en el cliente (caché local).
2. **Google Sheets via Apps Script** — verificación robusta server-side que resiste borrado de caché.

El valor real es siempre el mayor entre ambas fuentes (`Math.max(local, servidor)`).

---

## 🖼️ SEO y redes sociales

```html
og:image       → https://i.ibb.co/MyscRPqq/1.png  (1200×1200)
og:locale      → es_AR
twitter:card   → summary_large_image
schema.org     → WebSite + Person
canonical      → https://www.profeaniedutech.com.ar
```

El avatar (`avatar.png`) está en el repositorio pero la imagen activa para previews es la alojada en ImgBB, garantizando compatibilidad con todos los scrapers (WhatsApp, Instagram, LinkedIn, Telegram).

---

## 🗃️ Archivos relacionados (externos al repo)

| Archivo | Descripción |
|---|---|
| `fichas_interactivas_mundial2026.html` | Fichas del Mundial — recurso gratuito sin registro |
| Google Drive (privado) | Carpeta con Kit de Prompts y Guía + Plantillas para descarga |
| Empretienda | Tienda con productos premium — [profeani.empretienda.com.ar](https://profeani.empretienda.com.ar) |

---

## 📬 Contacto

**Profe Ani Edutech**  
✉️ [profenaiedutech@gmail.com](mailto:profenaiedutech@gmail.com)  
📸 [@profeani.edutech](https://www.instagram.com/profeani.edutech/)  
▶️ [YouTube](https://www.youtube.com/@profeani.edutech)  
🎵 [TikTok](https://www.tiktok.com/@profeani.edutech)  
💬 [Comunidad WhatsApp](https://chat.whatsapp.com/JRJ2GajwmmWJJYvMglYzoo)

---

© 2026 Profe Ani Edutech — Todos los derechos reservados.  
*Hecho con 💜 para docentes que quieren enseñar mejor sin trabajar más horas.*
