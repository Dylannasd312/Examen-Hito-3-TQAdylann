# Escenarios de Prueba con Gherkin

## 1. Objetivo

Documentar los escenarios de prueba funcionales de SauceDemo utilizando Gherkin, describiendo las condiciones iniciales, las acciones realizadas y los resultados esperados.

## 2. Herramientas utilizadas

- **Aplicación bajo prueba:** SauceDemo.
- **Técnica de prueba:** Caja negra.
- **Formato de especificación:** Gherkin.
- **Palabras clave:** Feature, Scenario, Given, When, Then y And.

## 3. Escenarios de prueba

### Escenario 1: Inicio de sesión exitoso

**ID:** TC-001

**Objetivo:** Verificar que un usuario pueda iniciar sesión con credenciales válidas.

```gherkin
Feature: Inicio de sesión en SauceDemo

  Scenario: Iniciar sesión con credenciales válidas
    Given que el usuario está en la página de inicio de sesión
    When introduce el usuario "standard_user"
    And introduce la contraseña "secret_sauce"
    And hace clic en el botón "Login"
    Then el sistema permite el acceso
    And muestra el catálogo de productos
```

**Resultado obtenido:** El sistema permitió el acceso y mostró el catálogo de productos.

**Estado:** APROBADO.

**Evidencia:** `evidencias/capturas/TC-001.png`

---

### Escenario 2: Inicio de sesión con credenciales incorrectas

**ID:** TC-002

**Objetivo:** Verificar que el sistema rechace las credenciales incorrectas.

```gherkin
Feature: Inicio de sesión en SauceDemo

  Scenario: Rechazar credenciales incorrectas
    Given que el usuario está en la página de inicio de sesión
    When introduce el usuario "usuario_incorrecto"
    And introduce la contraseña "clave_incorrecta"
    And hace clic en el botón "Login"
    Then el sistema rechaza el acceso
    And muestra un mensaje de error
```

**Resultado obtenido:** El sistema rechazó el acceso y mostró el mensaje de error: "Epic sadface: Username and password do not match any user in this service".

**Estado:** APROBADO.

**Evidencia:** `evidencias/capturas/TC-002.png`

---

### Escenario 3: Agregar un producto al carrito

**ID:** TC-003

**Objetivo:** Verificar que el usuario pueda agregar un producto al carrito de compras.

```gherkin
Feature: Gestión del carrito de compras

  Scenario: Agregar Sauce Labs Backpack al carrito
    Given que el usuario inició sesión correctamente
    And se encuentra en el catálogo de productos
    When hace clic en "Add to cart" para "Sauce Labs Backpack"
    Then el botón cambia a "Remove"
    And el indicador del carrito muestra "1"
```

**Resultado obtenido:** El producto se agregó correctamente, el botón cambió a "Remove" y el indicador del carrito mostró el número 1.

**Estado:** APROBADO.

**Evidencia:** `evidencias/capturas/TC-003.png`

---

### Escenario 4: Eliminar un producto del carrito

**ID:** TC-004

**Objetivo:** Verificar que el usuario pueda eliminar un producto del carrito.

```gherkin
Feature: Gestión del carrito de compras

  Scenario: Eliminar Sauce Labs Backpack del carrito
    Given que el usuario inició sesión correctamente
    And agregó "Sauce Labs Backpack" al carrito
    When hace clic en "Remove"
    Then el botón cambia a "Add to cart"
    And desaparece el indicador numérico del carrito
```

**Resultado obtenido:** El producto se eliminó correctamente, el botón volvió a mostrar "Add to cart" y desapareció el indicador numérico del carrito.

**Estado:** APROBADO.

**Evidencia:** `evidencias/capturas/TC-004.png`

---

### Escenario 5: Validación de campos obligatorios durante el checkout

**ID:** TC-005

**Objetivo:** Verificar que el sistema impida continuar con la compra cuando no se completan los campos obligatorios.

```gherkin
Feature: Validación de información de compra

  Scenario: Intentar continuar sin completar los datos
    Given que el usuario inició sesión correctamente
    And tiene un producto en el carrito
    And se encuentra en la página "Checkout: Your Information"
    When deja vacíos los campos First Name, Last Name y Zip/Postal Code
    And hace clic en "Continue"
    Then el sistema impide continuar
    And muestra el mensaje "Error: First Name is required"
```

**Resultado obtenido:** El sistema impidió continuar y mostró el mensaje "Error: First Name is required".

**Estado:** APROBADO.

**Evidencia:** `evidencias/capturas/TC-005.png`

---

## 4. Resumen de resultados

| ID | Escenario | Estado |
|---|---|---|
| TC-001 | Inicio de sesión exitoso | APROBADO |
| TC-002 | Inicio de sesión con credenciales incorrectas | APROBADO |
| TC-003 | Agregar un producto al carrito | APROBADO |
| TC-004 | Eliminar un producto del carrito | APROBADO |
| TC-005 | Validación de campos obligatorios | APROBADO |
| **Total** | **5 escenarios ejecutados** | **5 aprobados** |

### Porcentaje de aprobación

La fórmula utilizada es:

Porcentaje de aprobación = (Casos aprobados / Total de casos ejecutados) × 100

Porcentaje de aprobación = (5 / 5) × 100 = **100 %**

Este porcentaje corresponde únicamente a los cinco escenarios ejecutados.

## 5. Conclusión

Se documentaron cinco escenarios de prueba utilizando la estructura Gherkin para describir las condiciones iniciales, las acciones y los resultados esperados.

Las pruebas permitieron verificar el inicio de sesión con credenciales válidas e incorrectas, la incorporación y eliminación de productos del carrito y la validación de campos obligatorios durante el proceso de compra.

Los cinco escenarios ejecutados fueron aprobados de acuerdo con los resultados observados. La documentación facilita la comprensión y reproducción de las pruebas realizadas en SauceDemo.