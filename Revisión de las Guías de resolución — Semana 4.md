# Revisión de las Guías de resolución — Semana 4

Oct 12, 2026 · @Carlos Ruben Bageta

## Criterio

Se propone reformular 26 de las 40 guías, ajustar 5 y mantener 9. Se reformula toda guía que, copiada y ejecutada tal cual, resuelve el ejercicio.

| Decisión | Cuándo se aplica | Qué se hace |
| --- | --- | --- |
| Reformular | La guía contiene la línea de código completa o la respuesta a la pregunta del enunciado. | Se reemplaza por una pista y una verificación. |
| Ajustar | La guía orienta, pero revela un parámetro clave o tiene un error. | Se corrige o se quita solo ese fragmento. |
| Mantener | La guía nombra métodos o pasos y deja la construcción al estudiante. | Sin cambios. |

Formato propuesto para la guía nueva:

1. **Pista:** el concepto, el método o el parámetro a investigar, sin su valor. Idealmente formulada como pregunta.
2. **Verificación:** cómo comprobar que el resultado es correcto (forma, conteo, valores esperados). Traslada el esfuerzo a validar, que es lo que necesitarán al trabajar con IA.
3. **Solución (opcional):** el código completo dentro de un bloque `<details>` plegado, para consultar después de intentarlo.

Modelo ya presente en el material: las guías en viñetas de los ejercicios 10 a 12 del primer notebook.

## Semana\_4\_Introduccion\_a\_pandas\_v3

De 16 guías: 7 a reformular (15 a 21), 2 a ajustar por errores (7 y 10) y 7 se mantienen.

| Ej. | Guía actual (resumen) | Decisión | Guía propuesta |
| --- | --- | --- | --- |
| 1 | Nombra `pd.Series()` y el argumento `index`. | Mantener | Sin cambios. |
| 7 | Nombra `sep`, `skiprows` e `index_col='fecha'`. | Ajustar | Corregir `index_col='fecha'` por `'Fecha'`, como dice el enunciado. Lo demás, sin cambios. |
| 8 | Nombra `chunksize`, `sep='\s+'`, `na_values` y el bucle acumulador. | Mantener | Sin cambios: el estudiante debe armar el bucle. |
| 9 | Nombra `read_excel(sheet_name=...)` y `.to_parquet()`. | Mantener | Sin cambios. |
| 10 | Viñetas con `.head()`, `.tail()`, `.shape()`, `.info()`, `.isna().sum()`, `.describe()`. | Ajustar | Corregir `.shape()` por `.shape` (es un atributo; con paréntesis da error). |
| 11 | Viñetas con los pasos y métodos sugeridos. | Mantener | Sin cambios. |
| 12 | Viñetas con el umbral y la estrategia de graficación. | Mantener | Sin cambios. |
| 13 | Nombra `.set_index()` e `inplace`. | Mantener | Sin cambios. |
| 14 | Nombra `.reset_index()`. | Mantener | Sin cambios. |
| 15 | Línea completa con `set_index` y `sort_index(level=..., ascending=[False, True])`. | Reformular | **Pista:** construya el índice con `set_index` pasando ambas columnas y luego ordénelo con `sort_index`. ¿Qué tipo de valor debe recibir `ascending` para indicar un orden distinto en cada nivel? **Verificación:** el primer departamento mostrado debe ser el último alfabéticamente y, dentro de él, los ID deben ir de menor a mayor. |
| 16 | Línea completa: `estudiantes[['Nombre', 'Promedio']]`. | Reformular | **Pista:** para seleccionar varias columnas, el selector `[]` debe recibir una lista. ¿Cómo queda la expresión con la lista dentro de los corchetes de selección? **Verificación:** `resumen.columns` debe mostrar solo `Nombre` y `Promedio`, y `type(resumen)` debe ser `DataFrame`. |
| 17 | Línea completa: `.loc['2023-01-01':'2023-01-15', 'Temperatura']`. | Reformular | **Pista:** como el índice son fechas (etiquetas), use el selector por etiquetas: primero el rango de filas, luego la columna. Con etiquetas el extremo final sí se incluye, y el índice debe estar ordenado cronológicamente. **Verificación:** la primera y la última fecha del resultado deben ser 2023-01-01 y 2023-01-15. |
| 18 | Línea completa: `.iloc[10:21, 0:3]`. | Reformular | **Pista:** use el selector por posición. Con posiciones, el extremo final de un rango no se incluye: ¿qué número debe escribir para que la fila 20 quede incluida? **Verificación:** `subconjunto.shape` debe ser `(11, 3)`. |
| 19 | Línea completa con las dos condiciones y `&`. | Reformular | **Pista:** escriba cada condición como una comparación sobre su columna y combínelas con `&`, cada una entre paréntesis. ¿Qué error aparece si omite los paréntesis? **Verificación:** en el resultado, el mínimo de `Precio` debe ser mayor a 100 y el máximo de `Existencia`, menor a 10. |
| 20 | Línea completa con `.isin([...])`. | Reformular | **Pista:** en lugar de encadenar tres comparaciones con `\|`, existe un método de las Series que verifica si cada valor pertenece a una lista. Úselo para construir la máscara booleana. **Verificación:** `resultado['Destino'].unique()` debe devolver solo las tres ciudades. |
| 21 | Línea completa de `.query()` con `@salario_minimo`. | Reformular | **Pista:** dentro de la cadena de `.query()` las condiciones se escriben como comparaciones entre columnas y valores, unidas con `&` o `and`. Para referenciar una variable de Python se antepone un símbolo especial a su nombre: búsquelo en la documentación de `query`. **Verificación:** cambie el valor de `salario_minimo` y compruebe que cambia la cantidad de filas. |

## Semana\_4\_Introduccion\_a\_pandas\_segunda\_parte\_v3

De 24 guías: 19 a reformular, 3 a ajustar (5, 20 y 22) y 2 se mantienen (19 y 21).

| Ej. | Guía actual (resumen) | Decisión | Guía propuesta |
| --- | --- | --- | --- |
| 1 | Líneas completas: `ventas.isna().sum()` y `dropna(subset=['precio'])`. | Reformular | **Pista:** el conteo encadena dos métodos: uno marca los nulos y otro los suma por columna. Para eliminar, `dropna` tiene un parámetro que restringe la búsqueda de nulos a ciertas columnas. **Verificación:** después de eliminar, `ventas['precio'].isna().sum()` debe ser 0, aunque otras columnas sigan teniendo nulos. |
| 2 | Líneas completas con `mean()` y `fillna(media, inplace=True)`. | Reformular | **Pista:** calcule la media de la columna y guárdela en una variable. Use `fillna` con ese valor y asigne el resultado de vuelta a la columna; evite `inplace=True` sobre una columna. **Verificación:** no deben quedar nulos y la media de la columna no debe cambiar. ¿Por qué no cambia? |
| 3 | `fillna` con `method='ffill'` y `limit=2`. | Reformular | **Pista:** pandas tiene un método específico para propagar el último valor válido hacia adelante. Revise qué parámetro limita la cantidad de nulos consecutivos que rellena. **Verificación:** con una serie de prueba con 3 nulos seguidos, el tercero debe seguir siendo `NaN`. |
| 4 | Línea completa: `drop_duplicates(inplace=True)`. | Reformular | **Pista:** el enunciado pide primero identificar. Cuente las filas repetidas con el método que las marca y luego elimínelas con su método par. Revise qué hacen por defecto `subset` y `keep`. **Verificación:** el largo del DataFrame debe bajar exactamente en la cantidad de duplicados que contó. |
| 5 | Ordenar por fecha y `drop_duplicates(subset=[...], keep='last')`. | Ajustar | **Pista:** ordene primero por `fecha_registro`. Luego use `drop_duplicates` restringido a la columna del correo: ¿qué valor de `keep` conserva la última aparición? **Verificación:** `clientes['correo_electronico'].is_unique` debe ser `True`. |
| 6 | Línea completa: `df[df.duplicated(subset=claves)]`. | Reformular | **Pista:** `duplicated` devuelve una Serie booleana que sirve como máscara de filtrado. La función debe recibir la lista de columnas clave y pasarla al parámetro que restringe la comparación. **Verificación:** pruebe la función con un DataFrame pequeño donde sepa de antemano cuántos duplicados hay. |
| 7 | Diccionario completo y `df['genero'].map(mapeo)`. | Reformular | **Pista:** arme un diccionario con los valores actuales como claves y los nuevos como valores, y aplíquelo con el método de Series pensado para sustituir por correspondencias. **Verificación:** `df['genero'].unique()` debe mostrar solo los dos valores nuevos. ¿Qué pasaría con un valor que no está en el diccionario? |
| 8 | Línea completa: `apply(lambda row: ..., axis=1)`. | Reformular | **Pista:** la lambda recibe una fila completa y devuelve la suma de las dos columnas. Para que `apply` recorra filas y no columnas, revise el parámetro `axis`. **Verificación:** compare con `empleados['salario_base'] + empleados['bono']`; deben coincidir. ¿Cuál de las dos formas es más simple? |
| 9 | Línea completa con la lambda de estandarización. | Reformular | **Pista:** la lambda recibe cada valor `x`; la fórmula es (x − media) / desvío. Calcule la media y el desvío una sola vez, fuera de la lambda. **Verificación:** la columna resultante debe tener media cercana a 0 y desvío cercano a 1. |
| 10 | Línea completa con el diccionario de `rename`. | Reformular | **Pista:** `rename` recibe en `columns` un diccionario de la forma {nombre\_viejo: nombre\_nuevo}. **Verificación:** `df.columns` debe mostrar `ID`, `Nombre` y `Edad`. |
| 11 | Línea completa: `rename(columns=lambda x: x.strip().lower())`. | Reformular | **Pista:** además de un diccionario, `columns` acepta una función que se aplica a cada nombre. Combine dos métodos de cadenas: uno quita espacios en los extremos y otro pasa a minúsculas. **Verificación:** pruebe con columnas `' Nombre '` y `'EDAD'`. |
| 12 | Línea completa (con la clave equivocada). | Reformular | **Pista:** `rename` tiene un parámetro distinto de `columns` para las etiquetas de fila. Arme el diccionario con los nombres incorrectos como claves. **Verificación:** `'Espña' in df.index` debe dar `False`. |
| 13 | Listas `bins` y `labels` completas y la llamada a `pd.cut`. | Reformular | **Pista:** defina una lista de 4 límites y otra de 3 etiquetas, y páselas a `pd.cut` en sus parámetros. ¿Por qué hay un límite más que etiquetas? **Verificación:** la edad 8 debe quedar como Menor y la 90 como Senior. |
| 14 | Línea completa: `pd.qcut(df['puntaje_examen'], q=4)`. | Reformular | **Pista:** `qcut` necesita la columna a dividir y la cantidad de grupos; revise qué parámetro la indica. **Verificación:** con `value_counts()`, cada grupo debe tener cerca del 25% de los estudiantes. ¿Qué cambia si usa `cut` con 4 bins? |
| 15 | Línea completa con `labels=False` + 1 y `value_counts()`. | Reformular | **Pista:** use `qcut` con 5 grupos. Para obtener niveles del 1 al 5 hay dos caminos: pasar una lista de etiquetas, o usar `labels=False` (numera desde 0) y ajustar. **Verificación:** el conteo por nivel debe dar cantidades similares. |
| 16 | Línea completa: `pd.get_dummies(estudios)`. | Reformular | **Pista:** pandas tiene una función que convierte una Serie categórica en una columna indicadora por categoría (*dummies*). **Verificación:** el resultado debe tener 5 filas, una columna por categoría distinta y un único valor verdadero por fila. |
| 17 | `get_dummies(..., prefix='Venta')` y `.join()` paso a paso. | Reformular | **Pista:** `get_dummies` tiene un parámetro para anteponer un prefijo a las nuevas columnas. Combine el resultado con la parte del DataFrame que quiere conservar, sin `Canal`. **Verificación:** `Canal` no debe estar en las columnas y debe existir `Venta_Online`. |
| 18 | Línea completa: `df['Lenguajes'].str.get_dummies('\|')`. | Reformular | **Pista:** `pd.get_dummies` trata cada cadena como una sola categoría, así que `"Python\|SQL"` sería una categoría aparte. Busque en el accesor `.str` un método que separe por un delimitador y genere los indicadores. **Verificación:** la fila `"Python\|SQL"` debe tener 1 en `Python` y `SQL`, y 0 en `R`. |
| 19 | Pasos en prosa: `groupby` por `Tienda` y `.mean()`. | Mantener | Sin cambios. |
| 20 | Pasos con `groupby(["dia", "smoker"])` y `.agg(["max", "min", "mean"])`. | Ajustar | Corregir `"smoker"` por `"fumador"`. Quitar la lista literal de funciones y dejar: "use `.agg()` con las tres estadísticas pedidas". |
| 21 | Viñetas con función auxiliar, `.loc`, `.idxmax()` y `apply`. | Mantener | Sin cambios. |
| 22 | Explica *left join* y cierra con la línea completa de `pd.merge`. | Ajustar | Quitar la última oración ("La sintaxis recomendada sería..."). Lo demás, sin cambios. |
| 23 | Nombra `pd.concat(axis=1)` y describe el resultado. | Reformular | **Pista:** ¿necesita apilar las Series una debajo de otra o una al lado de la otra? La función de concatenación de pandas tiene un parámetro que controla esa dirección. **Verificación:** el resultado debe tener 2 columnas y tantas filas como etiquetas sumen ambas Series. ¿Qué aparece en las celdas sin dato? |
| 24 | Responde la pregunta del enunciado: `.join` y su *left join*. | Reformular | **Pista:** los DataFrames tienen un método que combina por índice sin indicar claves. Pruébelo con una ciudad que esté en `datos_principales` pero no en `clima_promedio`, y observe qué filas se conservan y qué valor toma `Temperatura`. Responda la pregunta a partir de lo observado. |

## Errores técnicos en las guías actuales

Hay 8 errores o desajustes que conviene corregir, se reformule o no la guía. Se comprobaron con pandas 2.3.3, la versión instalada en tu equipo.

| Notebook | Ej. | Problema | Corrección |
| --- | --- | --- | --- |
| Primera parte | 7 | `index_col='fecha'`, pero el enunciado nombra la columna "Fecha". | `index_col='Fecha'` |
| Primera parte | 10 | `.shape()` da `TypeError`: `shape` es un atributo. | `.shape` |
| Segunda parte | 2 | `df[col].fillna(..., inplace=True)` hoy funciona con advertencia; en pandas 3 deja de modificar el DataFrame. | `estudiantes['calificacion_final'] = estudiantes['calificacion_final'].fillna(media)` |
| Segunda parte | 3 | `fillna(method='ffill')` está deprecado (FutureWarning). | `.ffill(limit=2)` |
| Segunda parte | 9 | La lambda recalcula media y desvío para cada elemento: correcto pero ineficiente. | Calcularlos una vez fuera de la lambda. |
| Segunda parte | 12 | La clave del diccionario es `'España'`; el índice a corregir es `'Espña'`. Con la guía, no se corrige nada. | `{'Espña': 'España', 'Francia_2': 'Francia'}` |
| Segunda parte | 16 | Dice "un solo 1", pero `get_dummies` devuelve `True`/`False` desde pandas 2. | "un solo `True`", o usar `dtype=int`. |
| Segunda parte | 20 | Agrupa por `"smoker"`, pero la columna del enunciado es `fumador`. | `["dia", "fumador"]` |

## Próximos pasos

- [x] Revisar la columna Decisión de ambas tablas y cambiar las que no compartas.
- [ ] Decidir si se incluye la solución plegada en `<details>` debajo de cada guía.
- [x] Aplicar los cambios en los notebooks \_v3 (sin tocar celdas de código ni el resto del texto).
