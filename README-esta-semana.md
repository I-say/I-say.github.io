# README — Cómo actualizar "Esta Semana"

La sección **Esta Semana** aparece en la página principal (`index.html`) entre el hero y los eventos. Es la ventana que abres al inicio de cada clase de Excel para hablar 15–20 minutos de noticias y películas de la semana.

---

## Regla de oro: solo agrega, nunca borres

Cada volumen anterior queda guardado como historial. Los visitantes pueden navegar entre semanas pasadas usando las flechas **◀ ▶** que aparecen en la sección. Nunca elimines un volumen, solo agrega uno nuevo.

---

## Cómo agregar un nuevo volumen (cada semana)

### Paso 1 — Abre `index.html` con cualquier editor de texto

### Paso 2 — Busca esta línea (está cerca del inicio, dentro de `const ISAY`):

```javascript
semanas: [
```

### Paso 3 — Agrega el nuevo volumen al INICIO del array

Pega el siguiente bloque **después de `semanas: [`** y **antes del primer `{`** del volumen anterior. Asegúrate de que termine con una coma `,`:

```javascript
  /* ── VOL. 02 — Semana del DD de Mes de AAAA ── */
  {
    numero:   "Vol. 02",
    fecha:    "Semana del 23 de marzo de 2026",
    intro:    "Frase de apertura de la clase. Qué tuvo de especial esta semana.",
    noticias: [
      {
        titulo: "Título de la noticia 1",
        fuente: "Nombre del medio · DD Mes AAAA",
        desc:   "Una o dos oraciones resumiendo de qué trata y por qué te llamó la atención."
      },
      {
        titulo: "Título de la noticia 2",
        fuente: "Nombre del medio · DD Mes AAAA",
        desc:   "Resumen breve y por qué es relevante para los alumnos."
      },
      {
        titulo: "Título de la noticia 3",
        fuente: "Nombre del medio · DD Mes AAAA",
        desc:   "Resumen breve."
      }
    ],
    pelicula: {
      titulo: "Nombre de la película",
      año:    "2024",
      nota:   "Una o dos oraciones de tu opinión o de por qué la recomendás."
    }
  },
```

### Paso 4 — Guarda y sube el archivo a GitHub

El nuevo volumen aparecerá automáticamente como el actual (◀ 1 / N ▶). Los volúmenes anteriores quedan accesibles con la flecha ◀.

---

## Ejemplo: cómo queda el array con 3 semanas

```javascript
semanas: [

  /* ── VOL. 03 — más reciente (siempre al inicio) ── */
  {
    numero:   "Vol. 03",
    fecha:    "Semana del 6 de abril de 2026",
    intro:    "Semana intensa: IA generativa en la industria y un documental imperdible.",
    noticias: [
      {
        titulo: "OpenAI lanza GPT-5",
        fuente: "The Verge · 5 Abr 2026",
        desc:   "La nueva versión promete razonamiento mejorado y capacidades multimodales más potentes."
      },
      {
        titulo: "México sube al top 10 de países con más startups de IA",
        fuente: "Expansión · 4 Abr 2026",
        desc:   "GDL y CDMX concentran el 70% de las nuevas empresas de inteligencia artificial del país."
      },
      {
        titulo: "Excel ahora integra Copilot en todas las versiones de Office 365",
        fuente: "Microsoft Blog · 3 Abr 2026",
        desc:   "Puedes pedirle a Copilot que genere fórmulas y tablas dinámicas con lenguaje natural."
      }
    ],
    pelicula: {
      titulo: "iO (2023)",
      año:    "2023",
      nota:   "Documental sobre el estado actual de la IA. Corto y muy bien producido, ideal para abrir debate."
    }
  },

  /* ── VOL. 02 ── */
  {
    numero: "Vol. 02",
    // ...
  },

  /* ── VOL. 01 ── */
  {
    numero: "Vol. 01",
    // ...
  },

  /* ── VOL. 00 — plantilla inicial (no borrar) ── */
  {
    numero: "Vol. 00",
    // ...
  }
]
```

---

## Si no hay película esa semana

Cambia `pelicula: { ... }` por `pelicula: null` y el bloque de película no aparecerá:

```javascript
pelicula: null
```

---

## Si quieres más o menos de 3 noticias

Puedes poner 2 o 4 noticias en el array `noticias: []`. La página las muestra todas automáticamente.

---

## Navegación entre semanas en la página

La sección "Esta Semana" muestra siempre el volumen más reciente (índice 0 del array). Los botones funcionan así:

| Botón | Acción |
|-------|--------|
| ▶ (derecha) | Va al volumen siguiente (más nuevo) |
| ◀ (izquierda) | Va al volumen anterior (más antiguo) |
| Contador `2 / 5` | Muestra qué semana estás viendo del total |

---

*README actualizado: Marzo 2026*
