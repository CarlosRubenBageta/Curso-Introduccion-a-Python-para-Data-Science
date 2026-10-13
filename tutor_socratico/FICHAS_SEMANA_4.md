# Fichas de ejercicios · Semana 4 (pandas)

Base de conocimiento del tutor socrático. Cada ficha corresponde a un ejercicio de los notebooks _v4 de la Semana 4.

- **Código:** `S4-P1-E14` = Semana 4, primera parte, ejercicio 14. P1 = `Semana_4_Introduccion_a_pandas_v4.ipynb`; P2 = `Semana_4_Introduccion_a_pandas_segunda_parte_v4.ipynb`.
- **Nivel de protección:** todos los ejercicios de esta semana son PRÁCTICA.
- **Pistas:** se entregan de a una y en orden. La Pista 1 coincide con la guía del notebook.
- **Verificación:** criterio para que el estudiante compruebe su resultado y para que el tutor revise el intento.
- **Alternativa:** solo puede comentarse después de que el ejercicio pasó la verificación.
- Las fichas no incluyen la solución en código a propósito.


## P1 · Introducción a pandas (primera parte)

### S4-P1-E1 · Crear una Serie con índice propio

**Enunciado:**

> Crea una Serie llamada `gastos` que contenga los valores `200, 500, 150, 400` y asígnales los índices `"Lunes", "Martes", "Miércoles", "Jueves"`.

- **Objetivo:** Construir una Serie a partir de una lista de valores y asignarle etiquetas de índice.
- **Pista 1:** Utiliza el constructor `pd.Series()` pasando la lista de valores y el argumento `index` con los nombres de los días.
- **Pista 2:** ¿Qué estructura de Python usas para pasar los cuatro valores? ¿Y para las cuatro etiquetas?
- **Pista 3:** ¿Coincide la cantidad de valores con la cantidad de etiquetas? Si no coincide, ¿qué error esperas?
- **Errores frecuentes:** Longitudes distintas entre valores e índice (`ValueError`). Escribir `pd.series` en minúscula u olvidar `import pandas as pd`.
- **Verificación:** `gastos['Martes']` devuelve 500 y `gastos.index` muestra los cuatro días en orden.

### S4-P1-E2 · Filtrar una Serie con una máscara booleana

**Enunciado:**

> Dada la Serie anterior, extrae únicamente los días en los que el gasto fue superior a 300.

- **Objetivo:** Construir una condición que devuelve True/False y usarla para filtrar la Serie.
- **Pista 1:** Una comparación aplicada a una Serie devuelve otra Serie de True/False. ¿Qué obtienes si comparas `gastos` con 300?
- **Pista 2:** Esa Serie booleana puede ir dentro de los corchetes de la Serie original para quedarse solo con los elementos True.
- **Pista 3:** ¿Qué etiquetas tienen True en la máscara? Esas son las que deben quedar en el resultado.
- **Errores frecuentes:** Quedarse con la máscara (True/False) en lugar de los valores filtrados. Recorrer la Serie con un bucle `for` en lugar de filtrar.
- **Verificación:** El resultado tiene 2 elementos: Martes (500) y Jueves (400).

### S4-P1-E3 · Alineación de Series por índice

**Enunciado:**

> Crea una segunda Serie `ingresos` con los valores `1000` para `"Lunes"` y `1200` para `"Viernes"`. Calcula el saldo final restando `gastos` a `ingresos`. Explica qué sucede con los días que no coinciden.

- **Objetivo:** Comprender que pandas opera alineando etiquetas y produce NaN donde falta un operando, y explicarlo con sus palabras.
- **Pista 1:** Crea la Serie `ingresos` con su propio índice. Antes de restar, predice cuántos elementos tendrá el resultado.
- **Pista 2:** Compara los índices de ambas Series: ¿qué días aparecen en las dos y cuáles en una sola?
- **Pista 3:** Si a un día le falta uno de los dos valores, ¿qué resultado puede dar pandas para ese día?
- **Errores frecuentes:** Esperar que la resta se haga posición por posición. Pensar que los NaN son un error del código.
- **Verificación:** El resultado tiene 5 etiquetas. Solo Lunes tiene valor (800); los otros cuatro días quedan en NaN. La explicación del porqué la redacta el estudiante: el tutor no la da.
- **Alternativa:** El método `.sub()` con el parámetro `fill_value` permite tratar como 0 el valor faltante.

### S4-P1-E4 · Seleccionar una columna y las primeras filas

**Enunciado:**

> Tienes un DataFrame con datos de estudiantes: `Nombre, Nota, Asistencia`. ¿Cómo mostrarías únicamente la columna de las Notas y las primeras 3 filas?

- **Objetivo:** Seleccionar una columna de un DataFrame y limitar la cantidad de filas mostradas.
- **Pista 1:** Hay dos operaciones: elegir la columna y quedarte con las primeras filas. ¿Cuál haces primero?
- **Pista 2:** Una columna se selecciona con corchetes y su nombre. Existe un método que devuelve las primeras filas.
- **Pista 3:** Ese método muestra 5 filas por defecto: ¿qué le pasas para que muestre 3?
- **Errores frecuentes:** Usar `.head()` sin argumento (muestra 5 filas). Seleccionar también `Nombre` cuando solo se pide `Nota`.
- **Verificación:** El resultado tiene 3 valores de la columna `Nota`. Si usó `df['Nota']` obtiene una Serie y con `df[['Nota']]` un DataFrame: pedir que explique la diferencia.

### S4-P1-E5 · Filtrar con dos condiciones

**Enunciado:**

> Tienes un DataFrame de ventas con columnas `Producto, Ventas, Region`. Filtra el DataFrame para obtener todas las filas donde la `Region` sea "Norte" **y** las `Ventas` sean mayores a 5000.

- **Objetivo:** Combinar dos condiciones booleanas con `&` y paréntesis.
- **Pista 1:** Escribe cada condición por separado y comprueba que cada una devuelve True/False.
- **Pista 2:** Para combinar condiciones sobre columnas se usa el operador `&`, no la palabra `and`.
- **Pista 3:** ¿Qué error aparece si quitas los paréntesis de cada condición? ¿Qué evalúa Python primero?
- **Errores frecuentes:** Usar `and` (error de valor de verdad ambiguo). Olvidar los paréntesis. Escribir 'norte' en minúscula.
- **Verificación:** Todas las filas del resultado cumplen `Region == 'Norte'` y `Ventas > 5000` (se puede comprobar con `.all()`).

### S4-P1-E6 · Columna derivada, orden y promedio por grupo

**Enunciado:**

> A partir de un DataFrame de empleados con columnas `Nombre, Salario_Mensual, Departamento`, realiza lo siguiente:
>
> - Crea una nueva columna llamada `Salario_Anual` (multiplicando el mensual por 12).
>
> - Ordena el DataFrame de mayor a menor según el `Salario_Anual`.
>
> - Obtén el salario promedio por `Departamento`.

- **Objetivo:** Crear una columna calculada, ordenar con `sort_values` y calcular un promedio por grupo.
- **Pista 1:** Resuelve una tarea por vez. Para crear la columna, asigna a `df['Salario_Anual']` una operación sobre la columna mensual.
- **Pista 2:** Para ordenar hay un método que empieza con `sort_` y un parámetro que controla el sentido. Para el promedio por departamento, piensa en «agrupar por».
- **Pista 3:** ¿Qué valor del parámetro de sentido ordena de mayor a menor? Después de agrupar, ¿sobre qué columna calculas la media?
- **Errores frecuentes:** Ordenar sin guardar el resultado. Calcular la media del grupo sobre todas las columnas: con columnas de texto da `TypeError` en pandas 2.
- **Verificación:** `Salario_Anual` es 12 veces `Salario_Mensual` en todas las filas; la primera fila tiene el salario anual más alto; el promedio tiene una fila por departamento.

### S4-P1-E7 · Leer un CSV con parámetros

**Enunciado:**

> Se te ha proporcionado un archivo llamado `datos_clima.csv` que contiene información meteorológica. El archivo tiene una fila de comentarios en la línea 0 y utiliza el carácter punto y coma (`;`) como separador. Escribe el código para cargar este archivo en un DataFrame llamado `clima`, asegurándote de que la columna "Fecha" se convierta en el índice del DataFrame.

- **Objetivo:** Usar los parámetros de `pd.read_csv()` para separador, filas a omitir e índice.
- **Pista 1:** Deberás utilizar `pd.read_csv()`. Los argumentos clave son `sep=';'` para el delimitador, `skiprows=` para omitir el comentario inicial e `index_col='Fecha'` para el índice.
- **Pista 2:** Abre el archivo en un editor de texto: ¿cuántas filas hay antes de los encabezados?
- **Pista 3:** El nombre en `index_col` debe coincidir exactamente con el encabezado, incluidas las mayúsculas.
- **Errores frecuentes:** `KeyError` por escribir 'fecha' en lugar de 'Fecha'. Olvidar `sep`: todo queda en una sola columna.
- **Verificación:** `clima.index.name` es 'Fecha' y `clima.shape` muestra más de una columna.

### S4-P1-E8 · Procesar un archivo por fragmentos

**Enunciado:**

> Imagina que recibes un archivo de texto masivo llamado `transacciones_2024.txt` que supera la memoria RAM disponible en tu equipo. El archivo utiliza espacios en blanco variables como separador y tiene valores marcados como "SIN_DATO" que deben tratarse como nulos. Escribe un script que procese el archivo en fragmentos de 5,000 filas y calcule la suma total de la columna "monto" recorriendo todos los fragmentos.

- **Objetivo:** Leer un archivo grande con `chunksize` y acumular un resultado en un bucle.
- **Pista 1:** Utiliza `pd.read_csv()` con `chunksize=5000` para obtener un iterador, `sep='\s+'` para los espacios variables y `na_values=['SIN_DATO']`. Dentro de un `for`, acumula la suma de «monto» en una variable externa.
- **Pista 2:** ¿Qué tipo de objeto devuelve `read_csv` con `chunksize`? Compruébalo con `type()`.
- **Pista 3:** ¿Dónde se crea la variable acumuladora: antes o dentro del bucle? ¿Qué pasa en cada caso?
- **Errores frecuentes:** Inicializar el acumulador dentro del bucle. Usar `sep=' '` en lugar de `'\s+'`. Si «SIN_DATO» no se lee como nulo, la columna queda como texto y la suma falla.
- **Verificación:** Con un archivo pequeño de prueba, la suma por fragmentos coincide con la suma leyendo el archivo completo.

### S4-P1-E9 · Migrar de Excel a Parquet

**Enunciado:**

> Como parte de un proceso de optimización, necesitas migrar un conjunto de datos que actualmente está en formato Excel (`inventario_viejos.xlsx`) a un formato binario más eficiente para futuras lecturas rápidas en un entorno de computación distribuida. Carga la hoja llamada "Stock_Actual" del archivo Excel y guárdala localmente en formato Apache Parquet bajo el nombre `inventario_optimizado.parquet`.

- **Objetivo:** Leer una hoja específica de Excel y guardarla en formato Parquet.
- **Pista 1:** Utiliza `pd.read_excel()` con `sheet_name="Stock_Actual"` y luego `.to_parquet('nombre_archivo.parquet')`. Parquet suele requerir `pyarrow` o `fastparquet`.
- **Pista 2:** Si aparece un `ImportError`, lee el mensaje: ¿qué librería falta?
- **Pista 3:** El valor de `sheet_name` debe coincidir exactamente con el nombre de la hoja.
- **Errores frecuentes:** Falta `openpyxl` (lectura de .xlsx) o `pyarrow` (Parquet). Nombre de hoja mal escrito.
- **Verificación:** `pd.read_parquet('inventario_optimizado.parquet')` devuelve la misma forma (`.shape`) que el DataFrame leído del Excel.

### S4-P1-E10 · Inspección inicial de un DataFrame

**Enunciado:**

> Dado el DataFrame de pandas generado `df_ventas`, que contiene las columnas `producto`, `cantidad`, `precio_unitario` y `fecha`, realiza una inspección inicial completa para identificar la salud de los datos. El objetivo es obtener un resumen de los tipos de datos, verificar si hay valores nulos en la columna `precio_unitario` y obtener las métricas estadísticas básicas de las columnas numéricas.

- **Objetivo:** Usar los métodos básicos de inspección y saber qué responde cada uno.
- **Pista 1:** Usa `.head()` y `.tail()`, el atributo `.shape`, `.info()`, `.isna().sum()` sobre la columna de interés y `.describe()`.
- **Pista 2:** ¿Qué diferencia hay entre lo que muestra `.info()` y lo que muestra `.describe()`?
- **Pista 3:** Para los nulos de una sola columna, selecciona primero la columna y luego cuenta.
- **Errores frecuentes:** Escribir `.shape()`: es un atributo y con paréntesis da `TypeError`. Esperar que `.describe()` muestre columnas de texto (por defecto no lo hace).
- **Verificación:** El estudiante puede responder: cuántas filas y columnas hay, el tipo de cada columna y cuántos nulos tiene `precio_unitario`.

### S4-P1-E11 · Métrica derivada, orden y histograma de un subconjunto

**Enunciado:**

> Supongamos que trabajas con un conjunto de datos sobre indicadores económicos por estado. Dispones de un DataFrame con las columnas `estado`, `población`, `gdp` y `tasa_empleo`. Se te pide que realices una inspección segmentada: primero, debes ordenar los datos de forma descendente según el `gdp` por habitante (necesitarás crear esta métrica) y luego visualizar mediante un histograma la distribución de la `tasa_empleo` únicamente para los 10 estados con mayor población.

- **Objetivo:** Crear una métrica, ordenar, seleccionar un top 10 por otro criterio y graficar un histograma.
- **Pista 1:** Genera el dataset con IA; crea la columna dividiendo `gdp` entre `población`; ordena con `.sort_values()` y `ascending=False`; filtra los 10 estados de mayor población con `.nlargest()` o ordenando y recortando; grafica el histograma de `tasa_empleo` sobre ese subconjunto.
- **Pista 2:** Relee la consigna: ¿el top 10 se elige por PIB per cápita o por población?
- **Pista 3:** El histograma es de `tasa_empleo` solo para el subconjunto, no para todo el DataFrame.
- **Errores frecuentes:** Confundir el criterio de orden con el criterio del top 10. Escribir `poblacion` sin tilde si la columna la tiene.
- **Verificación:** El subconjunto tiene 10 filas y son los estados de mayor población; el histograma tiene título y ejes con nombre.

### S4-P1-E12 · Detectar y graficar valores atípicos

**Enunciado:**

> Imagina que recibes un dataset de sensores industriales que registra la temperatura (`temp`) y la presión (`pres`) cada minuto. Durante la inspección visual mediante un gráfico de dispersión, notas que existen puntos que se alejan drásticamente del grupo principal de datos. Desarrolla un procedimiento lógico para inspeccionar estos "outliers": identifica programáticamente aquellas filas donde la temperatura sea superior a 3 desviaciones estándar respecto a la media y genera un nuevo gráfico de dispersión donde estos puntos atípicos se diferencien visualmente del resto.

- **Objetivo:** Calcular un umbral con media y desvío, filtrar los atípicos y diferenciarlos en un gráfico.
- **Pista 1:** Genera el dataset con IA; calcula media y desvío de `temp`; define el umbral media + 3 desvíos; extrae las filas que lo superan; grafica todos los puntos y superpón los atípicos con otro color y marcador.
- **Pista 2:** Calcula el umbral y guárdalo en una variable antes de filtrar: ¿es un número o una columna?
- **Pista 3:** Necesitas dos llamadas a `plt.scatter()`: una con todos los datos y otra solo con los atípicos.
- **Errores frecuentes:** Usar 3 desvíos sin sumar la media. Generar datos sin valores extremos: el filtro queda vacío.
- **Verificación:** Todos los puntos marcados superan el umbral; el gráfico tiene ejes con nombre y una leyenda que distingue ambos grupos.

### S4-P1-E13 · Establecer una columna como índice

**Enunciado:**

> Dado un DataFrame llamado `ventas` con las columnas `['ID_Producto', 'Ciudad', 'Ganancia']`, establezca la columna `ID_Producto` como el índice del objeto y muestre las primeras 5 filas para verificar el cambio.

- **Objetivo:** Usar `set_index` y entender que devuelve un DataFrame nuevo.
- **Pista 1:** Utiliza el método `.set_index('ID_Producto')`. Para que el cambio persista, asigna el resultado o usa `inplace=True`.
- **Pista 2:** ¿Guardaste el resultado de `set_index` en alguna variable?
- **Pista 3:** Después del cambio, ¿`ID_Producto` aparece como columna o como índice?
- **Errores frecuentes:** No asignar el resultado. `KeyError` por un nombre de columna mal escrito.
- **Verificación:** `ventas.index.name` es 'ID_Producto' y esa columna ya no está en `ventas.columns`.

### S4-P1-E14 · Convertir un índice jerárquico en columnas

**Enunciado:**

> Suponga que tiene un DataFrame con un índice jerárquico basado en `['Año', 'Mes']`. Escriba el código para convertir este índice nuevamente en columnas estándar del DataFrame, asegurándose de que el índice original sea reemplazado por los números enteros por defecto.

- **Objetivo:** Usar `reset_index` para devolver los niveles del índice a columnas.
- **Pista 1:** Aplica el método `.reset_index()`. Moverá los niveles 'Año' y 'Mes' del índice a columnas normales.
- **Pista 2:** Para probarlo necesitas un DataFrame con índice jerárquico: créalo primero con `set_index` sobre dos columnas.
- **Pista 3:** ¿Qué haría el parámetro `drop=True`? ¿Por qué no sirve en este caso?
- **Errores frecuentes:** No asignar el resultado. Usar `drop=True` y perder los niveles.
- **Verificación:** 'Año' y 'Mes' están en `columns` y el índice va de 0 a n-1.

### S4-P1-E15 · Índice jerárquico con orden mixto

**Enunciado:**

> Cree un índice jerárquico para un DataFrame de `empleados` utilizando las columnas `Departamento` y `ID_Empleado`. Una vez creado, ordene el índice de forma descendente para el primer nivel y ascendente para el segundo nivel.

- **Objetivo:** Crear un MultiIndex y ordenarlo con un sentido distinto en cada nivel.
- **Pista 1:** Construye el índice con `set_index` pasando ambas columnas y luego ordénalo con `sort_index`. ¿Qué tipo de valor debe recibir `ascending` para indicar un orden distinto en cada nivel?
- **Pista 2:** Revisa en la documentación de `sort_index` qué aceptan los parámetros `level` y `ascending`.
- **Pista 3:** Si `ascending` recibe una lista con un valor por nivel, ¿qué valores necesita este caso?
- **Errores frecuentes:** Ordenar un solo nivel. Usar `ascending=False` para ambos niveles.
- **Verificación:** El primer departamento mostrado es el último alfabéticamente y, dentro de él, los ID van de menor a mayor.

### S4-P1-E16 · Seleccionar varias columnas

**Enunciado:**

> Dado un DataFrame `estudiantes`, seleccione únicamente las columnas `Nombre` y `Promedio` y guarde el resultado en una nueva variable llamada `resumen`.

- **Objetivo:** Seleccionar varias columnas pasando una lista dentro de los corchetes.
- **Pista 1:** Para seleccionar varias columnas, el selector `[]` debe recibir una lista. ¿Cómo queda la expresión con la lista dentro de los corchetes de selección?
- **Pista 2:** Prueba `estudiantes['Nombre']` y mira su `type()`. ¿Es lo que necesitas?
- **Pista 3:** ¿Qué estructura de Python agrupa varios nombres? Ponla dentro de los corchetes.
- **Errores frecuentes:** `estudiantes['Nombre', 'Promedio']` da `KeyError`.
- **Verificación:** `resumen.columns` muestra solo `Nombre` y `Promedio`, y `type(resumen)` es DataFrame.

### S4-P1-E17 · Seleccionar un rango de fechas con loc

**Enunciado:**

> En un DataFrame `clima` donde el índice son fechas, seleccione todas las filas correspondientes al rango entre '2023-01-01' y '2023-01-15' para la columna `Temperatura`.

- **Objetivo:** Seleccionar por etiquetas un rango de filas y una columna con `.loc`.
- **Pista 1:** Como el índice son fechas (etiquetas), usa el selector por etiquetas: primero el rango de filas, luego la columna. Con etiquetas el extremo final se incluye, y el índice debe estar ordenado.
- **Pista 2:** `.loc` recibe `[filas, columnas]`; un rango de filas se escribe `inicio:fin`.
- **Pista 3:** ¿El índice es de fechas o de texto? Compruébalo con `clima.index.dtype`.
- **Errores frecuentes:** Usar `iloc` con fechas. Índice desordenado: error o resultado vacío. Suponer que el extremo final se excluye.
- **Verificación:** La primera y la última fecha del resultado son 2023-01-01 y 2023-01-15.

### S4-P1-E18 · Seleccionar por posición con iloc

**Enunciado:**

> Extraiga un subconjunto del DataFrame `inventario` que contenga desde la fila 10 hasta la 20 (inclusive) y las tres primeras columnas, utilizando exclusivamente sus posiciones numéricas.

- **Objetivo:** Seleccionar filas y columnas por posición y entender que el extremo final se excluye.
- **Pista 1:** Usa el selector por posición. Con posiciones el extremo final no se incluye: ¿qué número escribes para que la fila 20 quede incluida?
- **Pista 2:** `.iloc` recibe `[filas, columnas]`, cada uno como `inicio:fin`.
- **Pista 3:** Las tres primeras columnas van desde la posición 0 hasta… ¿cuál?
- **Errores frecuentes:** Escribir `10:20` y dejar afuera la fila 20. Usar `loc` y seleccionar por etiqueta.
- **Verificación:** `subconjunto.shape` es `(11, 3)`.

### S4-P1-E19 · Filtrar con dos condiciones

**Enunciado:**

> A partir de un DataFrame `productos`, filtre y muestre todos aquellos cuyo `Precio` sea mayor a 100 y cuya `Existencia` sea menor a 10.

- **Objetivo:** Combinar dos condiciones con `&` y paréntesis.
- **Pista 1:** Escribe cada condición como una comparación sobre su columna y combínalas con `&`, cada una entre paréntesis. ¿Qué error aparece si omites los paréntesis?
- **Pista 2:** Prueba cada condición por separado y comprueba que devuelve True/False.
- **Pista 3:** Pon la condición combinada dentro de `productos[...]`.
- **Errores frecuentes:** Usar `and`. Omitir los paréntesis.
- **Verificación:** En el resultado, el mínimo de `Precio` es mayor a 100 y el máximo de `Existencia` es menor a 10.

### S4-P1-E20 · Filtrar por pertenencia a una lista

**Enunciado:**

> Dado un DataFrame `vuelos`, seleccione las filas donde el `Destino` sea 'Madrid', 'Barcelona' o 'Sevilla'.

- **Objetivo:** Usar `.isin()` para filtrar por varios valores posibles.
- **Pista 1:** En lugar de encadenar tres comparaciones con `|`, existe un método de las Series que verifica si cada valor pertenece a una lista. Úsalo para construir la máscara.
- **Pista 2:** Busca en la documentación de Series un método cuyo nombre empieza con `is` y que recibe una lista.
- **Pista 3:** Ese método devuelve una máscara booleana: ponla dentro de `vuelos[...]`.
- **Errores frecuentes:** Pasar las ciudades sin lista. Escribir las ciudades con otras mayúsculas o tildes.
- **Verificación:** `resultado['Destino'].unique()` devuelve solo las tres ciudades.

### S4-P1-E21 · Filtrar con query y una variable externa

**Enunciado:**

> Utilizando el método `.query()`, filtre un DataFrame de `nominas` para encontrar empleados del departamento 'Ventas' cuyo salario sea superior a un valor almacenado en una variable de Python llamada `salario_minimo`.

- **Objetivo:** Escribir condiciones en `.query()` y referenciar una variable de Python.
- **Pista 1:** Dentro de la cadena de `.query()` las condiciones se escriben como comparaciones entre columnas y valores, unidas con `&` o `and`. Para referenciar una variable de Python se antepone un símbolo especial: búscalo en la documentación.
- **Pista 2:** Escribe primero la consulta solo con la condición del departamento y comprueba que funciona; luego agrega la del salario.
- **Pista 3:** Si escribes `salario_minimo` sin nada delante, pandas lo busca como columna: ¿qué error obtienes?
- **Errores frecuentes:** Mezclar comillas simples y dobles. Error de variable indefinida por olvidar el símbolo.
- **Verificación:** Al cambiar el valor de `salario_minimo` cambia la cantidad de filas del resultado.


## P2 · Introducción a pandas (segunda parte)

### S4-P2-E1 · Contar nulos y eliminar filas con nulos en una columna

**Enunciado:**

> Dado un DataFrame llamado `ventas` que contiene columnas de `producto`, `precio` y `fecha_venta`, escriba el código necesario para identificar cuántos valores nulos existen en cada columna y luego elimine únicamente las filas donde el `precio` sea nulo.

- **Objetivo:** Contar nulos por columna y eliminar filas según los nulos de una sola columna.
- **Pista 1:** El conteo encadena dos métodos: uno marca los nulos y otro los suma por columna. Para eliminar, `dropna` tiene un parámetro que restringe la búsqueda de nulos a ciertas columnas.
- **Pista 2:** `dropna()` sin argumentos elimina filas con nulos en cualquier columna: ¿es lo que pide la consigna?
- **Pista 3:** ¿Guardaste el resultado de `dropna`?
- **Errores frecuentes:** Usar `dropna()` general y perder filas con nulos en otras columnas. No asignar el resultado.
- **Verificación:** Después de eliminar, `ventas['precio'].isna().sum()` es 0, aunque otras columnas sigan teniendo nulos.

### S4-P2-E2 · Rellenar nulos con la media

**Enunciado:**

> Suponga un conjunto de datos de `estudiantes` con las columnas `nombre` y `calificacion_final`. Muchos estudiantes faltaron al examen, dejando su calificación como `NaN`. Implemente una solución que reemplace todos los valores nulos en la columna `calificacion_final` con la calificación media del grupo, asegurándose de que el cambio se refleje en el DataFrame original.

- **Objetivo:** Calcular un estadístico y usarlo para imputar nulos, asegurando que el cambio quede en el DataFrame.
- **Pista 1:** Calcula la media de la columna y guárdala en una variable. Usa `fillna` con ese valor y asigna el resultado de vuelta a la columna; evita `inplace=True` sobre una columna.
- **Pista 2:** `fillna` devuelve una Serie nueva: ¿dónde la guardas?
- **Pista 3:** ¿La media se calcula antes o después de rellenar? ¿Por qué importa?
- **Errores frecuentes:** `df['col'].fillna(..., inplace=True)`: advertencia en pandas 2, sin efecto en pandas 3.
- **Verificación:** No quedan nulos y la media de la columna no cambia. Pedir que explique por qué no cambia.

### S4-P2-E3 · Propagar el último valor válido con límite

**Enunciado:**

> En un registro meteorológico de temperaturas diarias, existen vacíos ocasionados por fallos temporales en los sensores. Dado que las temperaturas suelen ser similares a las del día anterior, utilice un método de pandas para rellenar los nulos propagando el último valor válido observado hacia adelante, limitando esta acción a un máximo de dos días consecutivos de fallos.

- **Objetivo:** Rellenar nulos hacia adelante limitando la cantidad de nulos consecutivos.
- **Pista 1:** pandas tiene un método específico para propagar el último valor válido hacia adelante. Revisa qué parámetro limita la cantidad de nulos consecutivos que rellena.
- **Pista 2:** El nombre del método viene de *forward fill*.
- **Pista 3:** Arma una serie de prueba como `[20, NaN, NaN, NaN, 25]` y predice el resultado antes de ejecutar.
- **Errores frecuentes:** Usar `fillna(method='ffill')`: deprecado en pandas 2, error en pandas 3. Usar el relleno hacia atrás.
- **Verificación:** Con 3 nulos seguidos, el tercero sigue siendo NaN.

### S4-P2-E4 · Identificar y eliminar filas duplicadas

**Enunciado:**

> Un sistema de registros hospitalarios ha generado múltiples entradas para el mismo paciente en una misma consulta. Dado el DataFrame `consultas` con columnas `id_paciente`, `fecha` y `diagnostico`, identifique si existen filas exactamente iguales y elimínelas conservando solo la primera ocurrencia.

- **Objetivo:** Contar filas exactamente repetidas y eliminarlas conservando la primera.
- **Pista 1:** La consigna pide primero identificar. Cuenta las filas repetidas con el método que las marca y luego elimínalas con su método par. Revisa qué hacen por defecto `subset` y `keep`.
- **Pista 2:** `duplicated()` devuelve True/False por fila: ¿cómo cuentas los True?
- **Pista 3:** ¿Qué aparición conserva `drop_duplicates` por defecto? Compruébalo en la documentación.
- **Errores frecuentes:** Contar con `len()` sobre la máscara (cuenta todas las filas). No asignar el resultado.
- **Verificación:** El largo del DataFrame baja exactamente en la cantidad de duplicados contados.

### S4-P2-E5 · Eliminar duplicados conservando el registro más reciente

**Enunciado:**

> En un DataFrame de `clientes` que incluye `correo_electronico` y `fecha_registro`, se han detectado correos duplicados. Escriba una instrucción que elimine los duplicados basados únicamente en la columna `correo_electronico`, pero asegurándose de conservar el registro con la fecha de registro más reciente (la última observada).

- **Objetivo:** Eliminar duplicados según una columna y decidir qué aparición conservar.
- **Pista 1:** Ordena primero por `fecha_registro`. Luego usa `drop_duplicates` restringido a la columna del correo: ¿qué valor de `keep` conserva la última aparición?
- **Pista 2:** Si ordenas de forma ascendente, ¿dónde queda el registro más reciente de cada correo?
- **Pista 3:** `keep` acepta 'first', 'last' o False: ¿cuál corresponde?
- **Errores frecuentes:** No ordenar antes: 'last' sería el último del archivo, no el más reciente. Fechas guardadas como texto: conviene convertirlas con `pd.to_datetime`.
- **Verificación:** `clientes['correo_electronico'].is_unique` es True.

### S4-P2-E6 · Función que devuelve las filas duplicadas

**Enunciado:**

> Cree una función que reciba un DataFrame, identifique qué filas tienen el mismo valor en un conjunto de columnas clave y devuelva un nuevo DataFrame que contenga únicamente las filas que se consideran duplicadas (excluyendo la primera aparición), para que el equipo de auditoría pueda revisarlas.

- **Objetivo:** Escribir una función que usa `duplicated` como máscara con columnas clave recibidas como parámetro.
- **Pista 1:** `duplicated` devuelve una Serie booleana que sirve como máscara. La función debe recibir la lista de columnas clave y pasarla al parámetro que restringe la comparación.
- **Pista 2:** Estructura: una función con dos parámetros (el DataFrame y las columnas clave) que devuelve un DataFrame.
- **Pista 3:** Con el valor por defecto de `keep`, ¿qué filas marca `duplicated`? ¿Coincide con lo que pide la consigna?
- **Errores frecuentes:** Devolver la máscara en lugar del DataFrame filtrado. Escribir las columnas fijas dentro de la función en lugar de usar el parámetro.
- **Verificación:** Probada con un DataFrame pequeño con duplicados conocidos, devuelve exactamente esas filas.

### S4-P2-E7 · Reemplazar valores con map

**Enunciado:**

> Dado un DataFrame con una columna `genero` que contiene los valores "M" y "F", utilice un diccionario de mapeo para transformar estos valores a "Masculino" y "Femenino" respectivamente, utilizando el método adecuado para una Serie.

- **Objetivo:** Usar un diccionario de correspondencias con `.map()` sobre una Serie.
- **Pista 1:** Arma un diccionario con los valores actuales como claves y los nuevos como valores, y aplícalo con el método de Series pensado para sustituir por correspondencias.
- **Pista 2:** Ese método recibe el diccionario y devuelve una Serie nueva: asígnala a la columna.
- **Pista 3:** ¿Qué pasaría con un valor que no está en el diccionario? Pruébalo.
- **Errores frecuentes:** Aplicar el método al DataFrame entero. Valores no previstos en el diccionario quedan como NaN.
- **Verificación:** `df['genero'].unique()` muestra solo 'Masculino' y 'Femenino'.

### S4-P2-E8 · Operación por fila con apply

**Enunciado:**

> Usted cuenta con un DataFrame de `empleados` con columnas `salario_base` y `bono`. Utilice una función lambda con el método `apply` para crear una nueva columna llamada `ingreso_total` que sea la suma de las dos columnas anteriores para cada fila.

- **Objetivo:** Usar `apply` con una lambda que opera por filas (`axis=1`).
- **Pista 1:** La lambda recibe una fila completa y devuelve la suma de las dos columnas. Para que `apply` recorra filas y no columnas, revisa el parámetro `axis`.
- **Pista 2:** Dentro de la lambda, accede a cada valor de la fila por el nombre de su columna.
- **Pista 3:** Con `axis=0`, ¿qué recibe la lambda? ¿Por qué aparece un `KeyError`?
- **Errores frecuentes:** Olvidar `axis=1`. Usar `df` cuando el DataFrame se llama `empleados`.
- **Verificación:** El resultado coincide con `empleados['salario_base'] + empleados['bono']`. Preguntar cuál de las dos formas es más simple.
- **Alternativa:** La suma directa de columnas (vectorizada) es más simple y más rápida.

### S4-P2-E9 · Estandarizar una columna con apply

**Enunciado:**

> En un conjunto de datos financieros, se requiere normalizar los valores de una columna `monto`. Aplique una transformación que reste el promedio de la columna y divida el resultado por la desviación estándar a cada elemento de dicha columna, utilizando una sola línea de código con `apply`.

- **Objetivo:** Aplicar la fórmula (x − media) / desvío a cada valor con `apply`.
- **Pista 1:** La lambda recibe cada valor `x`; la fórmula es (x − media) / desvío. Calcula la media y el desvío una sola vez, fuera de la lambda.
- **Pista 2:** Guarda la media y el desvío en dos variables antes de llamar a `apply`.
- **Pista 3:** La lambda solo usa `x` y esas dos variables.
- **Errores frecuentes:** Calcular media y desvío dentro de la lambda: correcto pero se recalcula para cada valor.
- **Verificación:** La columna resultante tiene media cercana a 0 y desvío cercano a 1.
- **Alternativa:** La versión vectorizada `(s - s.mean()) / s.std()` hace lo mismo sin `apply`.

### S4-P2-E10 · Renombrar columnas con un diccionario

**Enunciado:**

> Dado un DataFrame con columnas tituladas `c1`, `c2` y `c3`, cámbieles el nombre a `ID`, `Nombre` y `Edad` respectivamente, asegurándose de que los cambios se guarden en el objeto original.

- **Objetivo:** Usar `rename` con `columns` y un diccionario {viejo: nuevo}.
- **Pista 1:** `rename` recibe en `columns` un diccionario de la forma {nombre_viejo: nombre_nuevo}.
- **Pista 2:** ¿Qué estructura de Python asocia cada nombre viejo con uno nuevo?
- **Pista 3:** `rename` devuelve un DataFrame nuevo: asígnalo o usa `inplace=True`.
- **Errores frecuentes:** Pasar el diccionario sin `columns=`: pandas intenta renombrar el índice y las columnas no cambian, sin error.
- **Verificación:** `df.columns` muestra `ID`, `Nombre` y `Edad`.

### S4-P2-E11 · Normalizar nombres de columnas con una función

**Enunciado:**

> Implemente una solución que transforme automáticamente todos los nombres de las columnas de un DataFrame de modo que no tengan espacios en blanco iniciales o finales y que todos los caracteres estén en minúsculas.

- **Objetivo:** Pasar una función a `rename` para transformar todos los nombres.
- **Pista 1:** Además de un diccionario, `columns` acepta una función que se aplica a cada nombre. Combina dos métodos de cadenas: uno quita espacios en los extremos y otro pasa a minúsculas.
- **Pista 2:** Prueba primero los dos métodos sobre una cadena suelta, por ejemplo `' Nombre '`.
- **Pista 3:** Escribe una lambda que recibe un nombre y devuelve el nombre transformado.
- **Errores frecuentes:** Olvidar asignar el resultado. Quitar todos los espacios en lugar de solo los de los extremos.
- **Verificación:** Con columnas `' Nombre '` y `'EDAD'`, el resultado es `nombre` y `edad`.
- **Alternativa:** `df.columns = df.columns.str.strip().str.lower()` también resuelve la consigna.

### S4-P2-E12 · Renombrar etiquetas del índice

**Enunciado:**

> Suponga que ha transpuesto un DataFrame y ahora sus índices de fila son nombres de países con errores de ortografía. Utilice `rename` con un diccionario para corregir específicamente el índice "Espña" por "España" y "Francia_2" por "Francia".

- **Objetivo:** Usar `rename` con el parámetro `index` para corregir etiquetas de fila.
- **Pista 1:** `rename` tiene un parámetro distinto de `columns` para las etiquetas de fila. Arma el diccionario con los nombres incorrectos como claves.
- **Pista 2:** ¿Cuál es la clave y cuál el valor: el nombre incorrecto o el correcto?
- **Pista 3:** Compara tus claves con `df.index`: deben coincidir exactamente.
- **Errores frecuentes:** Invertir clave y valor. Usar `columns=` en lugar del parámetro del índice.
- **Verificación:** `'Espña' in df.index` es False y `'España' in df.index` es True.

### S4-P2-E13 · Discretizar con límites fijos (cut)

**Enunciado:**

> Usted tiene una lista de `edades = [15, 22, 40, 70, 8, 90]`. Utilice la función `cut` para segmentar estos datos en tres categorías: "Menor", "Adulto" y "Senior", definiendo manualmente los límites en 0, 18, 65 y 100 años.

- **Objetivo:** Usar `pd.cut` con límites y etiquetas definidos manualmente.
- **Pista 1:** Define una lista de 4 límites y otra de 3 etiquetas, y pásalas a `pd.cut` en sus parámetros. ¿Por qué hay un límite más que etiquetas?
- **Pista 2:** Revisa en la documentación los nombres de los parámetros para límites y etiquetas.
- **Pista 3:** Los intervalos son abiertos a izquierda, por ejemplo (0, 18]: ¿en qué categoría cae una edad de 18?
- **Errores frecuentes:** Igual cantidad de límites que de etiquetas (`ValueError`). Valores fuera del rango quedan como NaN.
- **Verificación:** 15 y 8 quedan como Menor; 22 y 40 como Adulto; 70 y 90 como Senior.

### S4-P2-E14 · Discretizar en cuartiles (qcut)

**Enunciado:**

> Dado un DataFrame con la columna `puntaje_examen`, utilice `qcut` para dividir a los estudiantes en 4 grupos iguales (cuartiles) basados en su desempeño, de modo que cada grupo represente el 25% de la clase.

- **Objetivo:** Usar `pd.qcut` para formar grupos de igual tamaño y distinguirlo de `cut`.
- **Pista 1:** `qcut` necesita la columna a dividir y la cantidad de grupos; revisa qué parámetro la indica.
- **Pista 2:** Ese parámetro acepta un entero (cantidad de grupos) o una lista de cuantiles.
- **Pista 3:** ¿Qué entero corresponde a cuartiles?
- **Errores frecuentes:** Usar `cut`: forma intervalos de igual ancho, no de igual cantidad. Muchos valores repetidos: error de límites no únicos.
- **Verificación:** Con `value_counts()`, cada grupo tiene cerca del 25% de los estudiantes. Preguntar qué cambia con `cut` y 4 grupos.

### S4-P2-E15 · Niveles de igual frecuencia numerados del 1 al 5

**Enunciado:**

> En una base de datos de transacciones bancarias, se desea analizar el comportamiento de los clientes según el monto de sus compras. Cree una nueva columna categórica que divida la columna `monto` en 5 bins de igual frecuencia, y asigne como nombres a esos niveles los números del 1 al 5. Obtenga además el conteo de cuántas transacciones hay en cada nivel.

- **Objetivo:** Usar `qcut` con 5 grupos, etiquetarlos del 1 al 5 y contar.
- **Pista 1:** Usa `qcut` con 5 grupos. Para obtener niveles del 1 al 5 hay dos caminos: pasar una lista de etiquetas, o usar `labels=False` (numera desde 0) y ajustar.
- **Pista 2:** Si eliges la lista de etiquetas, ¿cuántos elementos debe tener?
- **Pista 3:** Si eliges `labels=False`, ¿qué operación le falta al resultado para empezar en 1?
- **Errores frecuentes:** Lista de etiquetas con una cantidad distinta de 5. Leer el conteo sin ordenar los niveles.
- **Verificación:** La nueva columna tiene valores del 1 al 5 y el conteo por nivel da cantidades similares.

### S4-P2-E16 · Variables indicadoras (dummies) de una Serie

**Enunciado:**

> Dado un objeto de tipo Series llamado `estudios` que contiene los valores: `['Grado', 'Posgrado', 'Grado', 'Doctorado', 'Posgrado']`. Se solicita generar la matriz de variables indicadoras correspondiente.

- **Objetivo:** Generar la matriz de indicadores de una variable categórica.
- **Pista 1:** pandas tiene una función que convierte una Serie categórica en una columna indicadora por categoría (*dummies*).
- **Pista 2:** Crea primero la Serie `estudios` con los cinco valores.
- **Pista 3:** La función está en `pd` y su nombre empieza con `get_`.
- **Errores frecuentes:** Esperar 1/0: la función devuelve True/False (con `dtype=int` devuelve 1/0).
- **Verificación:** El resultado tiene 5 filas, una columna por categoría distinta y un único True por fila.

### S4-P2-E17 · Dummies con prefijo unidas al DataFrame

**Enunciado:**

> Dado un DataFrame llamado `datos_ventas` que tiene las columnas `ID_Venta` (numérico) y `Canal` (categórico con valores: 'Online', 'Tienda', 'Telefónico'). Se requiere crear las variables dummy para la columna `Canal`, pero asegurándose de que las nuevas columnas tengan el prefijo "Venta" y que se unan al DataFrame original descartando la columna categórica inicial.

- **Objetivo:** Generar dummies con prefijo, unirlas al DataFrame y descartar la columna original.
- **Pista 1:** `get_dummies` tiene un parámetro para anteponer un prefijo a las nuevas columnas. Combina el resultado con la parte del DataFrame que quieres conservar, sin `Canal`.
- **Pista 2:** `join` combina por índice: ¿coinciden los índices de las dummies y de `datos_ventas`?
- **Pista 3:** ¿Cómo quitas `Canal`: seleccionando solo `ID_Venta` o eliminando `Canal`?
- **Errores frecuentes:** Olvidar descartar `Canal`. Esperar `VentaOnline`: el separador por defecto es `_`.
- **Verificación:** `Canal` no está en las columnas y existe `Venta_Online`.
- **Alternativa:** `pd.get_dummies(datos_ventas, columns=['Canal'], prefix='Venta')` resuelve todo en un paso.

### S4-P2-E18 · Dummies de etiquetas múltiples

**Enunciado:**

> Dado un conjunto de datos de habilidades de programadores donde una columna llamada `Lenguajes` contiene etiquetas múltiples en formato de cadena, por ejemplo: `"Python|SQL"`, `"R|Python"`, `"SQL"`. Se solicita crear una matriz indicadora que separe cada lenguaje en su propia columna, identificando la presencia de cada uno de forma individual.

- **Objetivo:** Usar `.str.get_dummies()` cuando una celda contiene varias etiquetas separadas.
- **Pista 1:** `pd.get_dummies` trata cada cadena como una sola categoría, así que "Python|SQL" sería una categoría aparte. Busca en el accesor `.str` un método que separe por un delimitador y genere los indicadores.
- **Pista 2:** ¿Cuál es el separador en esta columna?
- **Pista 3:** El método se usa como `df['Lenguajes'].str.<método>(separador)`.
- **Errores frecuentes:** Usar `pd.get_dummies` y obtener columnas como 'Python|SQL'.
- **Verificación:** La fila "Python|SQL" tiene 1 en Python y en SQL, y 0 en R.

### S4-P2-E19 · Promedio por grupo

**Enunciado:**

> Dado un DataFrame llamado `datos_ventas` que contiene las columnas `Tienda`, `Departamento` y `Ventas_Semanales`, se solicita obtener el promedio de ventas por cada tipo de tienda.

- **Objetivo:** Agrupar por una columna y calcular la media de otra.
- **Pista 1:** Usa `groupby` con `Tienda` como clave y aplica `.mean()` sobre la columna de interés. El resultado es una Serie indexada por tienda.
- **Pista 2:** Selecciona la columna `Ventas_Semanales` después de agrupar.
- **Pista 3:** ¿Qué tipo de objeto obtienes y cuál es su índice?
- **Errores frecuentes:** Calcular la media sobre todas las columnas: `Departamento` es texto y da `TypeError`. Agrupar por la columna numérica.
- **Verificación:** Hay una fila por tienda; el promedio de una tienda coincide con el calculado filtrando esa tienda a mano.

### S4-P2-E20 · Agrupar por dos claves con varias agregaciones

**Enunciado:**

> Dado un conjunto de datos sobre propinas en un restaurante con las columnas `dia`, `fumador`, `total_factura` y `porcentaje_propina`, realice una operación que devuelva simultáneamente el valor máximo, el mínimo y el promedio del porcentaje de propina, agrupando los datos por el día de la semana y la condición de fumador.

- **Objetivo:** Agrupar por dos columnas y aplicar varias funciones con `.agg()`.
- **Pista 1:** Aplica `groupby` con una lista de las columnas `dia` y `fumador`, accede a `porcentaje_propina` y usa `.agg()` con las tres estadísticas pedidas.
- **Pista 2:** `.agg()` recibe una lista con los nombres de las funciones como texto.
- **Pista 3:** ¿Qué estructura tendrá el índice del resultado?
- **Errores frecuentes:** Escribir 'smoker' en lugar de 'fumador' (`KeyError`). Pasar las funciones sin lista.
- **Verificación:** El índice tiene dos niveles (día y fumador) y hay columnas max, min y mean, con max ≥ mean ≥ min en cada fila.

### S4-P2-E21 · Fila de salario máximo por ciudad

**Enunciado:**

> Dado un DataFrame de empleados con las columnas `Nombre`, `Ciudad` y `Salario`, escriba una función que identifique al empleado con el salario más alto de cada ciudad y aplíquela al conjunto de datos utilizando las herramientas de operaciones de grupo.

- **Objetivo:** Escribir una función que opera sobre un grupo y aplicarla con `groupby().apply()`.
- **Pista 1:** Define una función que recibe un grupo y devuelve la fila de salario máximo usando `.loc` con `.idxmax()` sobre `Salario`; agrupa por `Ciudad` e invoca `.apply()` con esa función.
- **Pista 2:** `idxmax` devuelve la etiqueta de la fila con el valor máximo; `.loc` recupera esa fila.
- **Pista 3:** Prueba la función primero con una sola ciudad, filtrada a mano.
- **Errores frecuentes:** Devolver solo el salario y no la fila completa. Advertencia de pandas 2.2+ sobre `apply` y las columnas de agrupación.
- **Verificación:** Hay una fila por ciudad y cada salario coincide con el máximo de esa ciudad (comparar con `groupby(...)['Salario'].max()`).
- **Alternativa:** `df.loc[df.groupby('Ciudad')['Salario'].idxmax()]` resuelve lo mismo sin función auxiliar.

### S4-P2-E22 · Unión izquierda con merge

**Enunciado:**

> Dado el siguiente escenario: Se cuenta con un DataFrame llamado `clientes` que contiene las columnas `ID_Cliente` y `Nombre`, y otro DataFrame llamado `pedidos` con las columnas `ID_Pedido`, `ID_Cliente` y `Monto`. Se desea obtener un listado de todos los pedidos realizados, incluyendo el nombre del cliente correspondiente, pero asegurándose de no perder ningún registro de la tabla `pedidos` incluso si el ID del cliente no se encuentra en la tabla de `clientes`.

- **Objetivo:** Elegir el tipo de unión que conserva todos los registros de una tabla.
- **Pista 1:** Usa `pd.merge`. Para conservar todos los pedidos, la unión es *left* si `pedidos` es el primer argumento o *right* si es el segundo. La clave es `ID_Cliente`.
- **Pista 2:** ¿Cuál es la tabla que no debe perder filas?
- **Pista 3:** Revisa el parámetro `how`: ¿qué valor conserva todas las filas de la tabla izquierda?
- **Errores frecuentes:** Usar el valor por defecto (*inner*) y perder pedidos sin cliente. Invertir el orden de los argumentos sin ajustar `how`.
- **Verificación:** `len(resultado)` es igual a `len(pedidos)` y los pedidos sin cliente tienen `Nombre` en NaN.

### S4-P2-E23 · Concatenar Series como columnas

**Enunciado:**

> Dado el siguiente escenario: Un analista tiene dos Series independientes, `s1` y `s2`. Ambas tienen índices de texto que no se solapan. El analista necesita combinar ambas estructuras en un solo objeto de tipo DataFrame, de modo que cada Serie original ocupe una columna distinta, alineando sus índices de forma que se cree la unión total de las etiquetas.

- **Objetivo:** Usar `pd.concat` y su eje para combinar Series lado a lado.
- **Pista 1:** ¿Necesitas apilar las Series una debajo de otra o una al lado de la otra? La función de concatenación de pandas tiene un parámetro que controla esa dirección.
- **Pista 2:** `pd.concat` recibe una lista con los objetos a combinar.
- **Pista 3:** El parámetro `axis` decide la dirección: ¿qué valor pone una Serie al lado de la otra?
- **Errores frecuentes:** Concatenar sin `axis` y obtener una sola columna larga. Pasar las Series sin lista.
- **Verificación:** El resultado tiene 2 columnas y tantas filas como etiquetas suman ambas Series. Preguntar qué aparece en las celdas sin dato.
- **Alternativa:** El parámetro `keys` asigna nombres a las columnas.

### S4-P2-E24 · Combinar por índice con join

**Enunciado:**

> Dado el siguiente escenario: Se tiene un DataFrame `datos_principales` indexado por nombres de ciudades y un DataFrame `clima_promedio` también indexado por ciudades. Se requiere integrar la columna `Temperatura` de `clima_promedio` dentro de `datos_principales` de la manera más eficiente posible, asumiendo que ambos objetos ya están alineados por sus etiquetas de fila. ¿Qué método es el más directo y cuál es su comportamiento respecto a las ciudades que podrían estar en `datos_principales` pero no en `clima_promedio`?

- **Objetivo:** Usar `.join` y deducir su comportamiento con etiquetas que no coinciden.
- **Pista 1:** Los DataFrames tienen un método que combina por índice sin indicar claves. Pruébalo con una ciudad que esté en `datos_principales` pero no en `clima_promedio`, y observa qué filas se conservan y qué valor toma `Temperatura`.
- **Pista 2:** Antes de ejecutar, predice cuántas filas tendrá el resultado.
- **Pista 3:** Compara la cantidad de filas del resultado con la de `datos_principales`: ¿qué tipo de unión hace por defecto?
- **Errores frecuentes:** Usar `merge` sin indicar que la unión es por índice. Columnas con el mismo nombre en ambos: `join` pide sufijos.
- **Verificación:** `len(resultado)` es igual a `len(datos_principales)` y la ciudad faltante tiene `Temperatura` en NaN. La respuesta a la pregunta del enunciado la redacta el estudiante.
