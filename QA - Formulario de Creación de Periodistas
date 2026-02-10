# ✅ QA Report — Formulario de Creación de Periodistas

Este documento presenta los resultados de las pruebas de aseguramiento de calidad realizadas sobre la funcionalidad de **creación y gestión de periodistas/autores** dentro del portal **CMS Alivia Media**.

---

## 📌 Información General

| Campo | Detalle |
|------|---------|
| **Portal** | https://cms.aliviamedia.com/ |
| **Fecha de Prueba** | 10 de febrero de 2026 |
| **Usuario QA** | editor@somoschivas.com.mx |
| **Objetivo** | Validar inserción de nuevos autores, validaciones, guardado exitoso y experiencia mobile |

---

## 🚦 Resumen de Estatus

| Requerimiento | Estatus | Observaciones |
|--------------|---------|--------------|
| Inserción de nuevos autores | ❌ Fallido | Error crítico impide el guardado |
| Validaciones de campos (nombres, fotos, etc.) | ✅ Exitoso | Inputs permiten carga correcta de datos y multimedia |
| Guardado y mensaje de confirmación | ❌ Fallido | El sistema muestra error en lugar de confirmar |
| Usabilidad en Mobile (inputs/botones) | ✅ Exitoso | Diseño responsivo y elementos accesibles |

---

## ❗ Hallazgos Críticos (Bloqueantes)

### 🔴 Error de API: `userId is null or undefined`

**Descripción**  
Al intentar procesar la creación de un nuevo periodista, el sistema despliega un banner de error que bloquea completamente el registro.

**Impacto**  
- Severidad: **Crítica**
- Impide el alta de nuevos colaboradores en la base de datos.

**Consistencia**  
El error ocurre de forma idéntica en:

- Desktop  
- Mobile  

---

### 📷 Evidencia Visual

- **Desktop:** Banner rojo aparece sobre el campo de correo electrónico.  
- **Mobile:** Banner aparece inmediatamente debajo del título **"Crear nuevo periodista"**.

---

## 🎨 Análisis de Interfaz y UX

### 🖥️ Vista Desktop (Escritorio)

- Se verificó el generador automático de contraseñas.
- Funciona correctamente el módulo de carga de fotografía de perfil.
- El formulario presenta estructura clara con campos obligatorios marcados con (*).

**Campos probados:**

- Nombre  
- Segundo nombre  
- Apellidos  
- Biografía profesional  

---

### 📱 Vista Mobile (Móvil)

- Inputs como **Correo Electrónico** y **Nombre** se adaptan correctamente al ancho de pantalla.
- Se mantienen iconos dentro de los campos para guiar al usuario.
- Menú hamburguesa y botones de navegación visibles y funcionales.

---

## 🧪 Datos de Prueba Utilizados

### Correos

- periodista_test1_D@aliviamedia.com  
- colaborador@aliviamedia.com  

### Nombres

- Test Desktop  
- Test Móvil  

---

## 🏁 Conclusión y Recomendación

Aunque la interfaz cumple con estándares de diseño y usabilidad (especialmente en mobile), la funcionalidad principal de guardado está rota.

✅ Se recomienda revisar con urgencia:

- La lógica de sesión del usuario autenticado  
- El envío correcto del parámetro **userId** en la API  
- Validaciones backend antes del deploy final  

---

**Estado general:** ❌ Bloqueado para entrega

