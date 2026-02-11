# QA Report: Gestión de Periodistas (Tabla)

Este documento detalla los resultados de las pruebas de aseguramiento de calidad para la visualización y consulta de colaboradores en el módulo de **Periodistas**.

## Información General

* **Portal:** `https://cms.aliviamedia.com/`
* **Fecha de Prueba:** 11 de febrero de 2026.
* **Objetivo:** Validar la integridad de los datos en la tabla, la adaptabilidad móvil y el rendimiento de carga.

---

##  Resumen de Estatus

| Requerimiento | Estatus | Observaciones |
| --- | --- | --- |
| **Integridad de información** | **Exitoso** | Nombres, roles, correos y productividad se muestran correctamente. |
| **Adaptabilidad Mobile** | **Exitoso** | Las columnas se ajustan según lo esperado para la HU. |
| **Velocidad de carga** | **Exitoso** | Respuesta fluida al renderizar la lista de periodistas. |
| **Visualización de Multimedia** | **Fallido** | Error en el renderizado de avatares/fotos en la tabla. |

---

##  Hallazgos Identificados

### 1. Error de Renderizado: Foto de Perfil / Avatar

* **Descripción:** La tabla no logra cargar la imagen de perfil de algunos periodistas, mostrando en su lugar un icono de imagen rota o un contenedor vacío.
* **Detalle:** El error es visible específicamente en los registros nuevos o aquellos con imágenes recientemente vinculadas.
* **Impacto:** **Bajo/Visual**. No afecta la funcionalidad de gestión, pero degrada la estética y la identificación rápida del usuario en la interfaz.
* **Evidencia:** En el listado, el usuario `test 1122026` presenta un icono de imagen rota en lugar del avatar circular.

---

##  Análisis de Columnas (Desktop)

De acuerdo a la revisión, la tabla despliega correctamente los siguientes metadatos:

* **Periodista:** Muestra el nombre completo, el correo electrónico y el espacio para el avatar.
* **Rol & Estado:** Identifica correctamente etiquetas como `Editor Jefe`, `Editor` o `Periodista`, junto al tag de estado `Activo`.
* **Productividad:** Visualización correcta del conteo de artículos (`0 arts.`) y la fecha del último acceso.
* **Acciones:** El menú de tres puntos (opciones) está presente para cada registro.

---

## 🏁 Conclusión

La página de consulta es funcional y cumple con la mayoría de los criterios de aceptación de la HU. El único punto pendiente de corrección es el **enlace o renderizado de las fotos** en la columna principal de la tabla.
