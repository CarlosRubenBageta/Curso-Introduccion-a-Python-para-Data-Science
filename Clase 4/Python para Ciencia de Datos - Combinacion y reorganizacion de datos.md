# Python para Ciencia de Datos

Exported on: 15/4/2026, 14:08:01

---

### User

Prompt para generacion de contenido a partir de fuentes con estilo ROL Actúa como un experto en pedagogía universitaria y especialista en la temática abordada en el cuaderno de NotebookLM proporcionado. Tu enfoque debe ser didáctico, riguroso y orientado a la comprensión profunda de los conceptos. OBJETIVO Generar contenido educativo estructurado EXCLUSIVAMENTE a partir de la información disponible en las fuentes del cuaderno de NotebookLM. TAREAS Para cada uno de los puntos indicados, desarrolla: 1. Explicación Detallada Define el concepto con precisión. Relaciona ideas clave presentes en las fuentes. Organiza la explicación de forma lógica y progresiva. Prioriza claridad conceptual sin perder rigor académico. 2. Práctica Activa Genera tres ejercicios por cada punto: Orientados a estudiantes universitarios. Con dificultad progresiva. Enfocados en aplicación y comprensión (no solo memorización). Cada ejercicio debe incluir: Enunciado claro y bien formulado. Contexto suficiente para ser resuelto sin ambigüedades. Una guía breve de resolución o solución final para verificación. FORMATO DE SALIDA Para cada punto: \[Nombre del punto\] Explicación \[Desarrollo teórico\] Ejercicio 1 Dado ... Guía de resolución: ... Ejercicio 2 Dado ... Guía de resolución: ... Ejercicio 3 Dado ... Guía de resolución: ... REGLAS ESTRICTAS Utiliza únicamente la información contenida en las fuentes del cuaderno. No incorpores conocimiento externo. No incluyas citas, ni hagas referencia a las fuentes utilizadas. No incluyas etiquetas como “básico”, “intermedio” o “avanzado”. Mantén consistencia terminológica con el material original. Usa lenguaje claro, formal y pedagógico. PUNTOS A DESARROLLAR Combinacion y reorganizacion de conjuntos de datos: ademass de los puntos relevantes que consideres adecuado, enfatiza que es y que diferencias hay entre join, merge y concat.

---

### Model

Combinación y reorganización de conjuntos de datos

Explicación

La integración de datos provenientes de múltiples fuentes es una tarea fundamental en el análisis de datos. En entornos de programación orientados a objetos como el ecosistema de Python, existen tres herramientas principales para realizar esta tarea: `merge`, `join` y `concat`. Aunque comparten el objetivo de combinar información, difieren significativamente en su lógica operativa y en cómo gestionan los índices y las claves.

**merge** **(Combinación basada en claves)** La función `pd.merge` implementa operaciones de unión similares a las de las bases de datos relacionales (SQL). Su lógica se centra en conectar filas utilizando una o más "claves" o columnas comunes. Es la herramienta de elección para realizar operaciones complejas como uniones "muchos a uno" o "muchos a muchos".

-   **Lógica de unión:** Por defecto, realiza una unión de tipo *inner* (intersección), conservando solo las claves que aparecen en ambos conjuntos. Sin embargo, permite otros tipos: *left* (preserva todas las claves del conjunto izquierdo), *right* (todas las del derecho) y *outer* (la unión de todas las claves, introduciendo valores nulos donde no hay coincidencia).-   **Flexibilidad:** Permite especificar columnas con nombres diferentes en cada conjunto mediante los argumentos `left_on` y `right_on`.

**join** **(Combinación basada en índices)** El método `.join` es una forma simplificada de combinar datos, diseñada específicamente para unir conjuntos basándose en sus índices (etiquetas de fila) en lugar de columnas arbitrarias.

-   **Diferencia operativa:** A diferencia de `merge`, el método `.join` realiza por defecto una unión de tipo *left* (preserva el índice del objeto original). Es ideal cuando se desea integrar datos de múltiples objetos que comparten el mismo índice pero tienen columnas diferentes.-   **Uso avanzado:** También permite unir el índice de un conjunto con una columna específica de otro mediante el argumento `on`.

**concat** **(Concatenación o apilamiento)** La función `pd.concat` se utiliza para "pegar" u objetos a lo largo de un eje determinado (filas o columnas). A diferencia de las anteriores, no busca necesariamente una relación lógica basada en el contenido de las celdas, sino que apila las estructuras.

-   **Ejes de operación:** Si se aplica sobre el eje de las filas (`axis=0`), el resultado es un objeto más largo. Si se aplica sobre el eje de las columnas (`axis=1`), el resultado es un objeto más ancho.-   **Jerarquías:** Permite crear índices jerárquicos (*MultiIndex*) mediante el argumento `keys`, lo que ayuda a identificar la fuente original de los datos una vez combinados.

En resumen, mientras que `merge` y `join` se basan en la alineación de valores (claves o índices), `concat` se basa en la disposición estructural de los conjuntos.

\--------------------------------------------------------------------------------

Ejercicio 1

Dado el siguiente escenario: Se cuenta con un DataFrame llamado `clientes` que contiene las columnas `ID_Cliente` y `Nombre`, y otro DataFrame llamado `pedidos` con las columnas `ID_Pedido`, `ID_Cliente` y `Monto`. Se desea obtener un listado de todos los pedidos realizados, incluyendo el nombre del cliente correspondiente, pero asegurándose de no perder ningún registro de la tabla `pedidos` incluso si el ID del cliente no se encuentra en la tabla de `clientes`.

**Guía de resolución:** Para resolver este problema, se debe utilizar `pd.merge`. Dado que el objetivo es mantener todos los registros del conjunto que contiene los pedidos, se debe realizar una unión de tipo *left* (si `pedidos` es el primer argumento) o *right* (si es el segundo). La clave de unión será la columna común `ID_Cliente`. La sintaxis recomendada sería `pd.merge(pedidos, clientes, on="ID_Cliente", how="left")`.

\--------------------------------------------------------------------------------

Ejercicio 2

Dado el siguiente escenario: Un analista tiene dos Series independientes, `s1` y `s2`. Ambas tienen índices de texto que no se solapan. El analista necesita combinar ambas estructuras en un solo objeto de tipo DataFrame, de modo que cada Serie original ocupe una columna distinta, alineando sus índices de forma que se cree la unión total de las etiquetas.

**Guía de resolución:** En este caso, la herramienta adecuada es `pd.concat` utilizando el argumento `axis=1` (o `axis="columns"`). Al tratarse de Series sin solapamiento de índices, el resultado será un DataFrame donde las filas correspondientes a etiquetas ausentes en una de las Series se llenarán con valores nulos (NaN). Además, se pueden asignar nombres a las columnas resultantes pasando una lista al argumento `keys`.

\--------------------------------------------------------------------------------

Ejercicio 3

Dado el siguiente escenario: Se tiene un DataFrame `datos_principales` indexado por nombres de ciudades y un DataFrame `clima_promedio` también indexado por ciudades. Se requiere integrar la columna `Temperatura` de `clima_promedio` dentro de `datos_principales` de la manera más eficiente posible, asumiendo que ambos objetos ya están alineados por sus etiquetas de fila. ¿Qué método es el más directo y cuál es su comportamiento respecto a las ciudades que podrían estar en `datos_principales` pero no en `clima_promedio`?

**Guía de resolución:** El método más directo es utilizar `.join`. Al invocar `datos_principales.join(clima_promedio)`, el sistema buscará por defecto las coincidencias en los índices de ambos objetos. El comportamiento estándar de `.join` es realizar un *left join*, lo que significa que el resultado final conservará exactamente todas las ciudades (filas) que existían en `datos_principales`. Si una ciudad de `datos_principales` no existe en `clima_promedio`, la columna `Temperatura` mostrará un valor nulo para esa fila.