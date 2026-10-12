# MiniProyecto — Análisis Básico de Ventas con pandas

## Objetivo

Desarrollar un pequeño proyecto de análisis de datos utilizando `pandas` para:

- cargar datos,
- explorar información,
- filtrar registros,
- limpiar datos simples,
- y generar algunos resúmenes básicos.

El objetivo es practicar las operaciones fundamentales de manipulación de datos tabulares vistas durante la Semana 4.

---

# Contexto del problema

Una tienda desea realizar un análisis inicial de sus ventas utilizando Python y pandas.

La empresa dispone de un conjunto de datos con información de productos vendidos.

Tu tarea será cargar el conjunto de datos, explorarlo y responder algunas preguntas básicas sobre las ventas.

---

# Parte 1 — Crear el conjunto de datos

Crear un DataFrame llamado:

```python
df_ventas
```

El DataFrame debe contener al menos 10 registros y las siguientes columnas:

| columna | descripción |
|---|---|
| producto | nombre del producto |
| categoria | categoría del producto |
| precio | precio unitario |
| cantidad | cantidad vendida |
| vendedor | nombre del vendedor |
| ciudad | ciudad de venta |

---

# Parte 2 — Exploración inicial

Realizar las siguientes tareas:

## Mostrar información general

Utilizar métodos para:

- visualizar las primeras filas,
- conocer las dimensiones del DataFrame,
- observar los tipos de datos,
- listar las columnas disponibles.

---

## Obtener estadísticas básicas

Calcular:

- promedio de precios,
- cantidad total de productos vendidos,
- precio máximo,
- precio mínimo.

---

# Parte 3 — Filtrado de información

Realizar filtros para:

## Productos caros

Mostrar los productos cuyo precio sea mayor a 500.

---

## Ventas por ciudad

Mostrar únicamente las ventas realizadas en una ciudad específica.

---

## Ventas por categoría

Mostrar únicamente productos de una categoría determinada.

---

# Parte 4 — Limpieza simple de datos

Agregar intencionalmente:

- al menos un valor faltante,
- y un registro duplicado.

Luego:

- identificar valores faltantes,
- eliminar duplicados,
- verificar nuevamente el DataFrame.

---

# Parte 5 — Agrupamiento básico

Utilizar `groupby()` para:

- calcular ventas totales por categoría,
- calcular cantidad total vendida por vendedor.

---

# Parte 6 — Transformación simple

Crear una nueva columna llamada:

```python
total_venta
```

La columna debe calcular:

```python
precio * cantidad
```

---

# Requisitos técnicos

El proyecto debe incluir:

- creación de DataFrames,
- uso de Series,
- selección de columnas,
- filtrado con condiciones,
- uso de `.loc` o `.iloc`,
- identificación de valores faltantes,
- eliminación de duplicados,
- agrupamiento con `groupby()`,
- creación de nuevas columnas.

---

# Recomendaciones

- Utilizar nombres claros para variables.
- Mantener el notebook ordenado.
- Separar cada parte utilizando títulos Markdown.
- Mostrar resultados intermedios para verificar el análisis.

---

# Ejemplo esperado de salida

```text
Promedio de precios: 720.5

Productos con precio mayor a 500:
Notebook
Monitor
Impresora

Ventas totales por categoría:
Electrónica    152000
Oficina         83000
```

---

# Desafío opcional

Agregar alguna de las siguientes mejoras:

- ordenar productos por precio,
- exportar el DataFrame a Excel,
- crear filtros combinados,
- calcular el producto más vendido,
- generar un resumen final automático.

---

# Criterios de evaluación

Se tendrá en cuenta:

- correcta utilización de pandas,
- organización del notebook,
- claridad del análisis,
- uso adecuado de filtros y agrupamientos,
- correcta manipulación de datos tabulares.
