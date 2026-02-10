# Revisiones-CMS

# Reporte de QA - Formulario de Creación de Periodistas

**Portal:** [https://cms.aliviamedia.com/](https://cms.aliviamedia.com/)  
**Usuario de prueba:** `editor@somoschivas.com.mx`  
**Fecha de reporte:** 10/02/2026  
**Objetivo:** Validar la inserción de nuevos autores, validaciones de campos, guardado exitoso y experiencia de usuario en Desktop y Mobile.

---

## 1. Hallazgos Funcionales (Errores Críticos)

### A. Error de API: `userId is null or undefined`

* **Descripción:** Al intentar procesar la creación de un nuevo periodista, el sistema despliega un banner de error que bloquea el registro.
* **Impacto:** Crítico. Impide totalmente el alta de nuevos colaboradores en la base de datos.
* **Consistencia:** El error ocurre de manera idéntica tanto en Desktop como en Mobile.
* **Evidencia:**
  - Desktop: Banner rojo aparece sobre el campo de correo electrónico.  
  - Mobile: Banner aparece inmediatamente debajo del título **"Crear nuevo periodista"**.

---

## 2. Hallazgos de Interfaz y UX (Responsive)

A nivel visual y de experiencia de usuario, el formulario presenta buena adaptabilidad y estructura clara.

### A. Vista Desktop (Escritorio)

* **Funcionalidades verificadas:**
  - Generador automático de contraseñas.
  - Área de carga de fotografía de perfil.
* **Formato:** Campos obligatorios marcados con (*).
* **Campos probados:**
  - Nombre  
  - Segundo nombre  
  - Apellidos  
  - Biografía profesional  

---

### B. Vista Mobile (Móvil)

* **Adaptabilidad:** Inputs como **Correo Electrónico** y **Nombre** se ajustan correctamente al ancho de pantalla.
* **Iconografía:** Se mantienen iconos dentro de los campos para mejorar la guía visual.
* **Navegación:** Menú hamburguesa y botones de navegación visibles y funcionales.

---

## 3. Datos de Prueba Utilizados

* **Correos:**
  - periodista_test1_D@aliviamedia.com  
  - colaborador@aliviamedia.com  

* **Nombres:**
  - Test Desktop  
  - Test Móvil  

---

## 4. Resumen de Pruebas

| ID Hallazgo | Gravedad | Categoría | Descripción Corta |
| :--- | :--- | :--- | :--- |
| **ERR-001** | Alta | Funcional | Error de API: `userId` null impide guardar periodistas. |
| **UX-001** | Baja | UI/UX | Formulario responsivo y usable en Mobile. |
| **VAL-001** | Baja | Validación | Inputs permiten carga correcta de datos y multimedia. |

---

## 5. Conclusiones y Próximos Pasos

Aunque el formulario cumple con estándares de diseño y usabilidad (especialmente en Mobile), la funcionalidad principal de guardado está bloqueada.

Es imperativo revisar antes de entrega final:

* La lógica de sesión del usuario autenticado.
* El envío correcto del parámetro **userId** en la API.
* Validaciones backend previas al deploy.

**Estado general:** ❌ Bloqueado para entrega hasta corregir el error crítico.

---
