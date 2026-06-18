# Landing Page Captación — Adeslas Dental Max

Landing page optimizada para la generación de leads del seguro dental Adeslas Dental Max. Diseño premium, formulario multi-step con calculadora de precio en vivo, y cumplimiento RGPD completo.

## Stack técnico

- **Arquitectura:** HTML/CSS/JS vanilla en un solo archivo (`index.html`) — sin frameworks ni dependencias de build
- **Fuentes:** Sora (headings) + DM Sans (body) desde Google Fonts
- **Iconos:** Lucide (CDN, auto-inyectado como SVG)
- **Almacenamiento local:** Banner de cookies con persistencia en `localStorage`
- **Hosting:** Servible desde cualquier CDN, S3, Netlify, Vercel o servidor estático

## Decisiones de Growth & CRO

| Decisión | Por qué |
|---|---|
| **Single-file HTML** | Carga instantánea sin dependencias ni round-trips de build. Máxima portabilidad. |
| **Formulario multi-step** | Reduce la fricción percibida: paso 1 (nombre + email), paso 2 (teléfono + familiares). El usuario progresa sin sentir que está completando un formulario largo. |
| **Calculadora de precio en vivo** | Al seleccionar el número de asegurados se muestra el precio exacto. Reduce la incertidumbre financiera y cualifica el lead inmediatamente. |
| **Copy basado en análisis de oferta** | Titular, beneficios y FAQ extraídos del análisis real de la oferta oficial Adeslas Dental Max. Refleja con precisión: 49 tratamientos, sin carencias, sin cuestionario de salud. |
| **Micro-animaciones CSS** | Scroll reveal, fadeInUp, scaleIn. Dirigen la atención hacia el CTA y los beneficios clave sin depender de librerías JS. |
| **Contadores animados** | Las cifras (1.600+ odontólogos, 185+ clínicas) se animan al hacer scroll, reforzando la credibilidad. |
| **Checkbox de consentimiento RGPD** | En ambos formularios, obligatorio antes de enviar. Aviso de privacidad enlazado. |
| **Banner de cookies** | Con opciones "Aceptar" y "Rechazar". Persistencia en localStorage. |
| **API-ready** | Configura `API_ENDPOINT` en el JS y los leads se envían a tu API. Sin conexión, funciona en modo mock con logging. |
| **WhatsApp flotante** | Canal de conversación alternativo para leads que prefieren contacto instantáneo. |

## Estructura del proyecto

```
landing/
├── index.html             # Landing completa (~1390 líneas)
├── hero-bg.jpg            # Imagen de fondo del hero
├── legal/
│   ├── aviso-legal.html   # Aviso Legal (LSSI-CE)
│   ├── privacidad.html    # Política de Privacidad (RGPD + LOPDGDD)
│   └── cookies.html       # Política de Cookies (RGPD/ePrivacy)
└── README.md              # Este documento
```

## Secciones de la landing

1. **Header** — Logo + teléfono + CTA "Pide presupuesto". Sticky con glassmorphism.
2. **Hero** — Split layout: contenido left (badge, h1, subtítulo, feature pills) + form card right. Fondo con overlay degradado.
3. **Trust Bar** — Prueba social: "+50.000 familias", "4.5/5 Google", "Recomendado OCU".
4. **Coberturas** — 5 tarjetas con iconos Lucide: Diagnóstico, Prevención, Cirugía, Odontopediatría, Urgencias.
5. **Cómo funciona** — 3 pasos con números circulares y línea conectora. Fondo oscuro.
6. **Red de clínicas** — Contadores animados (1.600+ / 185+) + texto explicativo.
7. **Testimonios** — 3 tarjetas con avatar, nombre, ciudad y cita textual.
8. **FAQ** — Acordeón con 6 preguntas basadas en objeciones reales. Sin carencias, edad máxima, coberturas, etc.
9. **CTA Final** — Formulario compacto con título "Empieza a cuidar tu sonrisa hoy". Fondo oscuro con radial glow.
10. **Footer** — Enlaces a documentos legales, teléfono, copyright 2026.
11. **WhatsApp flotante** — Botón fixed con tooltip y animación pulse.
12. **Banner de cookies** — Barra inferior con persistencia en localStorage.

## Copywriting

El copy se extrajo del análisis detallado de la oferta oficial (`adeslas_dental_max_analisis.md`):

- **Propuesta de valor principal:** "desde 5 €/mes · 49 tratamientos sin coste · sin carencias"
- **Estructura de precios real:** 10 €/mes (1-2 personas), 5 €/mes (3+ personas)
- **Ventajas clave:** sin cuestionario de salud, sin edad máxima, sin períodos de carencia, cobertura desde el día 1
- **Red:** 1.600+ odontólogos, 185+ clínicas propias y concertadas
- **Público objetivo:** familias, parejas, usuarios que buscan solución dental asequible

## Documentos legales

Los tres documentos se adaptaron del Marco de Seguridad y Desarrollo Software (MSDS v1.1):

- **Aviso Legal:** responsable del sitio, propiedad intelectual, condiciones de uso, legislación aplicable
- **Política de Privacidad:** RGPD art. 13 — responsable, finalidad, base legal (consentimiento + relación precontractual), conservación (2 años leads, 5 años clientes), derechos ARSO+olvido+portabilidad, medidas de seguridad
- **Política de Cookies:** tabla de cookies, tipos, gestión en navegadores, consentimiento

## Diseño visual

- **Paleta:** Azul corporativo Adeslas (`#0057A8`) como primario, teal (`#00A896`) como acento, sobre fondos neutros (`#F8FAFC`) y oscuros (`#0F1923`)
- **Tipografía:** Sora para titulares (geométrica, premium) + DM Sans para cuerpo (limpia, legible)
- **Iconos:** Lucide — librería de iconos open-source con estilo de línea consistente. Carga asíncrona desde CDN con inicialización explícita.
- **Efectos:** Glassmorphism en form card, scroll-triggered reveals, shimmer en botones, animación de contadores, tooltip en WhatsApp
- **Responsive:** 2 breakpoints (1024px tablet, 767px móvil). Layout adaptativo en todas las secciones.

## SEO y rendimiento

- Meta viewport + charset declarados
- Etiqueta `<html lang="es">` para accesibilidad e indexación
- Google Fonts con `preconnect` y `display=swap`
- HTML semántico con `<header>`, `<section>`, `<footer>`, `<nav>`, `<main>`
- Atributos `aria-expanded` en FAQ, `aria-label` en botones, `required` y `pattern` en campos
- Tiempo de carga: ~79 KB total (todo incluido, sin contar hero-bg.jpg)

## Cómo usar

1. Abre `index.html` en el navegador para ver la landing.
2. Para conectar con una API real, edita `API_ENDPOINT` en el script (constante al inicio del JS).
3. Los formularios del hero (multi-step) y del CTA final envían datos al mismo endpoint.
4. Los leads incluyen: nombre, email, teléfono, número de familiares, precio calculado, timestamp y fuente.
5. Sin API configurada, los datos se registran en consola (modo mock).

## Despliegue

Al ser HTML estático, puedes desplegarlo en cualquier servicio:

```bash
# Ejemplo con Netlify CLI
netlify deploy --prod --dir=./landing

# Ejemplo con Vercel
vercel --prod ./landing
```

O simplemente copiar la carpeta `landing/` a cualquier servidor web estático (Apache, Nginx, S3, etc.).
