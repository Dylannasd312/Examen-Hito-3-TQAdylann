# Casos de prueba de caja negra

## Información general

- Aplicación: SauceDemo (Swag Labs)
- Tipo de pruebas: Funcionales de caja negra
- Técnica: Pruebas basadas en entradas y resultados observables
- Estado inicial: Pendiente de ejecución

---

## TC-001: Inicio de sesión exitoso

**Prioridad:** Alta

**Precondiciones:**
- La página de inicio de sesión está disponible.

**Datos de prueba:**
- Usuario: `standard_user`
- Contraseña: `secret_sauce`

**Pasos:**
1. Abrir SauceDemo.
2. Introducir el usuario.
3. Introducir la contraseña.
4. Pulsar Login.

**Resultado esperado:**
El sistema permite el acceso y muestra el catálogo de productos.

**Resultado obtenido:** Se inició sesión correctamente y se visualizó el catálogo de productos.

**Estado:** APROBADO

**Evidencia:** evidencias/capturas/TC-001.png

---

## TC-002: Inicio de sesión con credenciales incorrectas

**Prioridad:** Alta

**Precondiciones:**
- La página de inicio de sesión está disponible.

**Datos de prueba:**
- Usuario: `usuario_incorrecto`
- Contraseña: `clave_incorrecta`

**Pasos:**
1. Abrir SauceDemo.
2. Introducir las credenciales incorrectas.
3. Pulsar Login.

**Resultado esperado:**
El sistema rechaza el acceso y muestra un mensaje de error.

**Resultado obtenido:** El sistema rechazó el acceso y mostró: Epic sadface: Username and password do not match any user in this service.

**Estado:** APROBADO

**Evidencia:** evidencias/capturas/TC-002.png

---

## TC-003: Agregar un producto al carrito

**Prioridad:** Alta

**Precondiciones:**
- El usuario inició sesión correctamente.
- El catálogo de productos está visible.

**Datos de prueba:**
- Producto: Sauce Labs Backpack.

**Pasos:**
1. Identificar Sauce Labs Backpack.
2. Pulsar Add to cart.
3. Comprobar el indicador del carrito.

**Resultado esperado:**
El producto se agrega al carrito y el indicador refleja una unidad.

**Resultado obtenido:** El botón cambió a Remove y el indicador del carrito muestra 1.

**Estado:** APROBADO

**Evidencia:** evidencias/capturas/TC-003.png

---

## TC-004: Eliminar un producto del carrito

**Prioridad:** Media

**Precondiciones:**
- El usuario inició sesión.
- Se agregó Sauce Labs Backpack al carrito.

**Datos de prueba:**
- Producto: Sauce Labs Backpack.

**Pasos:**
1. Abrir el carrito.
2. Comprobar que el producto esté presente.
3. Pulsar Remove.

**Resultado esperado:**
El producto desaparece del carrito y el indicador se actualiza según corresponda.

**Resultado obtenido:** El botón volvió a Add to cart y desapareció el indicador numérico del carrito.

**Estado:** APROBADO

**Evidencia:** evidencias/capturas/TC-004.png

---

## TC-005: Validación de campos obligatorios del checkout

**Prioridad:** Alta

**Precondiciones:**
- El usuario inició sesión.
- Hay al menos un producto en el carrito.

**Datos de prueba:**
- Nombre: vacío.
- Apellido: vacío.
- Código postal: vacío.

**Pasos:**
1. Abrir el carrito.
2. Pulsar Checkout.
3. Dejar vacíos los campos del formulario.
4. Pulsar Continue.

**Resultado esperado:**
El sistema impide continuar y muestra un mensaje de validación.

**Resultado obtenido:** El sistema impidió continuar y mostró Error: First Name is required.

**Estado:** APROBADO

**Evidencia:** evidencias/capturas/TC-005.png