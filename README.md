# trabajo-integrador
INFORME TEÓRICO: CONCEPTOS APLICADOS EN EL PROGRAMA DE GESTIÓN DE PAÍSES
Introducción

El programa desarrollado en Python permite administrar información de diferentes países mediante un sistema que ofrece distintas operaciones, como agregar, actualizar, buscar, filtrar, ordenar y mostrar estadísticas.

Para desarrollar este sistema se utilizaron diferentes conceptos fundamentales de programación, como listas, diccionarios, funciones, condicionales, ordenamientos, estadísticas básicas y archivos CSV.

A continuación, se explica cada uno de estos conceptos y su aplicación dentro del programa.

1. Listas

Una lista es una estructura de datos que permite almacenar varios elementos dentro de una misma variable. Los elementos se guardan en un orden determinado y se pueden modificar, agregar o eliminar.

En Python, las listas se escriben utilizando corchetes [].

Aplicación en el programa:

En el sistema se utiliza una lista llamada paises, que almacena todos los países ingresados por el usuario.

python
def cargar_paises():
    paises = []


Cada vez que se agrega un país, se incorpora a la lista mediante el método append().

python
paises.append(nuevo_pais)


La lista permite trabajar con todos los países cargados, recorrerlos, buscarlos, ordenarlos y aplicar filtros.

2. Diccionarios

Un diccionario es una estructura de datos que permite almacenar información mediante pares de clave y valor. Cada dato tiene una clave que permite identificarlo y acceder a él.

En Python, los diccionarios se escriben utilizando llaves {}.

Aplicación en el programa:

En el sistema, cada país se representa mediante un diccionario que contiene cuatro datos:

Nombre.
Población.
Superficie.
Continente.

Ejemplo:

python
pais = {
    "nombre": "Argentina",
    "poblacion": 46000000,
    "superficie": 2780400,
    "continente": "América"
}


Para acceder a un dato se utiliza su clave. Por ejemplo:

python
pais["nombre"]
pais["continente"]


Los diccionarios permiten organizar la información de cada país de manera clara y facilitar su consulta y modificación.

3. Funciones

Las funciones son bloques de código que realizan una tarea específica. Permiten organizar el programa, evitar repetir instrucciones y facilitar su mantenimiento.

En Python, las funciones se definen utilizando la palabra reservada def.

Aplicación en el programa:

El sistema está dividido en diferentes funciones, cada una encargada de realizar una operación.

Algunos ejemplos son:

agregar_pais(): permite incorporar un nuevo país.
actualizar_pais(): permite modificar los datos de un país existente.
buscar_pais(): permite buscar un país por su nombre.
mostrar_paises(): muestra todos los países cargados.
guardar_paises(): guarda la información en el archivo CSV.
mostrar_estadisticas(): calcula y muestra diferentes estadísticas.

Esta organización permite que el código sea más ordenado, comprensible y fácil de modificar.

4. Condicionales

Los condicionales permiten que un programa tome decisiones dependiendo de si se cumple o no una determinada condición.

En Python se utilizan principalmente las instrucciones if, elif y else.

Aplicación en el programa:

Los condicionales se utilizan en diferentes partes del sistema para controlar las operaciones y validar los datos ingresados.

Por ejemplo:

python
if not paises:
    print("No hay países para mostrar.")
    return


En este caso, se verifica si la lista está vacía. Si no hay países cargados, se muestra un mensaje y se finaliza la función.

También se utilizan para controlar las opciones del menú principal:

python
if opcion == "1":
    agregar_pais(paises)
elif opcion == "2":
    actualizar_pais(paises)
elif opcion == "3":
    buscar_pais(paises)
else:
    print("Error: opción inválida.")


De esta manera, el programa ejecuta una acción diferente según la opción seleccionada por el usuario.

5. Ordenamientos

Los ordenamientos son procedimientos que permiten organizar los datos siguiendo un criterio determinado, como el orden alfabético o de menor a mayor.

En Python se puede utilizar la función sorted(), que devuelve una nueva lista con los elementos ordenados.

Aplicación en el programa:

El sistema permite ordenar los países según tres criterios:

Por nombre.
Por población.
Por superficie.

Por ejemplo:

python
ordenados = sorted(
    paises,
    key=lambda p: p["nombre"].lower()
)


Este código ordena los países alfabéticamente según su nombre.

También se utiliza el parámetro reverse=True para ordenar los valores de mayor a menor.

El ordenamiento facilita la visualización y comparación de la información almacenada.

6. Estadísticas básicas

Las estadísticas básicas permiten analizar un conjunto de datos y obtener información resumida a partir de ellos.

En el programa se utilizan operaciones matemáticas para calcular y mostrar diferentes resultados relacionados con los países registrados.

Aplicación en el programa:

El sistema permite obtener las siguientes estadísticas:

País con mayor población: se utiliza max() para encontrar el país que tiene el valor más alto de población.
País con menor población: se utiliza min() para encontrar el país que tiene el valor más bajo de población.
Promedio de población: se suman todas las poblaciones y se divide el resultado por la cantidad de países.
Promedio de superficie: se suman todas las superficies y se divide por la cantidad de países.
Cantidad de países por continente: se utiliza un diccionario para contar cuántos países pertenecen a cada continente.

Ejemplo del cálculo del promedio:

python
promedio_poblacion = (
    sum(p["poblacion"] for p in paises) / len(paises)
)


Estas operaciones permiten obtener información general y realizar comparaciones entre los países registrados.

7. Archivos CSV

Los archivos CSV (Comma-Separated Values) son archivos de texto que permiten almacenar información organizada en filas y columnas, separando los datos mediante comas.

Son utilizados para guardar e intercambiar información entre diferentes programas, como Python y Excel.

En Python se puede trabajar con archivos CSV mediante el módulo csv.

Aplicación en el programa:

El sistema utiliza un archivo llamado paises.csv para almacenar permanentemente la información de los países.

Se utilizan dos funciones principales:

Lectura del archivo:

python
with open(ARCHIVO, "r", encoding="utf-8-sig",
          newline="") as archivo:
    lector = csv.DictReader(archivo)


La función csv.DictReader() permite leer el archivo y acceder a cada dato mediante el nombre de su columna.

Escritura del archivo:

python
with open(ARCHIVO, "w", encoding="utf-8",
          newline="") as archivo:
    escritor = csv.DictWriter(
        archivo,
        fieldnames=CAMPOS
    )
    escritor.writeheader()
    escritor.writerows(paises)


La función csv.DictWriter() permite guardar los datos de los países en el archivo CSV.

El uso de archivos CSV permite conservar la información aunque el programa se cierre y volver a utilizarla cuando se ejecute nuevamente.

Conclusión

A través del desarrollo de este programa se aplicaron diferentes conceptos fundamentales de Python que permiten construir un sistema organizado para administrar información.

Las listas y los diccionarios permiten almacenar y organizar los datos; las funciones dividen el programa en tareas específicas; los condicionales permiten controlar las decisiones; los ordenamientos facilitan la organización de la información; las estadísticas permiten analizar los datos y los archivos CSV permiten guardar y recuperar la información de manera permanente.

La integración de todos estos conceptos permitió desarrollar un sistema de gestión de países funcional, organizado y fácil de utilizar.
https://drive.google.com/file/d/1x2PJbaXWHLrCcO9jPgJZiHuwnHp9wCx8/view?usp=sharing
