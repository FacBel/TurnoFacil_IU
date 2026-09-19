---
name: accessibility-audit
description: >-
  Auditoría y verificación continua de accesibilidad digital conforme a las pautas WCAG 2.1 Nivel AA. Úsalo para validar ratios de contraste, atributos ARIA, navegación total por teclado y accesibilidad táctil.
---

# Skill: Auditoría de Accesibilidad Digital (WCAG 2.1 AA)

Esta habilidad asegura que todas las interfaces creadas sean 100% inclusivas, accesibles para personas con discapacidades y compatibles con tecnologías asistivas.

---

## 1. Reglas de Contraste de Color (WCAG AA)
- **Texto Normal (< 18pt / 24px regular)**: Ratio mínimo de **4.5:1** contra su fondo inmediato.
- **Texto Grande (≥ 18pt o ≥ 14pt bold)**: Ratio mínimo de **3.0:1**.
- **Componentes de Interfaz y Gráficos (Botones, Bordes de Inputs, Iconos esenciales)**: Ratio mínimo de **3.0:1**.

---

## 2. Navegabilidad por Teclado y Foco Visible
- Todos los elementos interactivos deben poder alcanzarse secuencialmente usando `Tab` y `Shift+Tab`.
- **Foco Visible Innegociable**: No remover jamás el outline sin un reemplazo claro. Utilizar clases como:
  ```html
  class="focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-purple-400 focus-visible:ring-offset-2 focus-visible:ring-offset-slate-900"
  ```
- **Orden de Tabulación Lógico**: El orden del foco debe coincidir exactamente con el flujo visual del contenido.

---

## 3. Semántica ARIA y Formularios Accesibles
- Cada `<input>`, `<select>` y `<textarea>` debe contar con un `<label>` explícito asociado mediante `for="id"`.
- Los botones que solo contienen iconos deben incorporar `aria-label="Descripción de la acción"`.
- Los iconos decorativos deben incluir `aria-hidden="true"`.
- Estados dinámicos de selección deben reflejarse mediante `aria-pressed="true|false"` o `aria-selected="true|false"`.

---

## 4. Ergonomía y Objetivos Táctiles
- Dimensiones mínimas de toque en móviles de **44 × 44 píxeles** (`min-h-[44px] min-w-[44px]`).
- Espaciado adecuado entre botones adyacentes para prevenir pulsaciones accidentales.
