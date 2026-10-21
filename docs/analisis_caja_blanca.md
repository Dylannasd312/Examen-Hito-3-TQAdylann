# Análisis de caja blanca

## 1. Objetivo

Analizar la función `validar_compra()` mediante la identificación
de sus decisiones y el diseño de casos de prueba que permitan
verificar sus diferentes caminos de ejecución.

## 2. Decisiones identificadas

| ID | Condición | Resultado verdadero | Resultado falso |
|---|---|---|---|
| D1 | edad < 18 | Compra no permitida: edad | Continúa |
| D2 | not cuenta_activa | Compra no permitida: cuenta | Continúa |
| D3 | saldo >= monto and monto > 0 | Compra aprobada | Compra rechazada |

La decisión D3 contiene dos condiciones simples:
- saldo >= monto
- monto > 0

## 3. Casos de prueba

| ID | Edad | Cuenta activa | Saldo | Monto | Resultado esperado |
|---|---:|---|---:|---:|---|
| WB-001 | 16 | Sí | 100 | 50 | Compra no permitida: edad |
| WB-002 | 25 | No | 100 | 50 | Compra no permitida: cuenta |
| WB-003 | 25 | Sí | 100 | 50 | Compra aprobada |
| WB-004 | 25 | Sí | 30 | 50 | Compra rechazada |
| WB-005 | 25 | Sí | 100 | 0 | Compra rechazada |

## 4. Cobertura de decisiones

Se identificaron tres decisiones con dos resultados posibles
cada una, para un total de seis resultados de decisión.

Los casos diseñados cubren los resultados verdadero y falso
de D1, D2 y D3.

Cobertura de decisiones: 6/6 × 100 = 100 %.

## 5. Conclusión

Los casos diseñados recorren las ramas principales de la función
y verifican las condiciones de edad, estado de cuenta, saldo
disponible y monto positivo.