# Fichas de ejercicios · Semana 3 (Estructuras de control de flujo)

Base de conocimiento del tutor socrático. Cada ficha corresponde a un ejercicio del notebook `Semana_3_Estructuras_de_control_de_flujo_de_datos_v4.ipynb`.

- **Código:** `S3-E5` = Semana 3, ejercicio 5.
- **Nivel de protección:** todos los ejercicios de esta semana son PRÁCTICA, salvo indicación en la ficha.
- **Pistas:** se entregan de a una y en orden. La Pista 1 coincide con la guía del notebook.
- **Verificación:** criterio para que el estudiante compruebe su resultado y para que el tutor revise el intento.
- Las fichas no incluyen la solución en código a propósito.

### S3-E1 · Instalar e importar numpy

**Enunciado:**

> Ejercicio 1: Instalacion de paquetes desde Jupyter Notebook
>
> - Instala usando el gestor **pip** la libreria *numpy*.
>
> Investiga:
>
> - cómo es el proceso para importar la libreria antes de utilizar sus funciones? Realiza la importación de *numpy*.
>
> - Cómo es el manejo de *alias* para el manejo de liberias? Formula un ejemplo con *numpy*.
>
> - Cómo es el proceso para importar una función específica de la libreria? Úsala en un ejemplo.

- **Objetivo:** Instalar un paquete desde Jupyter e importarlo de tres formas: completo, con alias y una función específica.
- **Pista 1:** En una celda de Jupyter puedes instalar con `%pip install` seguido del nombre del paquete.
- **Pista 2:** Para usar una librería hay que importarla con `import`; un alias se agrega con `as`.
- **Pista 3:** Para traer solo una función se usa la forma `from ... import ...`.
- **Errores frecuentes:** Usar `pip install` sin `%` dentro de una celda. Instalar en otro entorno de Python distinto del kernel del notebook.
- **Verificación:** La importación se ejecuta sin error, `numpy.__version__` (o el alias que elegiste) muestra un número de versión y tu ejemplo con la función importada funciona.

### S3-E2 · Par o impar

**Enunciado:**

> Ejercicio 2
>
> Escribe un programa que determine si un número es par o impar.

- **Objetivo:** Usar el operador de resto y una estructura `if`/`else`.
- **Pista 1:** Un número es par si al dividirlo por 2 no queda resto. ¿Qué operador de Python da el resto de una división?
- **Pista 2:** Usa `if` con esa condición y `else` para el otro caso.
- **Pista 3:** Compara el resto con 0 usando `==`.
- **Errores frecuentes:** Usar `=` en lugar de `==`. Olvidar los dos puntos o la indentación.
- **Verificación:** Con 7 imprime impar; con 10, par; con 0, par; con -3, impar.

### S3-E3 · ¿Puede votar?

**Enunciado:**

> Ejercicio 3
>
> Evalúa si una persona puede votar (edad >= 16).

- **Objetivo:** Escribir una condición con un operador relacional y cubrir ambos casos.
- **Pista 1:** Guarda la edad en una variable y escribe una condición con `if` usando la comparación del enunciado.
- **Pista 2:** ¿Qué se imprime si la condición no se cumple? Agrega `else`.
- **Pista 3:** Prueba el caso límite: 16 años.
- **Errores frecuentes:** Usar `>` en lugar de `>=` y dejar afuera a quien tiene 16.
- **Verificación:** Con 16 puede votar; con 15, no; con 40, sí.

### S3-E4 · Números del 1 al 10 con for

**Enunciado:**

> Ejercicio 4
>
> Imprime los números del 1 al 10.

- **Objetivo:** Recorrer una secuencia con `for` y `range()`.
- **Pista 1:** `range()` genera una secuencia de números para recorrer con `for`. ¿Incluye el número final?
- **Pista 2:** Si el final no se incluye, ¿qué número debes poner para llegar a 10?
- **Pista 3:** Imprime la variable del bucle en cada vuelta.
- **Errores frecuentes:** Usar `range(10)`, que va de 0 a 9.
- **Verificación:** Se imprimen 10 líneas, del 1 al 10.

### S3-E5 · Cuenta regresiva con while

**Enunciado:**

> Ejercicio 5
>
> Imprime los números del 10 al 1 usando while.

- **Objetivo:** Escribir un bucle `while` con valor inicial, condición y actualización.
- **Pista 1:** Con `while` necesitas tres cosas: un valor inicial, una condición y un cambio de la variable en cada vuelta.
- **Pista 2:** Si cuentas hacia abajo, ¿la variable sube o baja en cada vuelta?
- **Pista 3:** ¿Qué condición deja de cumplirse justo después de imprimir 1?
- **Errores frecuentes:** Olvidar actualizar la variable: el bucle no termina (hay que interrumpir el kernel).
- **Verificación:** Se imprimen 10 líneas, del 10 al 1, y el programa termina.

### S3-E6 · Saltar múltiplos de 3 con continue

**Enunciado:**

> Ejercicio 6
>
> Recorre números del 1 al 10 y salta los múltiplos de 3 utilizando `continue`.

- **Objetivo:** Usar `continue` para saltear una vuelta de un bucle.
- **Pista 1:** Recorre los números con `for` y, dentro del bucle, pregunta si el número es múltiplo de 3 con el operador de resto.
- **Pista 2:** `continue` saltea el resto de la vuelta actual: ¿va antes o después del `print`?
- **Pista 3:** La condición de múltiplo de 3 es que el resto de dividir por 3 sea 0.
- **Errores frecuentes:** Poner `continue` después del `print`: no saltea nada.
- **Verificación:** Se imprimen 1, 2, 4, 5, 7, 8 y 10 (7 números).

### S3-E7 · Tablas de multiplicar del 1 al 3

**Enunciado:**

> Ejercicio 7
>
> Genera una tabla de multiplicar del 1 al 3.

- **Objetivo:** Usar bucles anidados.
- **Pista 1:** Necesitas dos bucles, uno dentro del otro: el de afuera recorre las tablas (del 1 al 3) y el de adentro, los multiplicadores.
- **Pista 2:** Decide hasta qué multiplicador llega cada tabla (por ejemplo, hasta 10) y usa `range()` en consecuencia.
- **Pista 3:** Imprime cada línea con el formato `2 x 3 = 6`.
- **Errores frecuentes:** Indentar mal el bucle interno: queda fuera del externo.
- **Verificación:** Si cada tabla llega hasta 10, se imprimen 30 líneas y la última es 3 x 10 = 30.
