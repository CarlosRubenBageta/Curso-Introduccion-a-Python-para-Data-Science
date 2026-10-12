# MiniProyecto — Simulador Básico de Cajero Automático

## Objetivo

Desarrollar un pequeño programa en Python que simule operaciones simples de un cajero automático utilizando:

- estructuras condicionales,
- operadores lógicos,
- bucles,
- control de flujo,
- y funciones básicas.

El objetivo es practicar la construcción de programas interactivos utilizando lógica de programación y estructuras de control.

---

# Contexto del problema

Una entidad bancaria desea implementar una versión simplificada de un cajero automático para pruebas internas.

El programa deberá permitir que un usuario:

- consulte su saldo,
- deposite dinero,
- retire dinero,
- y salga del sistema.

---

# Requisitos del proyecto

## Datos iniciales

Definir inicialmente:

```python
saldo = 100000
```

Además, definir una contraseña simple:

```python
password = "python123"
```

---

# Parte 1 — Inicio de sesión

Solicitar al usuario que ingrese una contraseña.

Si la contraseña es incorrecta:

- mostrar un mensaje de error,
- finalizar el programa.

Si la contraseña es correcta:

- permitir el acceso al sistema.

---

# Parte 2 — Menú interactivo

Mostrar repetidamente el siguiente menú utilizando un bucle `while`:

```text
===== CAJERO AUTOMÁTICO =====

1. Consultar saldo
2. Depositar dinero
3. Retirar dinero
4. Salir
```

El programa debe continuar ejecutándose hasta que el usuario elija salir.

---

# Parte 3 — Funcionalidades

## Opción 1 — Consultar saldo

Mostrar el saldo actual.

---

## Opción 2 — Depositar dinero

Solicitar un monto.

Validar que:

- el monto sea positivo.

Si es válido:

- agregar el monto al saldo,
- mostrar el nuevo saldo.

---

## Opción 3 — Retirar dinero

Solicitar un monto.

Validar que:

- el monto sea positivo,
- el saldo sea suficiente.

Si el retiro es válido:

- descontar el dinero del saldo,
- mostrar el nuevo saldo.

Si el saldo no es suficiente:

- mostrar un mensaje de error.

---

## Opción 4 — Salir

Mostrar un mensaje de despedida y finalizar el programa.

---

# Requisitos técnicos

El proyecto debe incluir:

- estructuras `if`, `elif` y `else`,
- operadores lógicos,
- bucles `while`,
- uso de `break` o `continue`,
- validaciones básicas,
- interacción con el usuario mediante `input()`.

---

# Recomendaciones

- Utilizar nombres de variables claros.
- Mantener el código ordenado.
- Utilizar comentarios simples.
- Verificar distintos escenarios de prueba.

---

# Ejemplo esperado de ejecución

```text
Ingrese la contraseña: python123

===== CAJERO AUTOMÁTICO =====

1. Consultar saldo
2. Depositar dinero
3. Retirar dinero
4. Salir

Seleccione una opción: 1

Saldo actual: $100000
```

---

# Desafío opcional

Agregar alguna de las siguientes mejoras:

- límite máximo de intentos de contraseña,
- historial simple de operaciones,
- transferencia ficticia de dinero,
- validación para impedir ingreso de texto en montos numéricos.

---

# Criterios de evaluación

Se tendrá en cuenta:

- correcta utilización de estructuras condicionales,
- uso adecuado de bucles,
- validaciones implementadas,
- claridad del código,
- organización general del programa.
