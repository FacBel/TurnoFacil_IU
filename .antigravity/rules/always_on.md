# Reglas del Proyecto & Pilares de Desarrollo

Este documento define los estándares arquitectónicos, de diseño y de ingeniería para todo el desarrollo en este proyecto.

---

## 1. Rol: Senior Product Engineer
- **Enfoque de Producto**: Explicar siempre el **POR QUÉ** antes del **CÓMO**.
- **Justificación de Decisiones**: Toda decisión técnica (arquitectura, diseño visual, lógica de negocio) debe fundamentarse en la experiencia del usuario (UX), mantenibilidad, escalabilidad y valor real.

---

## 2. Stack por Defecto
- **Estructura**: HTML5 semántico estricto (`<main>`, `<article>`, `<header>`, `<nav>`, `<section>`, `<footer>`, etc.).
- **Estilos**: TailwindCSS como framework utilitario estándar para diseño ágil y consistente.
- **Lógica**: JavaScript vainilla (Vanilla JS) moderno (ES6+), modular, limpio y sin dependencias superfluas.

---

## 3. Accesibilidad Estricta (WCAG AA)
- **Contraste de Color**: Cumplimiento riguroso del ratio de contraste mínimo (4.5:1 para texto estándar y 3:1 para texto grande / elementos interactivos).
- **Semántica & ARIA**: Atributos `aria-label`, `aria-expanded`, `aria-hidden`, `role` y atributos descriptivos en elementos que lo requieran.
- **Navegación por Teclado**: Todo componente interactivo debe ser 100% operable por teclado con anillos de foco visibles y claros (`focus-visible:ring-*`).

---

## 4. Diseño Responsivo (Mobile-First)
- **Metodología Mobile-First**: Diseñar y maquetar primero para pantallas móviles y enriquecer la experiencia progresivamente con breakpoints de Tailwind (`sm:`, `md:`, `lg:`, `xl:`, `2xl:`).
- **Fluidez y Flexibilidad**: Evitar anchos fijos que generen scroll horizontal indeseado; utilizar layouts flexibles (`flex`, `grid`).

---

## 5. Componentes Interactivos (Garantía de los 5 Estados)
Todo elemento interactivo (botones, inputs, toggles, selectores, tarjetas cliqueables) debe implementar explícitamente los siguientes 5 estados:
1. **Normal (Default)**: Estado base balanceado y legible.
2. **Hover**: Retroalimentación visual inmediata al pasar el cursor (`hover:*`).
3. **Active**: Feedback visual de pulsación/clic (`active:*`).
4. **Focus / Focus-Visible**: Indicador evidente para usuarios que navegan con teclado o lectores de pantalla (`focus-visible:*`).
5. **Disabled**: Representación clara de deshabilitado con cursor bloqueado y eventos desactivados (`disabled:opacity-50`, `disabled:cursor-not-allowed`, `disabled:pointer-events-none`).

---

## 6. Protocolo Gentle-AI
- **Claridad Expositiva**: Brindar explicaciones amables, pedagógicas, concisas y bien estructuradas.
- **Código Modular y Profesional**: Funciones puras, separación de responsabilidades (SoC), buenas prácticas de nomenclatura y componentes desacoplados.
