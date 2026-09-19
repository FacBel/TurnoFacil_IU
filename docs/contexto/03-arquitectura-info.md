# Master Context Vivo: 03. Arquitectura de Información y Componentes MVP

## 1. Flujo Principal en 5 Pasos (*Stepper UI*)

Para minimizar la carga cognitiva del usuario, el proceso de reserva se fragmenta en un asistente guiado (*Stepper*) de 5 etapas secuenciales:

```
[ 1. Servicio ] ──> [ 2. Profesional ] ──> [ 3. Fecha & Hora ] ──> [ 4. Datos ] ──> [ 5. Confirmación ]
```

### Detalle de cada Paso:
1. **Paso 1: Selección de Servicio**
   - Tarjetas interactivas con título, descripción corta, duración (minutos) y precio.
   - Filtro rápido por categorías: *Corte*, *Barba*, *Combos*, *Tratamientos*.
2. **Paso 2: Selección de Profesional**
   - Tarjetas de especialistas con fotografía/avatar, nombre, rol y badge de especialidad.
   - Opción genérica: *"Cualquier profesional disponible"* (para maximizar disponibilidad de turnos).
3. **Paso 3: Selección de Fecha y Franja Horaria**
   - Selector horizontal de días con fecha actual destacada.
   - Grilla de slots horarios organizados por *Mañana*, *Tarde* y *Noche*, con estados `Libre`, `Ocupado` y `Seleccionado`.
4. **Paso 4: Datos de Contacto y Resumen**
   - Formulario ultra-ligero: Nombre Completo, Teléfono (WhatsApp) y Notas adicionales optativas.
   - Resumen dinámico (*Live Summary Card*) con el detalle de lo seleccionado.
5. **Paso 5: Confirmación y Ticket Digital**
   - Visualización del comprobante de reserva con código identificador único.
   - Acciones de valor: *Guardar en Google Calendar*, *Enviar detalle por WhatsApp* y *Modificar/Cancelar*.

---

## 2. Componentes Clave del MVP (Desglose Funcional)

| Componente | Rol en la UI | Elementos Clave |
| :--- | :--- | :--- |
| **`AppHeader`** | Navegación e Identidad | Logo de la barbería/salón, estado de atención ("Abierto hoy hasta 20:00") y botón de contacto. |
| **`StepProgress`** | Orientación Espacial | Indicador visual de los 5 pasos con estados: *Completado*, *Activo*, *Pendiente*. |
| **`ServiceCard`** | Selección de Servicio | Selector `radio`/`checkbox`, precio resaltado, duración en minutos y descripción. |
| **`StaffCard`** | Selección de Profesional | Avatar con borde de estado, nombre, especialidad y selección accesible. |
| **`TimeSlotGrid`** | Selección de Horarios | Botones de horario con contraste WCAG, estado `disabled` para slots ocupados. |
| **`BookingSummarySticky`** | Resumen Dinámico | Barra o tarjeta fija en pantalla móvil que actualiza el total ($) y duración acumulada. |
| **`BookingForm`** | Captura de Datos | Inputs accesibles con etiquetas asociadas (`<label>`), validación en tiempo real y mensaje de error. |
| **`ConfirmationTicket`** | Cierre y Reaseguro | Resumen final con badge de éxito, fecha formateada y llamadas a la acción (*CTAs*). |

---

## 3. Jerarquía de Información (*Visual Hierarchy*)

1. **Nivel 1 (Foco Operativo)**: Opciones seleccionables del paso activo con contrastes destacados.
2. **Nivel 2 (Feedback de Progreso)**: Resumen inferior persistente (*Sticky Bar*) que refleja costo y duración.
3. **Nivel 3 (Acción Primaria - CTA)**: Botón principal *"Continuar"* / *"Confirmar Turno"* con ancho completo en móvil y estado hover/active evidente.
4. **Nivel 4 (Navegación Secundaria)**: Botón *"Volver"* accesible para corregir decisiones previas sin perder datos.
