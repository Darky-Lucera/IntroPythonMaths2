**Indice** (versión 0.4 beta)

- [Introducción a Python](#introducción-a-python)
- [Módulos: Imports en Python y su Importancia](#módulos-imports-en-python-y-su-importancia)
  - [Módulos comunes o entandar](#módulos-comunes-o-entandar)
  - [Módulos externos que usaremos en clase](#módulos-externos-que-usaremos-en-clase)
- [Comentarios en Python](#comentarios-en-python)
- [Tipos de variables en Python](#tipos-de-variables-en-python)
  - [Slicing (rebanado) de listas, tuplas y otros tipos de secuencias:](#slicing-rebanado-de-listas-tuplas-y-otros-tipos-de-secuencias)
  - [Constantes](#constantes)
- [Operadores](#operadores)
  - [Operadores Aritméticos](#operadores-aritméticos)
  - [Operadores Lógicos](#operadores-lógicos)
  - [Operadores bit a bit](#operadores-bit-a-bit)
  - [Operadores de Comparación](#operadores-de-comparación)
  - [Precedencia de operadores y paréntesis](#precedencia-de-operadores-y-paréntesis)
- [Indentación](#indentación)
- [Condicionales](#condicionales)
- [Bucles](#bucles)
  - [Funciones útiles para bucles](#funciones-útiles-para-bucles)
- [List comprehension](#list-comprehension)
- [Funciones y parámetros en Python](#funciones-y-parámetros-en-python)
  - [Funciones:](#funciones)
  - [Parámetros:](#parámetros)
    - [Parámetros especiales](#parámetros-especiales)
  - [Funciones lambda](#Funciones-lambda)
- [Clases](#clases)
  - [Otros métodos especiales de las clases](#otros-métodos-especiales-de-las-clases)
  - [Herencia](#herencia)

# Introducción a Python

Python es un lenguaje de programación de alto nivel que se destaca por su sintaxis clara y legible. Es ideal para principiantes debido a su facilidad de aprendizaje y su amplia aplicación en diferentes campos como desarrollo web, análisis de datos, inteligencia artificial, entre otros.

# Módulos (imports) y su Importancia

Los módulos en Python son declaraciones que permiten a un programa utilizar código definido en otros archivos o módulos. Son necesarios porque facilitan la reutilización de código y la organización de proyectos en múltiples archivos.

Cuando importamos un módulo en Python, obtenemos acceso a todas las funciones, clases y variables definidas en ese módulo. Esto nos permite utilizar el código sin necesidad de volver a escribirlo, lo que ahorra tiempo y reduce la posibilidad de errores.

**Ejemplos**:

Importar un módulo completo:
```python
import math

math.sqrt(2)
```

Importar un módulo con un alias:
```python
import math as m

m.sqrt(2)
```

Importar solo ciertas funciones, o clases, de un módulo:
```python
from math import sqrt, sin

sqrt(2)
```

Importar todas las funciones y clases de un módulo (no recomendado debido a posibles conflictos de nombres):
```python
from math import *

sqrt(2)
```

Importar un módulo y asignar sus funciones, o clases, a un alias (no recomendado si quieres trabajar con otras personas y pretendes que entiendan tu código):
```python
from math import sqrt as raiz

raiz(2)
```

Importar un módulo desde un paquete:
```python
import package.module
```

Importar un módulo desde un paquete con un alias:
```python
import matplotlib.pyplot as plt
```

Importar un módulo desde un paquete y ciertas funciones o clases:
```python
from sympy.abc import x, y
```

Estas son algunas de las formas comunes de utilizar la declaración import en Python para importar módulos y elementos específicos de los mismos. 
Es importante elegir la forma más adecuada según las necesidades del proyecto y para mantener el código limpio y legible.

Algunos módulos ya vienen integrados en python, otros hay que instalarlos (por ejemplo con pip).

```shell
pip install numpy
```

**Nota**: A veces pip se llama pip3 para evitar confundirlo con el mismo comando de Python 2 (en general usaremos Python 3).

## Módulos comunes o entandar

**math**: Proporciona funciones matemáticas como sqrt() para calcular la raíz cuadrada, sin() para el seno de un ángulo, cos() para el coseno, etc.<br/>
https://docs.python.org/3/library/math.html

**random**: Se utiliza para generar números aleatorios y realizar operaciones relacionadas con la aleatoriedad, como la selección aleatoria de elementos de una lista o la generación de números aleatorios con ciertas distribuciones.

**os**: Proporciona funciones para interactuar con el sistema operativo, como acceder a variables de entorno, manipular rutas de archivos, crear y eliminar directorios, etc.

**datetime**: Permite trabajar con fechas y horas, incluyendo la creación de objetos de fecha/hora, el cálculo de diferencias entre fechas, el formato de fechas y horas, etc.

**json**: Se utiliza para trabajar con datos en formato JSON (JavaScript Object Notation), incluyendo la serialización y deserialización de datos entre objetos de Python y cadenas JSON.

**csv**: Proporciona funciones para leer y escribir archivos CSV (Comma Separated Values), que son utilizados comúnmente para almacenar datos tabulares.

...

## Módulos externos que usaremos en clase

**Sympy**: es una librería para facilitar la realización de cálculos matemáticos con variables sin necesidad de definir funciones nativas de Python.<br/>
https://docs.sympy.org/latest/index.html

**Scipy**: es una librería con diversas funciones para matemáticas y ingeniería.<br/>
https://docs.scipy.org/doc/scipy/reference/index.html

**Numpy**: es la librería para realizar cálculos y manipulación numérica por excelencia.<br/>
https://numpy.org/doc/stable/user/index.html

**Matplotlib**: es una librería para gráficos.<br/>
https://matplotlib.org/stable/users/index

...

# Comentarios en Python

**Comentarios de una línea**:
- Se inician con el símbolo #.
- Se extienden hasta el final de la línea.
- Se pueden usar para explicar una sola línea de código o para agregar una breve descripción.

**Comentarios multilínea**:
- Se inician con tres comillas simples (''') o tres comillas dobles (""").
- Se extienden hasta que se encuentran las tres comillas finales.
- Se pueden usar para explicar bloques de código o para agregar información más detallada.

```python
"""
Este es un comentario multilínea.
Se puede usar para explicar bloques de código
o para agregar información más detallada.
"""

# Esto es un comentario de una sola línea
print("Hola, mundo!")
```

# Tipos de variables en Python

En Python, existen diferentes tipos de variables. En python no hay que declarar las variables antes de ser utilizadas (como en C).

**Nota**: Si escribís mal el nombre variable al escribir en ella, se creará una nueva. Si intentáis leer un nombre de variable que no existe, os dará un error.

```python
foo = 4
...
fooo = foo + 1 # incrementamos el valor de foo en 1 (ERROR!)
```

Tipos de datos:

- Números:
  - Enteros (int): 1, 2, 3
  - Decimales (float): 1.5, 2.75
- Cadenas de texto (str): "Hola", 'mundo'.
- Booleanos (bool): True, False
- Listas (list): [1, 2, 3], ["a", 'b', "c"]. 
- Tuplas (tuple): (1, 2, 3), ("a", 'b', "c"). 
- Diccionarios (dict): {"nombre": "Ana", 'edad': 14}. 
- Conjuntos (set): {1, 2, 3}. 

**Números Enteros**:
- Hexadecimal: 0xabcd
- Decimal: 1234
- Octal: 0o1234
- Binario: 0b1001
- Cadena: int("1234"), int("1234", 10), int("0xabcd", 16), int("abcd", 16), int("1234", 8), int("0o1234", 8), int("0b1001", 2), int("1001", 2)

**Números Decimales**:
- Decimales: 1.0, 1., .2
- Exponente: 2e2 (200), 2e-2 (0.02)

**Cadenas**:
- "Se pueden usar comillas dobles".
- 'Se pueden usar comillas simples'.
- **Doc**: https://www.w3schools.com/python/python_ref_string.asp

**Listas**:
- Las listas son colecciones ordenadas y modificables de elementos.
- Definición y sintaxis: Se definen utilizando corchetes [], o la función ```list()```, y los elementos se separan por comas.
- Los elementos de una lista pueden ser de diferentes tipos (números, cadenas, otras listas, etc.).
- Se pueden acceder a los elementos de una lista mediante su índice, empezando desde 0.
- Se pueden modificar los elementos individuales de una lista, añadir nuevos elementos, eliminar elementos, o incluso cambiar toda la lista.
- **Doc**: https://www.w3schools.com/python/python_ref_list.asp

**Tuplas**:
- Las tuplas son colecciones ordenadas e inmutables de elementos.
- Definición y sintaxis: Se definen utilizando paréntesis ```()```, o la función ```tuple()``` (vacia y no se puede modificar), y los elementos se separan por comas.
- Al igual que las listas, los elementos de una tupla pueden ser de diferentes tipos.
- A diferencia de las listas, una vez creada una tupla, no se pueden modificar sus elementos.
- Se accede a los elementos de una tupla mediante su índice, igual que en las listas.
- **Doc**: https://www.w3schools.com/python/python_ref_tuple.asp

**Diccionarios**:
- Los diccionarios son colecciones no ordenadas de pares clave-valor.
- Definición y sintaxis: Se definen utilizando llaves ```{}```, o la función ```dict()```, y los pares clave-valor se separan por comas.
- Cada elemento del diccionario consiste en una clave única y su correspondiente valor.
- Los valores en un diccionario pueden ser de cualquier tipo, mientras que las claves deben ser inmutables (como cadenas, números o tuplas).
- Se accede a los valores de un diccionario mediante su clave, en lugar de su índice como en las listas y tuplas.
- Los diccionarios son útiles para representar datos estructurados y realizar búsquedas eficientes por claves.
- **Doc**: https://www.w3schools.com/python/python_ref_dictionary.asp

**Conjuntos**:
- Colección desordenada: Los conjuntos no mantienen un orden específico de los elementos. Esto significa que no puedes confiar en el orden en el que los elementos fueron agregados al conjunto.
- Elementos únicos: Los conjuntos no pueden contener elementos duplicados. Si intentas agregar un elemento que ya está presente en el conjunto, no se realizará ninguna acción.
- Mutabilidad: Los conjuntos son mutables, lo que significa que puedes agregar o eliminar elementos después de que el conjunto ha sido creado.
- Definición y sintaxis: Los conjuntos se definen utilizando llaves ```{}```, o la función ```set()```. 
- Operaciones de conjuntos: Los conjuntos admiten una variedad de operaciones comunes, como unión, intersección, diferencia y diferencia simétrica.
- Iteración: Puedes iterar sobre los elementos de un conjunto utilizando un bucle for, aunque el orden de los elementos puede variar en cada iteración.
- No indexación: Los conjuntos no admiten indexación ni slicing, ya que no mantienen un orden específico de los elementos.
- Un conjunto solo puede contener elementos de un tipo de dato hasheable: números, cadenas de caracteres, booleanos o tuplas.
- **Doc**: https://www.w3schools.com/python/python_ref_set.asp

**Nota**: Todas las colecciones, excepto los conjuntos, pueden contener elementos de cualquier tipo, incluido otros contenedores.

**Avanzado**: https://docs.python.org/3/library/stdtypes.html

**Avanzado**: https://docs.python.org/3/library/constants.html

## Slicing (rebanado) de listas, tuplas y otros tipos de secuencias:

Slicing es una técnica poderosa en Python que te permite acceder a subconjuntos de una secuencia, como una lista, tupla o cadena.

**Sintaxis**: secuencia[inicio:fin:paso]

- **secuencia**: La secuencia a la que se aplica el slicing.
- **inicio**: El índice del primer elemento a incluir. Por defecto, es 0 (el primer elemento).
- **fin**: El índice del último elemento a incluir. No se incluye el elemento en este índice. Por defecto, es el tamaño de la secuencia.
- **paso**: El número de elementos a saltar entre cada elemento incluido. Por defecto, es 1 (se incluyen todos los elementos).

```python
lista = ['a', 'b', 'c', 'd', 'e']

# Acceder al tercer elemento (recordad que se empieza a contar desde 0)
elemento = lista[2]
print(elemento) # Salida: 'c'

sublista = lista[2:]
print(sublista) # Salida: ['c', 'd', 'e']

sublista = lista[:3]
print(sublista) # Salida: ['a', 'b', 'c']

sublista = lista[2:4]
print(sublista) # Salida: ['c', 'd']

# Acceder a los elementos pares
sublista = lista[::2]
print(sublista) # Salida: ['a', 'c', 'e']

# Acceder a todos los elementos en orden inverso
sublista = lista[::-1]
print(sublista) # Salida: ['e', 'd', 'c', 'b', 'a']
```

## Constantes

- **True**: Representa el valor booleano verdadero. 
- **False**: Representa el valor booleano falso. 
- **None**: Representa la ausencia de valor o null. 

# Operadores 

## Operadores Aritméticos

Los operadores aritméticos en Python son símbolos que se utilizan para realizar operaciones matemáticas básicas. 

- Suma (+): Se utiliza para sumar dos números.
- Resta (-): Se utiliza para restar un número de otro.
- Multiplicación (*): Se utiliza para multiplicar dos números.
- División (/): Se utiliza para dividir un número por otro. Devuelve un resultado flotante.
- División entera (//): Se utiliza para dividir un número por otro y devolver el resultado como un número entero, truncando cualquier parte decimal.
- Módulo (%): Devuelve el resto de la división entre dos números.
- Exponente (**): Se utiliza para elevar un número a una potencia.

```python
a = 10
b = 3

suma = a + b
resta = a - b
multiplicacion = a * b
division = a / b
division_entera = a // b
modulo = a % b
exponente = a ** b

print("Suma:", suma)
print("Resta:", resta)
print("Multiplicación:", multiplicacion)
print("División:", division)
print("División entera:", division_entera)
print("Módulo:", modulo)
print("Exponente:", exponente)
```

## Operadores Lógicos

Los operadores lógicos en Python se utilizan para combinar expresiones booleanas y realizar operaciones de comparación. 

- AND: Devuelve True si ambas expresiones booleanas son True, de lo contrario devuelve False.
- OR: Devuelve True si al menos una de las expresiones booleanas es True, de lo contrario devuelve False.
- NOT: Devuelve True si la expresión booleana es False, y viceversa.
- XOR (^): Devuelve True si una, y solo una, de las expresiones booleanas es True; de lo contrario, devuelve False.

```python
x = True
y = False

resultado_and = x and y
resultado_or = x or y
resultado_not = not x
resultado_xor = x ^ y

print("Resultado de x AND y:", resultado_and)
print("Resultado de x OR y:", resultado_or)
print("Resultado de NOT x:", resultado_not)
print("Resultado de x XOR y:", resultado_xor)
```

## Operadores bit a bit

Permiten realizar operaciones con los bits individuales de un número entero.

- **&** : Y bit a bit
- **|** : O bit a bit
- **^** : XOR bit a bit
- **~** : Negación bit a bit
- **<<** : Desplazamiento a la izquierda
- **>>** : Desplazamiento a la derecha

```python
a = 5 # 0b101 en binario
b = 3 # 0b011 en binario

# Y bit a bit
c = a & b # 0b101 & 0b011 = 0b001 = 1
print(c)

# O bit a bit
d = a | b # 0b101 | 0b011 = 0b111 = 7
print(d)

# XOR bit a bit
e = a ^ b # 0b101 ^ 0b011 = 0b110 = 6
print(e)

# Negación bit a bit
f = ~a # ~0b101 = 0b1111111111111111111111111111111111111111111111111111111111111010 = -6
print(f)

# Desplazamiento a la izquierda
g = a << 1 # 0b101 << 1 = 0b1010 = 10
print(g)

# Desplazamiento a la derecha
h = a >> 1 # 0b101 >> 1 = 0b010 = 2
print(h)
```

## Operadores de Comparación

Los operadores de comparación en Python se utilizan para comparar dos valores y determinar la relación entre ellos. 

- Igualdad (==): Devuelve True si los dos operandos son iguales, de lo contrario devuelve False.
- Desigualdad (!=): Devuelve True si los dos operandos no son iguales, de lo contrario devuelve False.
- Mayor que (>): Devuelve True si el operando de la izquierda es mayor que el operando de la derecha, de lo contrario devuelve False.
- Menor que (<): Devuelve True si el operando de la izquierda es menor que el operando de la derecha, de lo contrario devuelve False.
- Mayor o igual que (>=): Devuelve True si el operando de la izquierda es mayor o igual que el operando de la derecha, de lo contrario devuelve False.
- Menor o igual que (<=): Devuelve True si el operando de la izquierda es menor o igual que el operando de la derecha, de lo contrario devuelve False.
- Identidad (is): Devuelve True si los dos operandos apuntan al mismo objeto en memoria, de lo contrario devuelve False.
- No identidad (is not): Devuelve True si los dos operandos no apuntan al mismo objeto en memoria, de lo contrario devuelve False.

```python
a = 5
b = 10
c = [1]
d = [1]
e = c

igualdad = (a == b)
desigualdad = (a != b)
mayor_que = (a > b)
menor_que = (a < b)
mayor_o_igual_que = (a >= b)
menor_o_igual_que = (a <= b)

print("Igualdad:", igualdad)
print("Desigualdad:", desigualdad)
print("Mayor que:", mayor_que)
print("Menor que:", menor_que)
print("Mayor o igual que:", mayor_o_igual_que)
print("Menor o igual que:", menor_o_igual_que)
print("Identidad:", c is d) # False
print("Identidad:", c is e) # True
print("No identidad:", c is not d) # True
print("No identidad:", c is not e) # False
```

## Precedencia de operadores y paréntesis

La precedencia de los operadores en Python determina el orden en el que se evalúan las expresiones en una operación. Aquí tienes una lista de la precedencia de los operadores, de mayor a menor:

- Paréntesis (): Los paréntesis tienen la mayor precedencia y se utilizan para forzar el orden de evaluación de las expresiones.
- Exponente **: Se evalúa de derecha a izquierda.
- Multiplicación *, División /, División Entera //, Módulo %: Estos operadores tienen la misma precedencia y se evalúan de izquierda a derecha.
- Suma +, Resta -: Estos operadores también tienen la misma precedencia y se evalúan de izquierda a derecha.

**Nota**: No todos los lenguajes de programación tienen la misma precedencia de operadores.

Cuando hay operadores con la misma precedencia, se evalúan de izquierda a derecha. Los paréntesis pueden anular esta precedencia y forzar la evaluación de una expresión antes que otra.

```python
resultado =  2 + 3  * 4   # 14
resultado = (2 + 3) * 4   # 20
```
# Indentación:

En Python, la indentación se utiliza para delimitar los bloques de código. Las instrucciones que forman parte de un bloque de código deben tener la misma indentación.

- Las variables y funciones definidas dentro de un bloque de código solo son visibles y accesibles dentro de ese bloque.
- El flujo de ejecución se ejecuta de forma secuencial dentro de un bloque de código.

# Condicionales

Los condicionales en Python son estructuras de control que permiten ejecutar diferentes bloques de código dependiendo de si se cumple una condición específica. 

**if**: El condicional if se utiliza para ejecutar un bloque de código si una condición es verdadera.

```python
if condicion:
    # Bloque de código a ejecutar si la condición es verdadera
    # ...
```

**if-else**: El condicional if-else se utiliza para ejecutar un bloque de código si una condición es verdadera y otro bloque de código si la condición es falsa.

```python
if condicion:
    # Bloque de código a ejecutar si la condición es verdadera
else:
    # Bloque de código a ejecutar si la condición es falsa
```

**if-elif-else**: El condicional if-elif-else se utiliza para evaluar múltiples condiciones en secuencia y ejecutar el bloque de código correspondiente al primer caso verdadero.

```python
if condicion1:
    # Bloque de código a ejecutar si la condicion1 es verdadera
elif condicion2:
    # Bloque de código a ejecutar si la condicion1 es falsa y la condicion2 es verdadera
else:
    # Bloque de código a ejecutar si ninguna de las condiciones anteriores es verdadera
```

# Bucles

Los bucles en Python son estructuras de control que permiten ejecutar un bloque de código repetidamente. 

**while**: El bucle while se utiliza para ejecutar un bloque de código mientras se cumpla una condición específica.

```python
while condicion:
    # Bloque de código a ejecutar mientras la condición sea verdadera
```

**Nota**: No existe do-while como en otros lenguajes de programación.

La forma de emular un bucle do ... while en python es la siguiente:

```python
while True:
  # Instrucciones del bucle
  if not condicion:
    break
```

**for**: El bucle for se utiliza para iterar sobre una secuencia (como una lista, una tupla, un diccionario, etc.) y ejecutar un bloque de código para cada elemento de la secuencia.

```python
for elemento in secuencia:
    # Bloque de código a ejecutar para cada elemento de la secuencia
```

**Break y Continue**: Dentro de bucles while y for, se pueden utilizar las palabras clave break y continue para controlar el flujo de ejecución del bucle.

**break** se utiliza para salir del bucle completamente cuando se cumple una condición.
**continue** se utiliza para pasar a la siguiente iteración del bucle sin ejecutar el resto del código en el bloque de bucle actual.

## Funciones útiles para bucles

- **enumerate**: Enumera los elementos de un iterable y devuelve una tupla con el índice y el elemento. Es útil para acceder a la posición actual y al elemento en un bucle.
- **len**: Devuelve la longitud de un iterable. Es útil para determinar el número de iteraciones que se necesitan en un bucle.
- **zip**: Combina dos o más iterables en una sola secuencia de tuplas.
- **map**: Aplica una función a cada elemento de un iterable y devuelve una nueva secuencia con los resultados.
- **filter**: Filtra los elementos de un iterable según una condición y devuelve una nueva secuencia con los elementos que cumplen la condición.
- **reversed**: Invierte el orden de los elementos de un iterable.
- **sorted**: Ordena los elementos de un iterable.
- **all**: Devuelve True si todos los elementos de un iterable son True.
- **any**: Devuelve True si al menos un elemento de un iterable es True.

**Nota**: Ver [funciones lambda](#funciones-lambda) más adelante.

```python
# Enumera los elementos de una lista y devuelve una tupla con el índice y el elemento.
lista = ["a", "b", "c"]

for indice, elemento in enumerate(lista):
  print(f"Índice: {indice}, Elemento: {elemento}")

# len() devuelve la longitud de una lista.
for i in range(len(lista)):
  print(lista[i])

# Combina dos listas en una sola secuencia de tuplas.
nombres = ["Ana", "Juan", "María"]
edades = [14, 15, 16]

for nombre, edad in zip(nombres, edades):
  print(f"Nombre: {nombre}, Edad: {edad}")

# Aplica una función a cada elemento de una lista y devuelve una nueva secuencia con los resultados.
lista = [1, 2, 3, 4, 5]

multiplicados = map(lambda x: x * 2, lista)

for numero in multiplicados:
  print(numero)

# Filtra los elementos de una lista según una condición y devuelve una nueva secuencia con los elementos que cumplen la condición.
lista = [1, 2, 3, 4, 5]

pares = filter(lambda x: x % 2 == 0, lista)

for numero in pares:
  print(numero)

# Invierte el orden de los elementos de una lista.
lista = ["a", "b", "c"]

for elemento in reversed(lista):
  print(elemento)

# Ordena los elementos de una lista.
lista = [2, 1, 3, 5, 4]

lista_ordenada = sorted(lista)
for numero in lista_ordenada:
  print(numero)

# Devuelve True si todos los elementos de una lista son True.
lista = [True, True, True]

print(all(lista))

# Devuelve True si al menos un elemento de una lista es True.
lista = [False, False, True]

resultado = any(lista)
print(resultado)
```

# List comprehension

La list comprehension es una característica de Python que permite crear listas de manera concisa y eficiente utilizando una sintaxis más compacta. Permite iterar sobre una secuencia y aplicar una expresión a cada elemento, todo en una sola línea de código. 

```python
# Ejemplo de list comprehension para generar una lista de cuadrados de números del 0 al 9
cuadrados = [x**2 for x in range(10)]
print(cuadrados)  # Output: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

En este ejemplo, la list comprehension ```[x**2 for x in range(10)]``` genera una lista de cuadrados de números del 0 al 9. La expresión ```x**2``` se aplica a cada elemento x de la secuencia ```range(10)```.

La sintaxis general de una list comprehension es la siguiente: [expresion for elemento in secuencia]

Donde expresion es la expresión que se aplica a cada elemento de la secuencia, elemento es una variable que representa cada elemento de la secuencia y secuencia es la secuencia sobre la cual se itera.

Además de esta forma básica, las list comprehension también pueden incluir condiciones para filtrar los elementos de la secuencia. Por ejemplo:

```python
# Ejemplo de list comprehension con una condición para filtrar números pares
numeros_pares = [x for x in range(10) if x % 2 == 0]
print(numeros_pares)  # Output: [0, 2, 4, 6, 8]
```

En este ejemplo, la condición if x % 2 == 0 filtra los números pares de la secuencia range(10). La list comprehension genera una lista con solo esos números.

```python
# Ejemplo de list comprehension con if-else al final para generar una lista de números pares y "impar" para los impares
numeros = ["impar" if x % 2 != 0 else x for x in range(10)]
print(numeros)  # Output: ['impar', 1, 'impar', 3, 'impar', 5, 'impar', 7, 'impar', 9]
```

En este caso, la list comprehension primero evalúa la condición x % 2 != 0, y si es verdadera, agrega el string 'impar'; de lo contrario, agrega el número x. Esto genera una lista con el string 'impar' para los números impares y los números mismos para los pares.

**Nota**: El uso del else después del for en una list comprehension no es válido en Python. Si necesitas incluir un if-else en una list comprehension, debes ubicarlo antes del for.

# Funciones y parámetros en Python

## Funciones:

En Python, las funciones son bloques de código reutilizables que puedes llamar desde otras partes del programa. Son una herramienta fundamental para organizar tu código y hacerlo más modular y fácil de mantener.

## Parámetros:

Los parámetros son variables que se pasan a una función cuando se llama. Permiten que la función reciba información del programa principal y la use para realizar su tarea.

**Sintaxis**:

La sintaxis básica para definir una función con parámetros es la siguiente:

```python
def nombre_de_la_funcion(parametro1, parametro2, ...):
  """Documentación de la función"""
  # Bloque de código de la función
  return valor_de_retorno
```

Ejemplo:
```python
def sumar(numero1, numero2):
  """Suma dos números."""
  return numero1 + numero2

resultado = sumar(10, 5)

print(resultado) # Imprime 15
```

En este ejemplo, la función sumar tiene dos parámetros: numero1 y numero2. La función suma estos dos números y devuelve el resultado.

**Tipos de parámetros**:

- Parámetros obligatorios: Son los parámetros que se deben especificar siempre que se llama a la función.
- Parámetros opcionales: Son los parámetros que tienen un valor predeterminado y no es necesario especificarlos al llamar a la función.
- Parámetros con nombre: Son los parámetros que se pueden especificar en cualquier orden al llamar a la función.

### Parámetros especiales

```args``` y ```kwargs``` son parámetros especiales que puedes usar en las funciones de Python para manejar un número variable de argumentos.

- **args** se usa para capturar un número **arbitrario** de argumentos posicionales. Estos argumentos se pasan a la función como una tupla.
- **kwargs** se usa para capturar un número **arbitrario** de argumentos con nombre. Estos argumentos se pasan a la función como un diccionario.

```python
def funcion(a, b=10, c=100):
  return a + b + c

funcion(1)      # 111
funcion(1, 2)   # 103
funcion(1, b=2) # 103
funcion(1, c=1) # 12
funcion()       # ERROR! a no tiene valor
funcion(b=3)    # ERROR! a no tiene valor
```

```python
def ejemplo_args(*args):
  """
  Esta función toma un número variable de argumentos posicionales y los imprime.
  """
  for arg in args:
    print(arg)

ejemplo_args(1, 2, 3, "Hola")
```

En este ejemplo, la función ```ejemplo_args``` toma un número variable de argumentos posicionales. El parámetro args es una tupla que contiene todos los argumentos que se pasaron a la función. El bucle for itera sobre la tupla args e imprime cada argumento.

```python
def ejemplo_kwargs(**kwargs):
  """
  Esta función toma un número variable de argumentos con nombre y los imprime.
  """
  for key, value in kwargs.items():
    print(f"{key}: {value}")

ejemplo_kwargs(nombre="Ana", edad=14, ciudad="Madrid")
```

En este ejemplo, la función ```ejemplo_kwargs``` toma un número variable de argumentos con nombre. El parámetro kwargs es un diccionario que contiene todos los argumentos con nombre que se pasaron a la función. El bucle for itera sobre el diccionario kwargs e imprime cada par clave-valor.

```python
def ejemplo_combinado(*args, **kwargs):
  """
  Esta función toma un número variable de argumentos posicionales y con nombre y los imprime.
  """
  print("Argumentos posicionales:")
  for arg in args:
    print(arg)
  print("Argumentos con nombre:")
  for key, value in kwargs.items():
    print(f"{key}: {value}")

ejemplo_combinado(1, 2, 3, "Hola", nombre="Ana", edad=14)
```

En este ejemplo, la función ```ejemplo_combinado``` toma tanto argumentos posicionales como argumentos con nombre. El parámetro args es una tupla que contiene todos los argumentos posicionales, y el parámetro kwargs es un diccionario que contiene todos los argumentos con nombre. La función imprime primero los argumentos posicionales, seguidos de los argumentos con nombre.

**Consejos**:
- Usa nombres descriptivos para las funciones y los parámetros.
- Documenta tus funciones para que sean más fáciles de entender.
- Divide tu código en funciones pequeñas y manejables.
- Prueba tus funciones para asegurarte de que funcionan correctamente.

## Funciones lambda

Una función lambda, también conocida como función anónima, es una pequeña función que se define en una sola línea. Se utiliza para definir funciones simples que se necesitan en un contexto específico y que no se necesitan en otras partes del código.

```python
# Sintaxis
# funcion_lambda = lambda argumentos: expresión

# Función lambda para calcular el cuadrado de un número
funcion_lambda = lambda x: x ** 2

resultado = funcion_lambda(5)

print(resultado) # 25
```

# Clases

**¿Qué son las clases?**

Las clases son una herramienta fundamental en la programación orientada a objetos (POO) que te permiten crear plantillas para definir objetos con características y comportamientos específicos. Son como moldes que se pueden usar para crear múltiples objetos con las mismas propiedades.

**¿Qué son los objetos?**

Los objetos son entidades que contienen datos y métodos. Los datos, también conocidos como atributos, definen las características del objeto. Los métodos son las acciones que el objeto puede realizar.

**¿Por qué usar clases?**

Las clases ofrecen varias ventajas:

- Reutilización de código: Permiten crear plantillas que se pueden usar para crear múltiples objetos con las mismas características y comportamientos.
- Modularidad: Ayudan a organizar el código en unidades modulares y fáciles de entender.
- Encapsulamiento: Permiten ocultar los detalles de implementación de un objeto y solo exponer las interfaces públicas.
- Herencia: Permiten crear nuevas clases a partir de clases existentes, reutilizando código y comportamiento.

**Ejemplo**:

Para crear una clase en Python, se utiliza la palabra clave class seguida del nombre de la clase y dos puntos (:). A continuación, se define el cuerpo de la clase, que contiene la definición de los atributos y métodos de la clase.

- **Atributos**: Son las variables que definen las características de un objeto.
- **Métodos**: Son las acciones que un objeto puede realizar (funciones).
- **Constructor**: Es un método especial que se llama al crear un nuevo objeto.
- **Herencia**: Permite crear nuevas clases a partir de clases existentes.
- **Polimorfismo**: Permite que diferentes objetos respondan al mismo mensaje de diferentes maneras.

```python
class Persona:
  def __init__(self, nombre, edad):
    self.nombre = nombre
    self.edad = edad

  def saludar(self):
    print(f"Hola, mi nombre es {self.nombre} y tengo {self.edad} años.")

persona1 = Persona("Ana", 14)
persona2 = Persona("Juan", 15)

persona1.saludar()
persona2.saludar()
```

**init**:
- Es un método especial que se define en las clases de Python.
- Se llama automáticamente cuando se crea un nuevo objeto de la clase.
- Se utiliza para inicializar los atributos del objeto.

**self**:
- Es una variable especial que se refiere al objeto actual.
- Se utiliza dentro de los métodos de la clase para acceder y modificar los atributos del objeto.

En este ejemplo:
- La clase Persona define dos atributos: nombre y edad.
- La clase Persona define un método: saludar.
- Se crean dos objetos de la clase Persona: persona1 y persona2.
- Se llama al método saludar de los objetos persona1 y persona2.
- El método __init__ de la clase Persona se llama automáticamente cuando se crean los objetos persona1 y persona2.
- El método __init__ inicializa los atributos nombre y edad de los objetos.
- El método saludar utiliza la variable self para acceder a los atributos nombre y edad del objeto actual.

## Otros métodos especiales de las clases

**repr**:
- Devuelve una representación legible para humanos del objeto.
- Se utiliza cuando se imprime el objeto en la consola.

**str**:
- Devuelve una representación del objeto como una cadena.
- Se utiliza cuando se convierte el objeto a una cadena.

**del**:
- Se llama automáticamente cuando se elimina un objeto.
- Se utiliza para liberar recursos que el objeto estaba utilizando.

```python
class Persona:
  def __init__(self, nombre, edad):
    self.nombre = nombre
    self.edad = edad

  def __repr__(self):
    return f"Persona(nombre='{self.nombre}', edad={self.edad})"

  def __str__(self):
    return f"{self.nombre} ({self.edad} años)"

  def __del__(self):
    print(f"Se ha eliminado el objeto {self.nombre}")

persona1 = Persona("Ana", 14)
print(persona1) # Puede llamarse a __repr__ o a __str__ si sólo existe uno de ellos
print(repr(persona1))
print(str(persona1))
del persona1
```

Salida:
Ana (14 años)
Persona(nombre='Ana', edad=14)
Ana (14 años)
Se ha eliminado el objeto Ana

## Herencia

¿Qué es la herencia?

La herencia es un mecanismo de la programación orientada a objetos (POO) que permite a una clase (conocida como clase hija o subclase) heredar los atributos y métodos de otra clase (conocida como clase padre o superclase).

¿Por qué usar la herencia?

Reutilización de código: Te permite evitar escribir el mismo código una y otra vez para crear clases con características similares.
Modularidad: Te permite dividir tu código en módulos independientes, lo que facilita su mantenimiento y comprensión.
Extensibilidad: Te permite crear nuevas clases a partir de clases existentes, lo que te permite aprovechar el código ya escrito.
¿Cómo funciona la herencia?

Para heredar de una clase en Python, se utiliza la palabra clave class seguida del nombre de la clase hija, dos puntos (:), y el nombre de la clase padre.

```python
class Persona:
  def __init__(self, nombre, edad):
    self.nombre = nombre
    self.edad = edad

  def saludar(self):
    print(f"Hola, mi nombre es {self.nombre} y tengo {self.edad} años.")

class Estudiante(Persona):
  def __init__(self, nombre, edad, escuela):
    super().__init__(nombre, edad)
    self.escuela = escuela

  def estudiar(self):
    print(f"{self.nombre} está estudiando en {self.escuela}.")

estudiante1 = Estudiante("Ana", 14, "Colegio San Francisco")

estudiante1.saludar()
estudiante1.estudiar()
```

En este ejemplo:
- La clase Estudiante hereda de la clase Persona.
- La clase Estudiante tiene un atributo adicional: escuela.
- La clase Estudiante tiene un método adicional: estudiar.
- El método __init__ de la clase Estudiante llama al método __init__ de la clase Persona para inicializar los atributos nombre y edad.
