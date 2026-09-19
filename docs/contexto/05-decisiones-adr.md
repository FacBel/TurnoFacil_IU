# Master Context Vivo: 05. Registro de Decisiones de Arquitectura (ADR)

# ADR-001: Selección del Stack Tecnológico (HTML5 Semántico + TailwindCSS + JavaScript Vainilla)

* **Fecha**: 2026-09-18
* **Estado**: Aceptado
* **Decisores**: Senior Product Engineer & Frontend Architect

---

## 1. Contexto y Problema
El producto **TurnoFácil** requiere una interfaz de usuario extremadamente ágil, con tiempos de carga casi instantáneos en dispositivos móviles, excelente compatibilidad con estándares de accesibilidad (WCAG AA) y cero sobrecarga de dependencias o frameworks pesados en su fase de MVP.

Se evaluaron tres alternativas principales:
1. **Framework SPA Complejo (React / Next.js)**: Potente para aplicaciones corporativas extensas, pero añade bundle size considerable, tiempo de configuración y complejidad innecesaria para un flujo interactivo ligero.
2. **CSS Tradicional Monolítico**: Mayor riesgo de inconsistencias de diseño, especificidad descontrolada y mayor esfuerzo para mantener un sistema de tokens unificado.
3. **HTML5 Semántico + TailwindCSS + JavaScript Vainilla Modular**: Máximo rendimiento, carga ultra rápida, clases de diseño utilitarias estandarizadas y control granular del DOM y accesibilidad.

---

## 2. Decisión
Adoptar **HTML5 Semántico**, **TailwindCSS** y **JavaScript Vainilla (ES6+)** como el stack oficial de desarrollo para el proyecto.

### Fundamentos Técnicos:
- **HTML5 Semántico**: Garantiza una estructura nativa comprensible para lectores de pantalla, motores de búsqueda y navegadores móviles sin requerir capas complejas de abstracción.
- **TailwindCSS**: Permite maquetar con un sistema de diseño estricto y consistente (espaciados, colores, breakpoints responsive, estados interactivos `hover`, `focus-visible`, `active`, `disabled`) sin salir del marcado.
- **JavaScript Vainilla (ES6+)**: Ofrece manipulación de estados y eventos nativa (`addEventListener`, `dataset`, `classList`), sin dependencias de terceros, asegurando un peso mínimo y rendimiento óptimo en redes móviles 3G/4G.

---

## 3. Consecuencias

### Positivas:
- **Rendimiento de Carga Máximo**: Tiempos de primer renderizado (FCP y LCP) inferiores a 1 segundo.
- **Mantenibilidad y Escalabilidad**: Las clases utilitarias de Tailwind evitan colisiones de selectores CSS globales.
- **Facilidad de Integración**: El código es portable y puede evolucionar fácilmente hacia cualquier backend o framework futuro sin refactorizaciones traumáticas.

### Negativas / Desafíos:
- Mayor responsabilidad en la gestión manual del estado reactivo en JavaScript.
- *Mitigación*: Implementación de un patrón de arquitectura modular simple basado en módulos JS desacoplados y eventos personalizados.
