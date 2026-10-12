# MiniProyecto — Análisis Básico de Ventas con pandas

## Uso responsable de IA (resumen)

La IA puede utilizarse como apoyo para aprender, pero no para reemplazar el razonamiento propio. Antes de consultar IA, escriba un intento personal o una explicación de lo que no entiende.

Se permite pedir pistas, explicaciones de errores, revisión de código propio y casos de prueba. No se permite copiar soluciones completas sin comprenderlas. Toda entrega debe incluir una breve declaración de uso de IA.

*(Política completa disponible en el notebook de la Semana 1.)*

## Ajuste del Miniproyecto 4: etapas, uso de IA y evidencia requerida

### Etapas

- **Etapa 1 (obligatoria):** crear el DataFrame y explorarlo.
- **Etapa 2 (obligatoria):** filtrado de información.
- **Etapa 3 (obligatoria):** limpieza simple y creación de `total_venta`.
- **Etapa 4 (obligatoria):** agrupamiento básico.
- **Opcional:** desafío final.

### Qué se permite

- Pedir explicación de filtros y de `groupby`.
- Pedir casos de prueba para la limpieza de datos.
- Comparar dos soluciones simples y decidir cuál es más clara.

### Qué no se permite

- Solicitar el análisis completo.
- Usar gráficos, métodos o librerías no vistos en clase sin justificación.

### Evidencia requerida

- Notebook con los pasos comentados y los resultados visibles.
- Declaración de uso de IA.
- Defensa breve de los resultados (explicar una parte del código y modificar un detalle simple).

### Entrega

Este miniproyecto forma parte del **documento único de entrega** del curso, junto con los demás miniproyectos concluidos. Consulte el *Instructivo de presentación* y la *Rúbrica de evaluación* para conocer el formato y los criterios.

## Objetivo

Desarrollar un pequeño proyecto de análisis de datos utilizando `pandas` para:

- crear y explorar datos,
- filtrar registros,
- limpiar datos simples,
- y generar algunos resúmenes básicos.

El objetivo es practicar las operaciones fundamentales de manipulación de datos tabulares vistas durante la Semana 4. El proyecto se resuelve **por etapas**: complete cada etapa y verifique sus resultados antes de continuar.

---

# Contexto del problema

Una tienda desea realizar un análisis inicial de sus ventas utilizando Python y pandas.

La empresa dispone de un conjunto de datos con información de productos vendidos.

Tu tarea será crear el conjunto de datos, explorarlo y responder algunas preguntas básicas sobre las ventas.

---

# Etapa 1 (obligatoria) — Crear y explorar el conjunto de datos

## Crear el DataFrame

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

## Exploración inicial

Utilizar métodos para:

- visualizar las primeras filas,
- conocer las dimensiones del DataFrame,
- observar los tipos de datos,
- listar las columnas disponibles.

Calcular además:

- promedio de precios,
- cantidad total de productos vendidos.

---

# Etapa 2 (obligatoria) — Filtrado de información

Realizar los siguientes filtros (utilizar `.loc` en al menos uno de ellos):

- **Productos caros:** mostrar los productos cuyo precio sea mayor a 500.
- **Ventas por ciudad:** mostrar únicamente las ventas realizadas en una ciudad específica.

---

# Etapa 3 (obligatoria) — Limpieza simple y nueva columna

## Limpieza

Agregar intencionalmente:

- al menos un valor faltante,
- y un registro duplicado.

Luego:

- identificar valores faltantes,
- eliminar duplicados,
- verificar nuevamente el DataFrame.

## Nueva columna

Crear una nueva columna llamada:

```python
total_venta
```

La columna debe calcular:

```python
precio * cantidad
```

---

# Etapa 4 (obligatoria) — Agrupamiento básico

Utilizar `groupby()` para calcular las **ventas totales por categoría** (a partir de `total_venta`).

---

# Requisitos técnicos

El proyecto debe incluir:

- creación de un DataFrame,
- selección de columnas,
- filtrado con condiciones,
- uso de `.loc` o `.iloc`,
- identificación de valores faltantes,
- eliminación de duplicados,
- creación de una nueva columna,
- agrupamiento con `groupby()`.

---

# Recomendaciones

- Utilizar nombres claros para variables.
- Mantener el notebook ordenado.
- Separar cada etapa utilizando títulos Markdown.
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

- filtrar las ventas por categoría,
- calcular la cantidad total vendida por vendedor,
- calcular el precio máximo y mínimo,
- ordenar productos por precio,
- exportar el DataFrame a Excel,
- crear filtros combinados,
- calcular el producto más vendido.

---

# Criterios de evaluación

Se tendrá en cuenta:

- correcta utilización de pandas,
- organización del notebook,
- claridad del análisis,
- uso adecuado de filtros y agrupamientos,
- correcta manipulación de datos tabulares,
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
