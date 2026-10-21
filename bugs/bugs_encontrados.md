# Registro de Bugs

## BUG-001: Imágenes incorrectas en el catálogo de productos

### Información general

- **ID:** BUG-001
- **Título:** Imágenes incorrectas en el catálogo de productos.
- **Aplicación:** SauceDemo
- **Módulo:** Catálogo de productos.
- **Usuario de prueba:** `problem_user`
- **Tipo de defecto:** Visual / Funcional.
- **Severidad:** Media.
- **Prioridad:** Media.
- **Estado:** Reproducido en la ejecución documentada.

### Descripción del problema

Al iniciar sesión en SauceDemo con el usuario `problem_user`,
se observa que varios productos del catálogo muestran la misma
fotografía de un perro con una pelota, aunque tienen nombres,
descripciones y precios diferentes.

En la captura se observa este comportamiento en productos como
Sauce Labs Backpack y Sauce Labs Bike Light.

La imagen mostrada no corresponde visualmente a los productos
identificados por sus respectivos nombres y descripciones.

### Precondiciones

1. Tener acceso a SauceDemo.
2. Disponer de las credenciales de demostración.
3. Utilizar el usuario `problem_user`.

### Datos de prueba

- **Usuario:** `problem_user`
- **Contraseña:** `secret_sauce`

### Pasos para reproducir

1. Acceder a https://www.saucedemo.com/.
2. Introducir el usuario `problem_user`.
3. Introducir la contraseña `secret_sauce`.
4. Hacer clic en el botón Login.
5. Observar las imágenes de los productos del catálogo.
6. Comparar las imágenes con los nombres y las descripciones.

### Resultado esperado

Cada producto debe mostrar una imagen que corresponda
visualmente al artículo descrito en el catálogo.

### Resultado obtenido

Varios productos muestran la misma fotografía de un perro
con una pelota, aunque sus nombres y descripciones corresponden
a artículos diferentes.

### Evidencia

- **Archivo:** `evidencias/capturas/BUG-001.png`
- **Descripción:** Captura del catálogo con el usuario
  `problem_user`, donde se observan imágenes incorrectas.

### Impacto

El defecto dificulta la identificación visual de los productos
y puede confundir al usuario durante la selección de artículos.

### Conclusión

Se documentó un defecto visual en el catálogo durante la
ejecución de la prueba con el usuario `problem_user`.
La evidencia permite observar la discrepancia entre las
imágenes mostradas y los productos identificados.