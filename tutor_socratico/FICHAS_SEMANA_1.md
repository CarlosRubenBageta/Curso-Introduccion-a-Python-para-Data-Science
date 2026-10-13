# Fichas de ejercicios · Semana 1 (Configuración del entorno y fundamentos de Python)

Base de conocimiento del tutor socrático. Cada ficha corresponde a un ejercicio del notebook `Semana1_Intro_Python_v4.ipynb`.

- **Código:** `S1-E5` = Semana 1, ejercicio 5.
- **Nivel de protección:** todos los ejercicios de esta semana son PRÁCTICA, salvo indicación en la ficha.
- **Pistas:** se entregan de a una y en orden. La Pista 1 coincide con la guía del notebook.
- **Verificación:** criterio para que el estudiante compruebe su resultado y para que el tutor revise el intento.
- Las fichas no incluyen la solución en código a propósito.

### S1-E1 · Listar el contenido de una carpeta (dir)

**Enunciado:**

> Ejercicio 1: Primeros pasos en la terminal - uso de dir
>
> Escribe **dir /p** en la terminal.

- **Objetivo:** Usar la terminal para ver el contenido del directorio actual.
- **Pista 1:** Abre la terminal de Windows (Símbolo del sistema, cmd) y escribe el comando tal cual. ¿Qué hace la opción `/p` cuando la lista no entra en la pantalla?
- **Pista 2:** Si la lista es larga, la terminal se detiene: ¿qué tecla te deja avanzar?
- **Pista 3:** Compara la salida con lo que ves en el Explorador de archivos para esa misma carpeta.
- **Errores frecuentes:** Usar PowerShell: ahí `dir /p` da error porque `/p` se interpreta como una ruta; conviene usar el Símbolo del sistema (cmd). En macOS o Linux el comando equivalente es `ls`.
- **Verificación:** La terminal muestra los archivos y carpetas del directorio actual y se pausa cuando se llena la pantalla.

### S1-E2 · Limpiar la pantalla de la terminal (cls)

**Enunciado:**

> Ejercicio 2: Primeros pasos en la terminal - uso de cls
>
> Escribe **cls** en la terminal. Observa que ocurre.

- **Objetivo:** Reconocer que `cls` limpia la pantalla sin modificar archivos.
- **Pista 1:** Escribe el comando y observa la pantalla antes y después. ¿Se borró algo de tu computadora o solo de la pantalla?
- **Pista 2:** Después de limpiar, presiona la flecha hacia arriba: ¿siguen disponibles los comandos anteriores?
- **Pista 3:** En macOS o Linux el equivalente es `clear`.
- **Errores frecuentes:** Pensar que `cls` borra archivos o deshace comandos.
- **Verificación:** La pantalla queda vacía con el cursor arriba, y los archivos de la carpeta no cambian (compruébalo con `dir`).

### S1-E3 · Moverse entre carpetas y crear una (cd, mkdir)

**Enunciado:**

> Ejercicio 3: Primeros pasos en la terminal - uso de cd, mkdir
>
> - Cambia de directorio a la carpeta *Desktop*, utilizando **cd** 
> - Luego, dentro del mismo directorio crea una carpeta con el nombre *Prueba*, utilizando **mkdir**
> - Verifica la creacion de la carpeta con **dir/p**
> - Ingresa a la carpeta creada con **cd**
> - Chequea los archivos existentes alli con **dir**
> - Sal de la carpeta utilizando **cd ..**

- **Objetivo:** Navegar por carpetas con `cd`, crear una carpeta con `mkdir` y saber en qué carpeta se está.
- **Pista 1:** Haz un paso por vez y, después de cada uno, mira la ruta que muestra la terminal antes del cursor: te indica en qué carpeta estás.
- **Pista 2:** `cd` recibe el nombre de la carpeta a la que quieres entrar; `mkdir` recibe el nombre de la carpeta nueva.
- **Pista 3:** `cd ..` sube un nivel: ¿en qué carpeta deberías quedar?
- **Errores frecuentes:** La carpeta del escritorio puede llamarse *Escritorio* o estar dentro de OneDrive (`OneDrive\Desktop`). Los nombres con espacios necesitan comillas.
- **Verificación:** En *Desktop*, `dir /p` muestra la carpeta *Prueba*; dentro de *Prueba*, `dir` no muestra archivos; después de `cd ..` la ruta vuelve a terminar en *Desktop*.

### S1-E4 · Copiar archivos (copy)

**Enunciado:**

> Ejercicio 4: Primeros pasos en la terminal - uso de copy
>
> Investiga la sintaxis del comando **copy** y copia dos archivos con diferente extension que elijas al directorio *Prueba*. Puedes consultar documentación en línea o pedir una pista a una IA, siguiendo la política de uso responsable de IA de este notebook (primero intenta por tu cuenta).

- **Objetivo:** Investigar la sintaxis de un comando y usarlo con origen y destino.
- **Pista 1:** Consulta la ayuda del comando escribiendo `copy /?`: ¿qué va primero, el origen o el destino?
- **Pista 2:** Elige dos archivos que conozcas (por ejemplo, un .txt y un .pdf) y escribe su ruta completa, o entra primero a la carpeta donde están.
- **Pista 3:** El destino puede ser la ruta de la carpeta *Prueba*.
- **Errores frecuentes:** Invertir origen y destino. Rutas con espacios sin comillas.
- **Verificación:** Dentro de *Prueba*, `dir` muestra los dos archivos copiados con sus extensiones.

### S1-E5 · Borrar archivos y carpetas (del, rmdir)

**Enunciado:**

> Ejercicio 5: Primeros pasos en la terminal - uso de del y rmdir
>
> - Sitúate en el directorio *Prueba*
> - Borra un solo archivo utilizando el comando **del**
> - Sal del directorio *Prueba*
> - Borra el directorio utilizando **rmdir**. Que mensaje nos da la terminal?. 
> - Intenta borrar ahora con **rmdir Prueba /s**. Confirma la eliminacion.
> - Verifica con **dir /p** si el directorio se elimino correctamente.

- **Objetivo:** Borrar archivos y carpetas desde la terminal y comprender por qué `rmdir` pide la carpeta vacía.
- **Pista 1:** Haz los pasos en orden. Antes de usar `rmdir`, predice qué va a pasar si la carpeta todavía tiene un archivo.
- **Pista 2:** Lee el mensaje de `rmdir`: ¿qué condición pide para borrar la carpeta?
- **Pista 3:** La opción `/s` borra también el contenido: por eso pide confirmación.
- **Errores frecuentes:** Intentar borrar la carpeta estando dentro de ella. Usar PowerShell, donde `rmdir /s` no funciona igual: conviene el Símbolo del sistema (cmd). Lo que se borra con `del` no va a la Papelera.
- **Verificación:** `rmdir Prueba` sin `/s` muestra un mensaje de que el directorio no está vacío; después de `rmdir Prueba /s`, `dir /p` ya no muestra *Prueba*.

### S1-E6 · Listar paquetes instalados (pip list)

**Enunciado:**

> Ejercicio 6: Primeros pasos en la terminal - uso de pip
>
> - Utiliza **pip** y el comando **list** para listar los paquetes instalados usando la sintaxis del gestor de paquetes.

- **Objetivo:** Usar la sintaxis `pip <comando>` en la terminal.
- **Pista 1:** Escribe `pip` seguido del comando indicado, en la terminal (no dentro de Python).
- **Pista 2:** Si la terminal no reconoce `pip`, prueba con `python -m pip` seguido del comando.
- **Pista 3:** La salida es una tabla de dos columnas: ¿qué representa cada una?
- **Errores frecuentes:** Escribirlo dentro del intérprete de Python (cuando el cursor es `>>>`). Mensaje "'pip' no se reconoce": Python no está en la variable PATH.
- **Verificación:** Aparece una tabla con las columnas *Package* y *Version* con los paquetes instalados.

### S1-E7 · Instalar paquetes (pip install)

**Enunciado:**

> Ejercicio 7: Primeros pasos en la terminal - uso de pip
>
> - Utiliza el gestor **pip** y el comando **install**, para instalar los paquetes **numpy, pandas, matplotlib, seaborn, scikit-learn y jupyterlab**

- **Objetivo:** Instalar varios paquetes con `pip install` y comprobar la instalación.
- **Pista 1:** `pip install` acepta varios paquetes en una sola línea, separados por espacios.
- **Pista 2:** Si algo falla, lee la última línea del mensaje: ¿qué paquete dio el error?
- **Pista 3:** Al terminar, vuelve a usar el comando del ejercicio 6 para comprobar.
- **Errores frecuentes:** Separar los paquetes con comas. Escribir `sklearn` en lugar de `scikit-learn`. Ejecutar el comando dentro de Python.
- **Verificación:** `pip list` muestra numpy, pandas, matplotlib, seaborn, scikit-learn y jupyterlab.

### S1-E8 · Primer print

**Enunciado:**

> Ejercicio 8: Primeros pasos con Python - uso de cadenas de texto
> Imprime por pantalla tu primer *"Hola mundo"*, utilizando el comando **print**.
>
> Sobre la historia en programacion del *Hola Mundo*, consultar, por ejemplo: 
> https://ozanerhansha.medium.com/on-the-origin-of-hello-world-61bfe98196d5

- **Objetivo:** Entrar al intérprete de Python y mostrar un texto con `print()`.
- **Pista 1:** Entra al intérprete escribiendo `python` en la terminal. `print` recibe entre paréntesis lo que quieres mostrar, y un texto va entre comillas.
- **Pista 2:** ¿Cómo te das cuenta de que estás dentro de Python y no en la terminal?
- **Pista 3:** ¿Qué pasa si olvidas las comillas? Pruébalo y lee el error.
- **Errores frecuentes:** Olvidar las comillas (`NameError`). Comillas tipográficas copiadas de un documento. Escribir `Print` con mayúscula.
- **Verificación:** En la línea siguiente aparece el texto que escribiste, por ejemplo Hola mundo.

### S1-E9 · Salir del intérprete de Python

**Enunciado:**

> Ejercicio 9: Primeros pasos con Python - salir del ambiente de Python
> Pulsa la combinación de teclas **Ctrl** **+** **z** y luego **Enter** (en Windows; en macOS o Linux, **Ctrl** **+** **d**). También puedes escribir **exit()** y pulsar **Enter**. Con ello volverás nuevamente al ambiente del sistema operativo de la terminal.

- **Objetivo:** Distinguir el intérprete de Python de la terminal y salir de él.
- **Pista 1:** Fíjate en el cursor: `>>>` indica que estás dentro de Python. En Windows, Ctrl + Z necesita Enter después.
- **Pista 2:** También puedes salir con `exit()`.
- **Pista 3:** ¿Qué cambia en el cursor cuando sales?
- **Errores frecuentes:** Usar Ctrl + C: interrumpe una instrucción pero no sale del intérprete.
- **Verificación:** El cursor vuelve a mostrar la ruta de la carpeta (por ejemplo, `C:\Users\...>`) en lugar de `>>>`.

### S1-E10 · Crear y ejecutar un script

**Enunciado:**

> Ejercicio 10: Primeros pasos con Python - Uso de scripts - variables y comando **print()** 
>
> - Abre el el Editor de texto de tu preferencia.
>
> - Genera un archivo con el nombre: **saludar.py** y grabalo en algun directorio de trabajo.
>
> - Agrega las siguientes lineas de codigo: 
>
> [imagen en el notebook]
>
> - Guarda el archivo nuevamente con los cambios.
>
> - Ejecutalo desde la terminal
>
> Contenido de la imagen del notebook:
>
> ```python
> # Este script almacena nombre y edad en dos variables y las imprime por pantalla.
> nombre = "Ruben"
> edad = 55
> print(f"Hola, mi nombre es {nombre} y tengo {edad} años.")
> ```

- **Objetivo:** Guardar código en un archivo .py y ejecutarlo desde la terminal.
- **Pista 1:** Copia las líneas de la imagen tal como están y guarda el archivo con extensión .py, no .txt.
- **Pista 2:** Para ejecutarlo, en la terminal entra a la carpeta donde lo guardaste y escribe `python` seguido del nombre del archivo.
- **Pista 3:** Si cambias el valor de una variable y vuelves a ejecutar, ¿qué cambia en la salida?
- **Errores frecuentes:** El Bloc de notas guarda `saludar.py.txt`: hay que elegir "Todos los archivos" al guardar. Ejecutar desde otra carpeta: error de archivo no encontrado. Comillas tipográficas en el código.
- **Verificación:** La terminal imprime: Hola, mi nombre es … y tengo … años., con los valores de tus variables.

### S1-E11 · Ejecutar código en Jupyter, VS Code o Colab

**Enunciado:**

> Ejercicio 11: Uso de los ambientes Jupyter Lab - VS Code - Google Colab
>
> - Abrir el Notebook en Jupyter Lab / VS Code / Google Colab.
> - Agregar una celda de codigo luego del ejercicio 10 de este Notebook.
> - Reproducir el codigo en dicha celda (No generar el script al que hace referencia el ejercicio).
> - Explorar los tres ambientes, generar nuevas lineas de codigo y ejecutarlas. Opcional: probar el asistente de IA de Google Colab (Gemini) solo para pedir explicaciones o pistas, respetando la política de uso responsable de IA de este notebook.

- **Objetivo:** Reconocer las celdas de código y ejecutarlas en distintos entornos.
- **Pista 1:** Empieza por un solo entorno. Agrega una celda de código debajo del ejercicio 10 y escribe allí las líneas del script.
- **Pista 2:** En Jupyter y VS Code, una celda se ejecuta con Mayús + Enter.
- **Pista 3:** Compara: ¿qué cambia entre ejecutar un script en la terminal y ejecutar una celda?
- **Errores frecuentes:** En VS Code, no hay un intérprete de Python (kernel) seleccionado. En Colab, el notebook debe subirse o abrirse desde Drive.
- **Verificación:** La celda muestra el mismo mensaje que el script del ejercicio 10 en cada entorno que probaste.

### S1-E12 · Pedir datos con input()

**Enunciado:**

> Ejercicio 12: Seleccion del ambiente de trabajo - Input del usuario
>
> - Selecciona el ambiente que sea adecuado para ti (puede ser cualquiera de los tres mencionados arrriba)
> - Ejecuta el siguiente script (el mismo muestra como se puede solicitar el ingreso de datos con el comando **input**):
>
> Código de la celda siguiente:
>
> ```python
> nombre = input("¿Cuál es tu nombre? ")
> print(f"¡Hola, {nombre}!")
> ```

- **Objetivo:** Ejecutar un programa que espera datos del usuario.
- **Pista 1:** Ejecuta la celda: el programa se detiene y espera que escribas algo. ¿Dónde aparece el cuadro para escribir?
- **Pista 2:** Escribe tu nombre y presiona Enter.
- **Pista 3:** Vuelve a ejecutar con otro nombre: ¿qué parte del mensaje cambia y por qué?
- **Errores frecuentes:** La celda queda "ejecutándose" porque está esperando el dato.
- **Verificación:** Se imprime ¡Hola, seguido de tu nombre!
