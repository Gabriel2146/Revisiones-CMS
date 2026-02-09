# Revisiones-CMS

# Reporte de QA - Creación de Live Blogging

**Portal:** [https://cms.aliviamedia.com/](https://cms.aliviamedia.com/)
**Usuario de prueba:** `editor@somoschivas.com.mx`
**Fecha de reporte:** 09/02/2026
**Objetivo:** Validar el formulario de inicio de eventos, configuración inicial y visualización en Desktop y Mobile.

---

## 1. Hallazgos de Interfaz (Responsive)

Se identificaron problemas de visualización en el componente de programación de inicio (Fecha/Hora), tanto en la versión de escritorio como en la móvil.

### A. Desbordamiento en Desktop
* **Descripción:** El selector de hora se sale del contenedor principal del formulario. El icono del reloj queda fuera de los límites visuales.
* **Archivo:** `![WhatsApp Image 2026-02-09 at 1 18 54 PM](https://github.com/user-attachments/assets/4e6eb8a1-a2c7-4041-82d4-fa04d4068d8f)`

### B. Desajuste en Mobile
* **Descripción:** Los campos de fecha y hora pierden alineación y proporción, dificultando la lectura y selección del tiempo de programación.
* **Archivo:** `![WhatsApp Image 2026-02-09 at 1 22 04 PM](https://github.com/user-attachments/assets/9a442dcc-e7f7-4510-af42-bee67f85c592)`

---

## 2. Hallazgos Funcionales (Errores Críticos)

### A. Error de Validación en `featuredMedia`
* **Problema:** Al intentar actualizar una nota o guardar cambios, el sistema elimina la imagen cargada y arroja un error de validación de tipo.
* **Mensaje del Sistema:** `Error: featuredMedia.type must be one of the following values: IMAGE, VIDEO`
* **Detalle:** El CMS no reconoce correctamente el formato del archivo cargado al momento de la edición, lo que impide guardar el progreso del Live Blog.
* **Archivo:** `![WhatsApp Image 2026-02-09 at 1 27 58 PM](https://github.com/user-attachments/assets/ed5bd047-90f5-4555-b804-53b37e8d6622)`

### B. Error 404 y Redirección Incorrecta
* **Descripción:** Al intentar acceder a eventos que ya están listados como "Publicados" tras iniciar sesión, el sistema muestra una página de error 404.
* **Navegación:** Al intentar regresar mediante el botón "Volver al inicio" del 404, el sistema redirige al sitio externo (Somos Chivas) en lugar de volver al Dashboard del CMS.

---

## 3. Resumen de Pruebas

| ID Hallazgo | Gravedad | Categoría | Descripción Corta |
| :--- | :--- | :--- | :--- |
| **ERR-001** | Baja | UI/UX | Desbordamiento del selector de hora en Desktop. |
| **ERR-002** | Baja | UI/UX | Falta de adaptabilidad en campos de fecha/hora en Mobile. |
| **ERR-003** | Alta | Funcional | Error en API/Validación: No permite actualizar `featuredMedia`. |
| **ERR-004** | Media | Navegación | Error 404 en publicados y redirección errónea fuera del CMS. |

---

## 4. Conclusiones y Próximos Pasos
El flujo de creación de Live Blogging presenta bloqueos críticos en la edición y actualización debido a la validación del tipo de media. Es necesario corregir la lógica del campo `featuredMedia` para que acepte los valores `IMAGE` o `VIDEO` correctamente antes de la fecha de entrega (viernes 13).
