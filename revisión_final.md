# Reporte Consolidado de QA: CMS Alivia Media

Este documento integra los hallazgos de las pruebas realizadas los días 11 y 12 de febrero de 2026, cubriendo tanto la actualización general del sistema como el módulo específico de gestión de periodistas.

## Información General

* **Portal:** `https://cms.aliviamedia.com/`
* **Fechas de Prueba:** 11 y 12 de febrero de 2026.
* **Estado General:** **Estable con observaciones críticas en permisos y multimedia**.

---

## Resumen de Estatus de Funcionalidad

| Módulo / Requerimiento | Estatus | Observaciones |
| --- | --- | --- |
| **CRUD (Artículos, Stories, Live Blog)** | Operativo | Edición de borradores y funciones generales funcionan correctamente. |
| **Creación de Periodistas** | Corregido | Validaciones de campos obligatorios e inserción de datos ya son funcionales. |
| **Integridad de Información (Tabla)** | Exitoso | Nombres, roles, correos y productividad se muestran correctamente. |
| **Adaptabilidad Mobile** | Exitoso | Las columnas de la tabla se ajustan según lo esperado. |
| **Velocidad de carga** | Exitoso | Respuesta fluida al renderizar la lista de periodistas. |
| **Visualización de Periodistas** | Parcial | Persiste el error en la imagen de perfil dentro de la tabla. |
| **Navegación (Publicados)** | Nota Técnica | Error 404 esperado por falta de sincronización del front-end con el nuevo back-end. |

---

## Hallazgos Detallados y Errores Identificados

### 1. Gestión de Periodistas (Tabla y Acciones)

* **Error de Renderizado Multimedia (Persistente):** La tabla no logra cargar la imagen de perfil (avatar) de algunos periodistas, mostrando un icono de imagen rota o contenedor vacío. Este error es visible en registros nuevos o recientemente vinculados, afectando la estética e identificación rápida.
* **Restricción de Edición (Nuevo):** El usuario con rol **Admin** no tiene habilitada la opción de editar periodistas desde el menú de acciones.
* **Análisis de Columnas:** Se validó que los metadatos de Rol (Editor Jefe, Periodista, etc.), Estado (Activo) y Productividad (conteo de artículos y último acceso) se despliegan correctamente.

### 2. Navegación y Errores de Redirección

* **Error 404 en Historias Publicadas:** Identificado pero no solucionado. Se debe a que el enlace redirige al sitio del medio, cuyo front-end aún no está actualizado para comunicarse con el nuevo back-end. Permanecerá como pendiente hasta el despliegue final del sitio público.

---

## Próximas Pruebas (Checklist de Cierre)

Actualmente se verifican los siguientes puntos para asegurar que no existan regresiones tras las últimas correcciones:

* [ ] **Subida de medios:** Validar imágenes y videos sin errores de tipo (`featuredMedia`).
* [ ] **Borrado de posts:** Confirmar eliminación de artículos, stories y blogs.
* [ ] **Edición de Web Stories:** Asegurar que el guardado de cambios no presente pérdida de datos.

---

## Conclusión Técnica

La actualización del 11 de febrero corrigió los bloqueos críticos de creación e inserción de datos. La página de consulta es funcional y cumple con la mayoría de los criterios de usabilidad y adaptabilidad. Sin embargo, persisten **detalles visuales en el renderizado de fotos** y una **inconsistencia en los permisos del rol Administrador** que deben atenderse antes de la entrega final.
