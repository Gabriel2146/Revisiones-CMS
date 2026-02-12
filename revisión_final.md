# Reporte de QA: Estado del CMS (Post-Actualización)

**Fecha:** 12 de febrero de 2026.
**Estado General:** **Estable con observaciones críticas en permisos y multimedia.**

---

## Resumen de Estatus de Funcionalidad

| Módulo | Estatus | Observaciones |
| --- | --- | --- |
| **CRUD (Artículos, Stories, Live Blog)** | Operativo | La edición de borradores y funciones generales del CRUD funcionan correctamente. |
| **Creación de Periodistas** | Corregido | Las validaciones de campos obligatorios y la inserción de datos ya son funcionales. |
| **Visualización de Periodistas** | Parcial | La tabla muestra los datos, pero persiste el error en la imagen de perfil. |
| **Navegación (Publicados)** | Nota Técnica | El error 404 en historias publicadas es un comportamiento esperado por falta de sincronización del front-end. |

---

## Hallazgos Pendientes y Nuevos Errores

### 1. Gestión de Periodistas (Tabla y Acciones)

* **Error en Multimedia (Persistente):** Las fotografías de los periodistas siguen sin visualizarse correctamente en la tabla general de consulta.
* **Restricción de Edición (Nuevo):** El usuario con rol **Admin** no tiene habilitada la opción de editar periodistas desde el menú de acciones.
* **Estado de Validaciones:** Se confirma que el sistema ya impide el registro si no se completa la información requerida (validación exitosa).

### 2. Error 404 en Historias Publicadas

* **Estado:** No solucionado, pero identificado.
* **Causa Raíz:** El enlace redirige al sitio del medio, cuyo front-end aún no está actualizado con el nuevo back-end.
* **Acción:** Se mantendrá como "pendiente" hasta el despliegue final del sitio público.

---

## Próximas Pruebas (Checklist para las 12:30 p. m.)

Para el cierre del reporte solicitado por LeoJP, se están verificando actualmente los siguientes puntos para asegurar que no existan regresiones:

* [ ] **Subida de medios:** Confirmar si permite subir imágenes y videos sin errores de validación de tipo (Error `featuredMedia`).
* [ ] **Borrado de posts:** Validar que la eliminación de artículos, stories y blogs se ejecute correctamente.
* [ ] **Edición de Web Stories:** Verificar que los cambios en el editor de historias se guarden sin pérdida de datos.


## 🏁 Conclusión Técnica

La actualización corrigió los bloqueos críticos de creación (inserción de datos), pero persisten detalles visuales en la tabla de periodistas y una posible inconsistencia en los permisos del rol Administrador para la edición de perfiles.

