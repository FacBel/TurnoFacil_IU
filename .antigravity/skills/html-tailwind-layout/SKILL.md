---
name: html-tailwind-layout
description: >-
  Especialidad en maquetación frontend estructurada con HTML5 semántico y diseño responsivo Mobile-First utilizando TailwindCSS. Úsalo para crear vistas, layouts fluidos y estructuras limpias sin dependencias de backend.
---

# Skill: Maquetado HTML5 Semántico & TailwindCSS Mobile-First

Esta habilidad guía la creación de estructuras web limpias, accesibles y altamente eficientes siguiendo los estándares de diseño moderno.

---

## 1. Principios de HTML5 Semántico
- **Estructuración jerárquica**:
  - Utilizar `<header>` para encabezados de página o de sección.
  - `<nav>` para bloques de navegación principal o breadcrumbs.
  - `<main>` para el contenedor principal de la vista (único por documento).
  - `<article>` para entidades autónomas e independientes (ej. tarjetas de servicio, reviews).
  - `<section>` con su correspondiente encabezado (`<h2>`-`<h6>`) para agrupar contenido temático.
  - `<footer>` para información de cierre, créditos y enlaces secundarios.
  - `<fieldset>` y `<legend>` para agrupar controles de formulario relacionados (ej. selector de horarios).

---

## 2. Metodología Responsive Mobile-First con TailwindCSS
- **Diseño Base**: Escribir siempre los estilos por defecto pensando en pantallas móviles (`360px` - `480px`).
- **Escalado Progresivo**: Aplicar utilidades de Tailwind con prefijos de breakpoint:
  - `sm:` (≥ 640px) - Tablets pequeñas / móviles apaisados.
  - `md:` (≥ 768px) - Tablets y pantallas medianas.
  - `lg:` (≥ 1024px) - Laptops y pantallas de escritorio estándar.
  - `xl:` (≥ 1280px) - Monitores amplios.
- **Evitar Anchos Fijos**: Usar `w-full`, `max-w-*`, `flex`, `grid`, `gap-*` para garantizar fluidez sin scroll horizontal.

---

## 3. Poda y Alcance del MVP
- ❌ **No incluir**: Motores de plantillas de servidor pesados (Blade, Pug, EJS con backend), frameworks fullstack (Next.js/Nuxt) ni dependencias de compilación complejas.
- ✅ **Incluir**: HTML5 nativo, TailwindCSS utilitario (CDN o configuración ligera) y modularidad limpia.
