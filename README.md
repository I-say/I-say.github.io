# isay.github.io — Guía de edición del sitio

Sitio personal de **Miguel Isay Morales Cortes** · Data Science · GDL 🇲🇽

---

## ⚠️ Regla principal: nunca borres, solo agrega

Este sitio está diseñado para acumular historial. Los eventos pasados, volúmenes de "Esta Semana" y clases antiguas son antecedentes valiosos. **Agrega siempre al inicio o al final del array correspondiente, nunca reemplaces ni elimines entradas anteriores.**

---

## Arquitectura del sitio

```
I-say.github.io/
├── index.html              ← Página principal (contenido editable en const ISAY)
├── nvidia-dli/
│   └── index.html          ← Portal del curso NVIDIA DLI
├── taller-excel/
│   ├── index.html          ← Hub del taller (lista de clases)
│   ├── clase-0.html        ← Clase 0: Bienvenida (placeholder)
│   └── clase-1.html        ← Clase 1: Lógica de Excel
└── img/
    └── profile.jpg         ← Foto de perfil
```

**Principio de diseño:** todo el contenido del `index.html` vive en el objeto `const ISAY = { ... }` al inicio del archivo. El motor de render debajo de ese objeto **no se toca**.

---

## Cómo editar el index.html

Abre `index.html` con cualquier editor (VS Code, Notepad++, etc.) y busca:

```javascript
const ISAY = {
```

Todo lo que está dentro de ese bloque es editable. Lo que está debajo de:

```javascript
}; /* ← fin de la zona editable */
```

**no se modifica.**

---

## Agregar un nuevo evento o actividad

Busca el array `eventos:` dentro de ISAY. **Copia el bloque siguiente y pégalo al inicio del array** (antes del primer `{`), seguido de coma:

```javascript
{
  tipo:        "evento",    // "evento" | "logro" | "taller"
  destacado:   false,       // true = tarjeta grande con stats
  icono:       "🎯",
  titulo:      "Nombre del evento",
  fecha:       "2026",
  lugar:       "Lugar del evento",
  descripcion: "Descripción breve del evento y tu rol en él.",
  roles:       ["Tu rol 1", "Tu rol 2"],
  link:        "",          // URL a la página del evento, o "" si no hay
  link_texto:  "Ver más",
  stats:       []           // [{num:"250", label:"Lugares"}] o [] si no hay
},
```

**No borres eventos anteriores.** El historial completo debe permanecer visible.

---

## Agregar un nuevo proyecto

Busca el array `proyectos:` y agrega al inicio:

```javascript
{
  icono:       "🔧",
  titulo:      "Nombre del proyecto",
  org:         "Organización · Año–Presente",
  descripcion: "Qué hace el proyecto y cuál es tu rol.",
  tags:        ["Tag1", "Tag2", "Tag3"],
  link:        ""
},
```

---

## Agregar una nueva entrada a la trayectoria

Busca el array `trayectoria:` y agrega al inicio:

```javascript
{ fecha: "2026–hoy", titulo: "Título del rol", org: "Organización", icono: "🎓" },
```

---

## Actualizar "Esta Semana"

Ver el archivo [`README-esta-semana.md`](README-esta-semana.md) para instrucciones completas.

**Resumen:** agrega un nuevo objeto al **inicio** del array `semanas:` en `index.html`. Los volúmenes anteriores se conservan y son navegables con las flechas ◀ ▶ en la página.

---

## Agregar una nueva clase al Taller de Excel

### 1. Crea el archivo de la clase

Duplica `taller-excel/clase-1.html` y renómbralo (ej. `clase-2.html`). Edita el contenido manteniendo la misma estructura HTML.

### 2. Agrégala al hub

Abre `taller-excel/index.html` y dentro de `<div class="clases-grid">` agrega:

```html
<a href="clase-2.html" class="clase-card">
  <div class="clase-num">Clase 2</div>
  <div class="clase-titulo">Nombre de la clase</div>
  <p class="clase-desc">Descripción breve de lo que se cubre.</p>
  <div class="clase-temas">
    <span class="clase-tema">Tema 1</span>
    <span class="clase-tema">Tema 2</span>
  </div>
  <div class="clase-arrow"><i class="fas fa-arrow-right"></i> Ver clase</div>
</a>
```

Convierte el placeholder correspondiente a tarjeta activa, o agrégala al final.

### 3. Actualiza el sidebar de las clases anteriores

En el sidebar de `clase-1.html` (y clases posteriores), agrega el link a la nueva clase en la lista de navegación.

---

## Actualizar la foto de perfil

Sube tu nueva foto como `img/profile.jpg` en el repositorio. El sitio la carga automáticamente.

---

## Desplegar cambios en GitHub

1. Ve a tu repositorio: `github.com/I-say/I-say.github.io`
2. Navega al archivo que quieres editar
3. Clic en el ícono ✏️ para editar, o arrastra los archivos nuevos a la carpeta correcta
4. Al guardar → **"Commit directly to the `main` branch"**
5. GitHub Pages despliega los cambios en 1–2 minutos automáticamente

---

## Paleta de colores y tipografía

| Variable    | Valor     | Uso                        |
|-------------|-----------|----------------------------|
| `--ink`     | `#0e0d0b` | Texto principal, fondos dark |
| `--paper`   | `#f5f0e8` | Fondo principal            |
| `--gold`    | `#b8860b` | Acentos, bordes destacados |
| `--gold-lt` | `#d4a843` | Dorado claro               |
| `--muted`   | `#7a7060` | Texto secundario           |
| `--teal`    | `#1a7a68` | Info, detalles positivos   |
| `--red`     | `#8b1a1a` | Alertas, énfasis           |
| `--excel`   | `#217346` | Identidad del Taller Excel |

Tipografías: **Playfair Display** (títulos) · **Inter** (cuerpo) · **JetBrains Mono** (código/fechas)

---

*README actualizado: Marzo 2026*
