# MiniProyecto — Simulador Básico de Cajero Automático

## Uso responsable de IA (resumen)

La IA puede utilizarse como apoyo para aprender, pero no para reemplazar el razonamiento propio. Antes de consultar IA, escriba un intento personal o una explicación de lo que no entiende.

Se permite pedir pistas, explicaciones de errores, revisión de código propio y casos de prueba. No se permite copiar soluciones completas sin comprenderlas. Toda entrega debe incluir una breve declaración de uso de IA.

*(Política completa disponible en el notebook de la Semana 1.)*

## Ajuste del Miniproyecto 3: etapas, uso de IA y evidencia requerida

### Etapas

- **Etapa 1 (obligatoria):** inicio de sesión simple (un solo intento).
- **Etapa 2 (obligatoria):** menú interactivo con `while`.
- **Etapa 3 (obligatoria):** funcionalidades básicas, sin validaciones.
- **Etapa 4 (obligatoria):** validaciones básicas.
- **Etapa 5 (opcional):** mejoras (intentos de contraseña, historial, etc.).

### Qué se permite

- Pedir pistas sobre condicionales, bucles y errores de lógica.
- Pedir que se explique un mensaje de error.

### Qué no se permite

- Pedir que se genere el menú completo sin haber escrito antes un intento propio.
- Copiar código que no se pueda explicar.

### Evidencia requerida

- Captura o copia del error encontrado y cómo se resolvió.
- Explicación del bucle principal.
- Justificación del uso de `break` o `continue`.
- Declaración de uso de IA y reflexión final.

### Entrega

Este miniproyecto forma parte del **documento único de entrega** del curso, junto con los demás miniproyectos concluidos. Consulte el *Instructivo de presentación* y la *Rúbrica de evaluación* para conocer el formato y los criterios.

## Objetivo

Desarrollar un pequeño programa en Python que simule operaciones simples de un cajero automático utilizando:

- estructuras condicionales,
- operadores lógicos,
- bucles,
- control de flujo,
- y funciones básicas.

El objetivo es practicar la construcción de programas interactivos utilizando lógica de programación y estructuras de control. El proyecto se resuelve **por etapas**: complete cada etapa y pruébela antes de pasar a la siguiente.

---

# Contexto del problema

Una entidad bancaria desea implementar una versión simplificada de un cajero automático para pruebas internas.

El programa deberá permitir que un usuario:

- consulte su saldo,
- deposite dinero,
- retire dinero,
- y salga del sistema.

---

# Datos iniciales

Definir inicialmente:

```python
saldo = 100000
```

Además, definir una contraseña simple:

```python
password = "python123"
```

---

# Etapa 1 (obligatoria) — Inicio de sesión

Solicitar al usuario que ingrese una contraseña (un solo intento).

Si la contraseña es incorrecta:

- mostrar un mensaje de error,
- finalizar el programa.

Si la contraseña es correcta:

- permitir el acceso al sistema.

---

# Etapa 2 (obligatoria) — Menú interactivo

Mostrar repetidamente el siguiente menú utilizando un bucle `while`:

```text
===== CAJERO AUTOMÁTICO =====

1. Consultar saldo
2. Depositar dinero
3. Retirar dinero
4. Salir
```

El programa debe continuar ejecutándose hasta que el usuario elija salir. En esta etapa, las opciones 2 y 3 pueden mostrar solo un mensaje provisional (por ejemplo, "Opción en construcción").

---

# Etapa 3 (obligatoria) — Funcionalidades básicas (sin validaciones)

## Opción 1 — Consultar saldo

Mostrar el saldo actual.

## Opción 2 — Depositar dinero

Solicitar un monto, sumarlo al saldo y mostrar el nuevo saldo.

## Opción 3 — Retirar dinero

Solicitar un monto, descontarlo del saldo y mostrar el nuevo saldo.

## Opción 4 — Salir

Mostrar un mensaje de despedida y finalizar el programa.

---

# Etapa 4 (obligatoria) — Validaciones básicas

Agregar a las opciones 2 y 3 las siguientes validaciones:

- **Depositar:** el monto debe ser positivo.
- **Retirar:** el monto debe ser positivo y el saldo debe ser suficiente.

Si alguna validación falla, mostrar un mensaje de error y volver al menú (puede utilizar `continue`). Para salir del menú, utilice `break` o una condición de corte del `while`.

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

# Etapa 5 (opcional) — Mejoras

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
- organización general del programa,
- explicación propia del código y declaración de uso de IA (ver Rúbrica de evaluación).

---

## Declaración de uso de IA

- ¿Utilicé IA en esta actividad?: Sí / No
- Herramienta utilizada:
- ¿Para qué la utilicé?:
- Intento propio antes de usar IA:
- Prompt utilizado:
- Sugerencias aceptadas:
- Sugerencias descartadas:
- ¿Qué aprendí al revisar la respuesta?:

## Reflexión final

Responda brevemente:

1. ¿Qué parte resolví sin IA?
2. ¿En qué momento consulté IA?
3. ¿Qué sugerencia me resultó útil?
4. ¿Qué sugerencia descarté o modifiqué?
5. ¿Puedo explicar todo el código entregado?
