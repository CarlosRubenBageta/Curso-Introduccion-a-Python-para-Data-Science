# MiniProyecto — Sistema Básico de Gestión de Estudiantes

## Uso responsable de IA (resumen)

La IA puede utilizarse como apoyo para aprender, pero no para reemplazar el razonamiento propio. Antes de consultar IA, escriba un intento personal o una explicación de lo que no entiende.

Se permite pedir pistas, explicaciones de errores, revisión de código propio y casos de prueba. No se permite copiar soluciones completas sin comprenderlas. Toda entrega debe incluir una breve declaración de uso de IA.

*(Política completa disponible en el notebook de la Semana 1.)*

## Ajuste del Miniproyecto 2: etapas, uso de IA y evidencia requerida

### Etapas

- **Etapa 1 (obligatoria):** datos (lista de diccionarios).
- **Etapa 2 (obligatoria):** funciones.
- **Etapa 3 (obligatoria):** resumen final.
- **Opcional:** desafío final.

### Qué se permite

- Pedir explicación de funciones propias.
- Pedir casos de prueba para las funciones.
- Pedir mejoras en los nombres de variables y funciones.

### Qué no se permite

- Pedir el programa completo resuelto.
- Copiar funciones que no se puedan explicar línea por línea.

### Evidencia requerida

- Intento propio (el código escrito antes de consultar IA).
- Prompts utilizados.
- Explicación, con palabras propias, de cada función.
- Declaración de uso de IA y reflexión final.

### Entrega

Este miniproyecto forma parte del **documento único de entrega** del curso, junto con los demás miniproyectos concluidos. Consulte el *Instructivo de presentación* y la *Rúbrica de evaluación* para conocer el formato y los criterios.

## Objetivo

Desarrollar un pequeño sistema en Python que permita registrar información básica de estudiantes utilizando:

- variables,
- listas,
- diccionarios,
- funciones,
- operadores,
- y estructuras de datos vistas en la Semana 2.

El objetivo principal es practicar la organización de información y la creación de funciones simples para manipular datos.

---

# Contexto del problema

Una academia necesita almacenar información básica de algunos estudiantes.

Cada estudiante tendrá:

- nombre,
- edad,
- carrera,
- promedio.

La información deberá almacenarse utilizando diccionarios y listas.

---

# Requisitos del proyecto

## Etapa 1 (obligatoria) — Crear los datos

Crear al menos **5 estudiantes** utilizando diccionarios.

Ejemplo de estructura:

```python
estudiante = {
    "nombre": "Ana",
    "edad": 21,
    "carrera": "Ingeniería",
    "promedio": 8.5
}
```

Todos los estudiantes deben almacenarse dentro de una lista.

Ejemplo:

```python
estudiantes = [estudiante1, estudiante2, estudiante3]
```

---

# Etapa 2 (obligatoria) — Crear funciones

Cada función debe recibir la lista de estudiantes como **parámetro** (no utilizar variables globales dentro de las funciones).

## Función 1 — Mostrar estudiantes

Crear una función llamada:

```python
mostrar_estudiantes(lista_estudiantes)
```

La función debe recorrer la lista y mostrar en pantalla la información de cada estudiante.

---

## Función 2 — Calcular promedio general

Crear una función llamada:

```python
calcular_promedio_general(lista_estudiantes)
```

La función debe:

- recorrer todos los estudiantes,
- sumar los promedios,
- calcular el promedio general,
- retornar el resultado.

---

## Función 3 — Buscar estudiantes destacados

Crear una función llamada:

```python
buscar_destacados(lista_estudiantes)
```

La función debe mostrar los estudiantes cuyo promedio sea mayor o igual a 8.

---

# Etapa 3 (obligatoria) — Resumen final

Mostrar finalmente:

- cantidad total de estudiantes,
- promedio general del curso,
- cantidad de estudiantes destacados.

---

# Requisitos técnicos

El proyecto debe incluir:

- uso de listas,
- uso de diccionarios,
- uso de funciones,
- parámetros y valores de retorno,
- operadores relacionales,
- operadores lógicos básicos,
- recorrido de estructuras de datos.

---

# Recomendaciones

- Utilizar nombres de variables descriptivos.
- Mantener el código ordenado.
- Agregar comentarios simples para explicar partes importantes.
- Probar el programa varias veces.

---

# Ejemplo esperado de salida

```text
===== LISTA DE ESTUDIANTES =====

Nombre: Ana
Edad: 21
Carrera: Ingeniería
Promedio: 8.5

Nombre: Martín
Edad: 20
Carrera: Agronomía
Promedio: 7.2

Promedio general: 8.1

Estudiantes destacados:
- Ana
- Lucía
```

---

# Desafío opcional

Agregar una función que permita:

- buscar estudiantes por carrera,
- o encontrar el estudiante con mayor promedio.

---

# Criterios de evaluación

Se tendrá en cuenta:

- correcta utilización de listas y diccionarios,
- claridad del código,
- uso adecuado de funciones,
- correcta organización del programa,
- legibilidad y orden general,
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
