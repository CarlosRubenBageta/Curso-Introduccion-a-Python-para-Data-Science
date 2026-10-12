---
exported: 2026-05-07T00:26:09.181Z
source: NotebookLM
type: note
title: "Creación de Variables Dummy en Python"
---

# Creación de Variables Dummy en Python

导出时间: 6/5/2026, 09:26:09

---

## Creación de variables Dummy

### Explicación

En el análisis de datos y el modelado estadístico, muchas variables de interés no son numéricas, sino **categóricas** (como el sexo de una persona, su nivel de estudios o el género de una película). Dado que la mayoría de los algoritmos de modelado matemático y aprendizaje automático requieren entradas numéricas, es necesario transformar estas categorías en una representación que la computadora pueda procesar. Esta transformación se conoce comúnmente como la creación de **variables dummy** o **variables indicadoras**, y en el ámbito del aprendizaje automático también se le llama **one-hot encoding**.

El concepto consiste en convertir una columna que posee k valores distintos en una matriz o DataFrame que tiene k columnas. En cada una de estas nuevas columnas, se asigna un valor de **1** si la observación original pertenecía a esa categoría y un **0** en caso contrario.

Existen casos más complejos donde una sola fila puede pertenecer a múltiples categorías simultáneamente (por ejemplo, una película que es a la vez "Acción" y "Aventura"). En estas situaciones, las categorías suelen estar codificadas en una cadena de texto separada por un delimitador (como una barra vertical `|`). Para procesar estos datos, se utilizan herramientas específicas que expanden cada etiqueta posible en su propia columna indicadora.

Además, al integrar estas nuevas columnas en un conjunto de datos principal, es una práctica recomendada añadir un **prefijo** al nombre de las columnas generadas. Esto facilita la identificación de la variable original de la cual provienen las categorías y mantiene el orden dentro del DataFrame resultante.

\--------------------------------------------------------------------------------

### Ejemplos Contextualizados

**Ejemplo Teórico (basado en el procesamiento de claves):**Supongamos un conjunto de datos simple con una columna llamada "Clave" que contiene los valores `['b', 'b', 'a', 'c', 'a', 'b']`. Al aplicar la función de creación de dummies, el sistema identifica tres categorías únicas: 'a', 'b' y 'c'. El resultado será un nuevo DataFrame con tres columnas etiquetadas como 'a', 'b' y 'c'. En la primera fila (que originalmente era 'b'), la columna 'b' tendrá un 1, mientras que 'a' y 'c' tendrán 0.

**Ejemplo Práctico (aplicado al análisis demográfico):**En una encuesta de salud, los encuestadores registran el sexo de los participantes como "Masculino" o "Femenino". Para realizar una regresión lineal que evalúe el impacto del sexo en el peso, el analista transforma esta variable categórica. Se generan dos columnas: `sexo_femenino` y `sexo_masculino`. Si un participante es hombre, su fila mostrará un 1 en la columna masculina y un 0 en la femenina, permitiendo que el modelo estadístico realice cálculos numéricos sobre esta información.

\--------------------------------------------------------------------------------

### Ejercicio 1

Dado un objeto de tipo Series llamado `estudios` que contiene los valores: `['Grado', 'Posgrado', 'Grado', 'Doctorado', 'Posgrado']`. Se solicita generar la matriz de variables indicadoras correspondiente.

**Guía de resolución:**Debe utilizarse la función `pd.get_dummies(estudios)`. El resultado será un DataFrame con 5 filas y 3 columnas correspondientes a las categorías únicas presentes en la serie. Verifique que cada fila contenga un solo 1 indicando la categoría correcta.

\--------------------------------------------------------------------------------

### Ejercicio 2

Dado un DataFrame llamado `datos_ventas` que tiene las columnas `ID_Venta` (numérico) y `Canal` (categórico con valores: 'Online', 'Tienda', 'Telefónico'). Se requiere crear las variables dummy para la columna `Canal`, pero asegurándose de que las nuevas columnas tengan el prefijo "Venta" y que se unan al DataFrame original descartando la columna categórica inicial.

**Guía de resolución:**Primero, genere las dummies usando `pd.get_dummies(datos_ventas['Canal'], prefix='Venta')`. Luego, utilice el método `.join()` para combinar este resultado con `datos_ventas[['ID_Venta']]` (seleccionando solo la columna numérica). Finalmente, verifique que la columna original 'Canal' ya no esté presente y que existan columnas como `Venta_Online`.

\--------------------------------------------------------------------------------

### Ejercicio 3

Dado un conjunto de datos de habilidades de programadores donde una columna llamada `Lenguajes` contiene etiquetas múltiples en formato de cadena, por ejemplo: `"Python|SQL"`, `"R|Python"`, `"SQL"`. Se solicita crear una matriz indicadora que separe cada lenguaje en su propia columna, identificando la presencia de cada uno de forma individual.

**Guía de resolución:**Para este caso de membresía múltiple, no se usa la función general, sino el método de acceso a cadenas de la serie: `df['Lenguajes'].str.get_dummies('|')`. El sistema detectará las tres etiquetas únicas (Python, R, SQL) y creará columnas para cada una. Una fila que originalmente contenía `"Python|SQL"` tendrá un 1 tanto en la columna `Python` como en la columna `SQL`.