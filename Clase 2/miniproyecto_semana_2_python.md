# MiniProyecto — Sistema Básico de Gestión de Estudiantes

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

## Parte 1 — Crear los datos

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

# Parte 2 — Crear funciones

## Función 1 — Mostrar estudiantes

Crear una función llamada:

```python
mostrar_estudiantes()
```

La función debe recorrer la lista y mostrar en pantalla la información de cada estudiante.

---

## Función 2 — Calcular promedio general

Crear una función llamada:

```python
calcular_promedio_general()
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
buscar_destacados()
```

La función debe mostrar los estudiantes cuyo promedio sea mayor o igual a 8.

---

# Parte 3 — Información adicional

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
- legibilidad y orden general.
