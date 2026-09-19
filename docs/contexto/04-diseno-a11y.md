# Master Context Vivo: 04. Sistema de Diseño y Accesibilidad (A11y)

## 1. Identidad Visual: Tema Oscuro Grafito & Púrpura

El sistema visual de **TurnoFácil** implementa un diseño *Dark Theme* moderno, sofisticado y de alto contraste que transmite profesionalismo y elegancia tecnológica.

### Paleta de Colores y Tokens:
- **Fondo Primario (`--bg-body`)**: `#09070f` (Grafito ultra-oscuro con matiz azulino/púrpura).
- **Superficie de Tarjetas (`--card-bg`)**: `rgba(18, 14, 30, 0.85)` con `backdrop-filter: blur(16px)`.
- **Bordes y Delimitadores (`--border-subtle`)**: `rgba(168, 85, 247, 0.20)`.
- **Acento Primario (Gradiente Violeta)**: `linear-gradient(135deg, #7c3aed 0%, #a855f7 50%, #ec4899 100%)`.
- **Acento Secundario (Hover/Glow)**: `#c084fc` / `rgba(168, 85, 247, 0.4)`.
- **Texto Principal (`--text-primary`)**: `#f8fafc` (Blanco cálido de alto contraste).
- **Texto Secundario (`--text-secondary`)**: `#cbd5e1` (Gris claro legible).
- **Texto Deshabilitado / Muted (`--text-muted`)**: `#94a3b8` / `#64748b`.
- **Estado de Éxito / Online**: `#10b981` (Verde esmeralda).

---

## 2. Normas de Accesibilidad Estricta (WCAG 2.1 Nivel AA)

### A. Ratios de Contraste de Color:
- **Texto Estándar**: Mínimo **4.5:1** contra el fondo circundante.
- **Texto Grande (≥ 18pt / 24px) y Elementos de Interfaz (Botones, Bordes)**: Mínimo **3.0:1**.

### B. Navegación Total por Teclado:
- Todos los elementos interactivos (tarjetas de servicio, slots de hora, botones) son operables vía `Tab`, `Shift+Tab`, `Space` y `Enter`.
- Anillos de foco visibles obligatorios en elementos enfocados: `focus-visible:ring-2 focus-visible:ring-purple-400 focus-visible:outline-none`.

### C. Semántica y Atributos ARIA:
- Uso estricto de etiquetas semánticas: `<main>`, `<nav>`, `<header>`, `<article>`, `<section>`, `<fieldset>`, `<legend>`.
- Atributos `aria-pressed`, `aria-expanded`, `aria-selected` y `aria-label` descriptivos en botones con iconos.

---

## 3. Garantía de los 5 Estados en Componentes Interactivos

Cada botón, selector, input y tarjeta interactiva debe implementar de forma visible sus 5 estados:

```
┌──────────────┬────────────────────────────────────────────────────────┐
│ Estado       │ Comportamiento Visual & Técnico                        │
├──────────────┼────────────────────────────────────────────────────────┤
│ 1. Normal    │ Apariencia base con contraste balanceado y legible.    │
│ 2. Hover     │ Brillo violeta sutil, elevación (`translate-y-0.5`).  │
│ 3. Active    │ Sensación de pulsación física (`scale-98`).            │
│ 4. Focus     │ Anillo de foco accesible (`focus-visible:ring-2`).     │
│ 5. Disabled  │ Opacidad reducida (50%), cursor `not-allowed`.         │
└──────────────┴────────────────────────────────────────────────────────┘
```

---

## 4. Principios Mobile-First & Ergonomía Táctil
- **Áreas Táctiles Mínimas**: Dimensiones de interacción de al menos `44px × 44px` para evitar clics erróneos en smartphones.
- **Layouts Flexibles**: Grid y Flexbox sin valores fijos en píxeles que ocasionen scroll horizontal indeseado.
