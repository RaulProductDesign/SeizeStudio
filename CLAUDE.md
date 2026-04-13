# Seize Studio · Contexto del proyecto

## Qué es Seize Studio

Seize Studio es un proyecto de café de especialidad en Cuenca (España). No es una cafetería al uso: es un espacio en el casco antiguo dedicado a experiencias en torno al café — catas guiadas, talleres de preparación y charlas con productores y tostadores. Grupos pequeños, formato íntimo.

El nombre viene de Seize, la ciudad ficticia del anime *Sora no Woto*, inspirada en Cuenca. "Studio" ancla el concepto: no es un bar, es un espacio de aprendizaje y experiencia compartida.

**Misión:** Acercar el café de especialidad a Cuenca a través de experiencias cercanas e íntimas.

---

## Estado actual del proyecto

Estamos en fase de **validación**. El objetivo es comprobar si hay público en Cuenca antes de abrir. Para eso hemos construido una landing page cuyo único objetivo es recoger correos electrónicos de personas interesadas.

La landing está en `seize_landing.html`. El repositorio está en https://github.com/RaulProductDesign/SeizeStudio.

---

## La landing

### Estructura de secciones

1. **Hero** — Eyebrow "Seize Studio · Cuenca · 2026", tagline grande en cursiva ("Curiosos del café, / bienvenidos."), ornamento `— ✦ —`, CTA que baja al formulario
2. **El proyecto** — Intro del concepto + tres experiencias en cards con imagen placeholder (talleres tiene imagen de Unsplash)
3. **Formulario** — Lista de espera para la primera cata, conectado a Google Apps Script
4. **Footer** — Logo, Instagram (pendiente de enlazar), política de privacidad

### Decisiones de diseño tomadas en sesión

- El logo "Seize / Studio" fue eliminado del hero. Solo existe en la nav y el footer
- La tagline "Curiosos del café, bienvenidos." es el elemento dominante del hero: Playfair Display italic, `clamp(48px, 7vw, 80px)`, "bienvenidos." en color `--amber`
- El ornamento `— ✦ —` separa la tagline del CTA
- Se eliminó el bloque `.hero-scroll` (línea animada de scroll)
- El eyebrow del hero incluye "Seize Studio": `"Seize Studio · Cuenca · 2026"`
- Max-width de secciones subido a `1200px` (antes `860px`)
- Base font-size subida a `17px`; todos los textos escalados proporcionalmente
- El mensaje de éxito del formulario usa DM Sans 300 (antes IM Fell English italic — poca legibilidad)
- Las tres cards de experiencias tienen imagen real de Unsplash (CDN directo, `background-size: cover`)
- Instagram enlazado: `https://www.instagram.com/seize.estudio/`
- Página de privacidad creada en `privacidad.html`, enlazada desde el footer de ambas páginas
- Animación de carga en el botón del formulario: tres puntos con `dot-pulse`, el mensaje de confirmación aparece cuando el fetch resuelve

### Copy clave

**Hero tagline:** "Curiosos del café, / bienvenidos." (salto de línea tras la coma)

**Intro del proyecto:**
> Seize Studio es un espacio en el casco antiguo de Cuenca dedicado a las experiencias en torno al café. Catas guiadas, talleres de preparación y charlas con productores y tostadores.

**Las tres experiencias:**

- **Catas** — Nos sentamos, probamos y prestamos atención. Sin prisa, sin jerga. Solo café bueno y ganas de entender qué tiene de especial lo que hay en la taza.
- **Talleres** — Aprender haciendo. Desde cómo preparar un café en casa hasta entender por qué el tuyo no sabe como el de tu cafetería favorita. Nos manchamos las manos juntos.
- **Charlas** — Invitamos a gente que sabe: tostadores, productores, baristas con historia. Sin ponencias, sin PowerPoints. Una conversación de verdad sobre café con alguien que vive de ello.

**Formulario:**
- Eyebrow: "Primera cata"
- Título: "Apúntate a la lista de espera."
- Descripción: "Estamos preparando nuestra primera cata. Cuando tengamos fecha, precio y todos los detalles, serás el primero en saberlo. Deja tu correo y te avisamos."
- CTA: "Quiero saber más"
- Success: "¡Apuntado! Te avisamos cuando tengamos todos los detalles."
- Nota legal: "Al enviar tu correo aceptas que Seize lo use para informarte sobre este evento. Puedes darte de baja en cualquier momento escribiéndonos directamente."

---

## Guía de marca (resumen técnico)

El archivo completo es `seize_estudio_manual_de_marca.html`. Aquí el resumen para uso en código.

### Paleta de color

```css
--dark:   #2A1F0E;   /* Fondo principal oscuro */
--rust:   #8B4A20;   /* Acento, bordes, eyebrows */
--amber:  #C07A40;   /* Ornamentos, CTAs, ✦, "bienvenidos." en hero */
--kraft:  #D4B896;   /* Hover states */
--sepia:  #C8B89A;   /* Bordes suaves, divisores */
--cream:  #F5EFE0;   /* Texto sobre oscuro, fondos de card */
--cream2: #EDE5D0;   /* Fondos secundarios */
--light:  #FAF6ED;   /* Fondo general de página */
--mid:    #9A8A70;   /* Texto secundario, labels */
--body:   #4A3A28;   /* Texto de cuerpo */
```

### Tipografías

```html
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,700;1,400;1,700&family=IM+Fell+English:ital@0;1&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
```

| Tipografía | Uso |
|---|---|
| Playfair Display 700 | Títulos, nombres de experiencia |
| Playfair Display italic | Hero tagline (grande), títulos secundarios en cursiva |
| IM Fell English italic | Ornamentos (— ✦ —) |
| DM Sans 300 | Cuerpo de texto, mensaje de éxito del formulario |
| DM Sans 500 + uppercase + letter-spacing | Labels, eyebrows, CTAs |

### Elementos de marca recurrentes

- **Ornamento:** `— ✦ —` en IM Fell English, color `--amber`
- **Diamante separador:** `div` 5–7px rotado 45°, color `--rust`
- **Regla con diamante:** línea `--rust` + diamante central (ver `.hero-rule-wrap`)
- **Eyebrow de sección:** 11px, `letter-spacing: 0.2em`, uppercase, color `--rust`
- **Fondo con grid sutil:** `repeating-linear-gradient` en `rgba(200,184,154,0.03–0.04)` cada 40px, usado en hero y formulario
- **Border-radius:** prácticamente 0 en cards (2px máximo). El espacio es austero, no redondeado

### Tono de voz

- Cercano pero no informal
- Sin jerga de specialty coffee cuando se habla al público general
- Frases cortas. Sin relleno
- Primera persona del plural ("nos sentamos", "nos manchamos las manos")
- Sin signos de exclamación salvo en el mensaje de confirmación

---

## Stack técnico de la landing

- HTML + CSS + JS vanilla. Sin frameworks
- Fuentes vía Google Fonts
- Favicons en `files/`: `favicon.svg`, `favicon-32.png`, `favicon-180.png`, `favicon.ico`
- Formulario: POST a Google Apps Script → escribe en Google Sheets

### Endpoint del formulario

```
https://script.google.com/macros/s/AKfycbw1Zmp_3w3cQ4QQZuvQdS0UyJ5gfHDpecgZdH-Qqd88NFovMms6Gm9LFvQD_1xjA4-yAA/exec
```

- method: POST
- mode: no-cors
- Content-Type: application/x-www-form-urlencoded
- body: `email=<valor>`

En caso de éxito oculta `#form-wrap` y muestra `#successMsg`. En error muestra `alert()`.

---

## Pendientes

- [ ] Foto real del espacio para el hero (sustituir `.hero-img-placeholder`)
- [ ] Hosting (GitHub Pages o Netlify recomendado — gratuito)
- [ ] Animaciones de entrada (scroll reveal en secciones, fade-in hero)
