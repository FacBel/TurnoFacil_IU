---
name: interactive-components-5states
description: >-
  Estándar y generador de componentes interactivos con garantía total de los 5 estados visuales (Default, Hover, Active, Focus/Focus-Visible y Disabled). Úsalo para diseñar botones, selectores, tarjetas cliqueables y campos de formulario.
---

# Skill: Componentes Interactivos con Garantía de los 5 Estados

Esta habilidad estandariza la creación de componentes de interfaz que brinden retroalimentación táctil y visual inequívoca en todos sus estados de ciclo de vida.

---

## 1. La Matriz de los 5 Estados

Todo componente interactivo debe implementar explícitamente:

| # | Estado | Utilidades Tailwind Representativas | Propósito UX |
| :-: | :--- | :--- | :--- |
| **1** | **Normal (Default)** | `bg-gradient-to-r from-purple-600 to-pink-500 text-white font-medium` | Legibilidad clara, contraste WCAG y propósito evidente. |
| **2** | **Hover** | `hover:from-purple-500 hover:to-pink-400 hover:shadow-lg hover:-translate-y-0.5` | Feedback inmediato al colocar el cursor encima. |
| **3** | **Active** | `active:scale-[0.98] active:brightness-95` | Sensación física de compresión/pulsación al hacer clic. |
| **4** | **Focus / Focus-Visible** | `focus-visible:ring-2 focus-visible:ring-purple-400 focus-visible:ring-offset-2` | Indicador claro para usuarios de teclado o accesibilidad. |
| **5** | **Disabled** | `disabled:opacity-50 disabled:cursor-not-allowed disabled:pointer-events-none` | Comunicación no ambigua de bloqueo o indisponibilidad. |

---

## 2. Implementación de Referencia (Botón Primario Accesible)

```html
<button 
  type="button"
  class="relative inline-flex items-center justify-center gap-2 px-6 py-3 rounded-xl font-semibold text-white bg-gradient-to-r from-purple-600 to-pink-600 shadow-md shadow-purple-900/30 transition-all duration-200 ease-out
         hover:from-purple-500 hover:to-pink-500 hover:shadow-lg hover:shadow-purple-700/50 hover:-translate-y-0.5
         active:scale-[0.98] active:shadow-sm
         focus:outline-none focus-visible:ring-2 focus-visible:ring-purple-400 focus-visible:ring-offset-2 focus-visible:ring-offset-slate-950
         disabled:opacity-50 disabled:cursor-not-allowed disabled:pointer-events-none disabled:shadow-none"
  aria-label="Confirmar reserva de turno"
>
  <span>Confirmar Turno</span>
  <svg class="w-5 h-5 transition-transform duration-200 group-hover:translate-x-1" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
  </svg>
</button>
```

---

## 3. Tarjetas Seleccionables y Slots de Horario
Para elementos como tarjetas de servicio o botones de horario que alternan estado de selección:
- Incorporar `data-selected="true|false"` y `aria-pressed="true|false"`.
- Aplicar estilos diferenciados cuando está seleccionado (`ring-2 ring-purple-400 bg-purple-950/40`).
- Aplicar `disabled:opacity-40 disabled:line-through` en horarios ya reservados.
