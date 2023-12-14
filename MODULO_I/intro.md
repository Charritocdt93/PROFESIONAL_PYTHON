# Introducción

"Programar y desarrollar software" es como "saber escribir y ser redactor":
sin duda la primera habilidad es básica para la segunda, pero la segunda suele
integrar una metodología que aporta ciertas garantías al texto producido.
Con la primera entrenas la técnica y con la segunda, las estrategias para
una ejecución eficaz y duradera.

Programar consiste en automatizar tareas mientras que el desarrollo de
software guía estos esfuerzos para hacer del código fuente un artefacto
duradero, mantenible y fácil de cambiar.

El objetivo de este curso es enseñar programación en Python, desde la óptica
del desarrollo de software, intentando en todo momento producir código
legible y mantenible.

## Python


[Python](https://www.python.org/) es un lenguaje de programación creado en
a comienzos de los 90 por
[Guido van Rossum](https://en.wikipedia.org/wiki/Guido_van_Rossum).
Es un sucesor del lenguage
[ABC](https://en.wikipedia.org/wiki/ABC_%28programming_language%29), del que
toma la sintáxis de anidamiento basada en el sangrado del código fuente,
entre otras características. Además, a lo largo de su historia, Python ha
influenciado a otros lenguajes muy populares como JavaScript, Ruby, Go o Kotlin.
Entre las compañías que utilizan Python, se encuentran:
Instagram, Uber, Spotify, Dropbox, Netflix...

Python es también una [referencia](https://docs.python.org/3/reference/) y
existen diversas implementaciones siendo
[CPython](https://github.com/python/cpython) la implementación de referencia,
hecha en C. Existen implementaciones en .Net y Java pero se quedaron estancadas
en Python 2. La implementación alternativa más prometedora es
[PyPy](https://docs.python-guide.org/starting/which-python/#implementations),
enfocada en velocidad y escrita en
[RPython](https://rpython.readthedocs.io/en/latest/rpython.html).

Python es un lenguaje fuertemente y dinámicamente tipado, multiparadigma y con
sólidos modelos de ejecución y memoria. Su librería estándar es una de las
más completas incluyendo sistemas de logging, bibliotecas de red, un
frameworks de testing, herramientas de empaquetado y distribución,
virtualización de entornos, etc.

La comunidad de Python se organiza alrededor de la
[Python Software Foundation](https://www.python.org/psf/).

Python evoluciona gracias a las "proposiciones de mejoras de Python" o
**_PEP_** (Python Enhancement Proposal), en inglés. Los _PEP_ se definen en el
[PEP1](https://www.python.org/dev/peps/pep-0001/)
y se listan en el [PEP0](https://www.python.org/dev/peps/). A verces los PEP
no son implementables como características del lenguaje sino que recogen
recomendaciones.


PEP 20, Zen de Python:

> Hermoso es mejor que feo.

> Explícito es mejor que implícito.

> Simple es mejor que complejo.

> Complejo es mejor que complicado.

> No anidado es mejor que anidado.

> Escaso es mejor que denso.

> La legibilidad cuenta.

> Los casos especiales no son lo suficientemente especiales como para romper las reglas.

> La practicidad supera a la pureza.

> Los errores nunca deben pasarse por alto a menos que se silencien explícitamente.

> Ante la ambigüedad, rechaza la tentación de adivinar.

> Debería haber una, y preferiblemente solo una, manera obvia de hacerlo. Aunque esa manera puede no ser obvia al principio

> Ahora es mejor que nunca. Aunque nunca a menudo es mejor que en este momento.

> Si la implementación es difícil de explicar, es una mala idea.

> Si la implementación es fácil de explicar, puede ser una buena idea.

> Los espacios de nombres son una gran idea, ¡hagamos más de esos!

Las librerías de Python se organizan en torno al
[Python Package Index](https://pypi.org/), que es un repositorio de paquetes
instalables en los entornos Python. La interfaz de línea de comandos para
gestionar paquetes python es [pip](https://pypi.org/project/pip/).

Se puede encontrar más información sobre Python en los siguientes recursos:

- [Python Documentation](https://docs.python.org/3/)\*
- [Real Python Tutorials](https://realpython.com/)\*
- [News from the Python Sorftware Foundation](http://pyfound.blogspot.com/)
- [A brief history of Python](https://medium.com/@johnwolfe820/a-brief-history-of-python-ca2fa1f2e99e)
- [PEP20](https://www.python.org/dev/peps/pep-0020/)\*
- [Programming Language Influence Network](https://exploring-data.com/vis/programming-languages-influence-network/#Python)

## Comentarios.

En Python, los comentarios son líneas de texto que no se ejecutan como código y se utilizan para proporcionar información adicional dentro del código fuente. Aquí tienes algunas formas de trabajar con comentarios en Python:

### Comentarios de una sola línea:

```python
# Esto es un comentario de una sola línea
variable = 42  # También puedes colocar comentarios al final de una línea de código
```

### Comentarios de múltiples líneas:

```python
"""
Esto es un comentario
de múltiples líneas.
Puedes usar triple comillas simples (''') o dobles (""")
para encerrar bloques de comentarios de varias líneas.
"""
```

### Uso de comentarios para desactivar código:

```python
# Puedes comentar líneas de código para desactivarlas temporalmente
# Esto no se ejecutará:
# print("Este código está comentado")

# Pero esto sí se ejecutará:
print("Este código no está comentado")
```

### Comentarios para explicar el código:

```python
# Puedes usar comentarios para explicar el propósito de tu código
edad = 25  # Definimos la variable 'edad' y le asignamos el valor 25
```

### Docstrings (cadenas de documentación):

```python
def funcion_ejemplo(parametro):
    """
    Esta es una función de ejemplo que toma un parámetro.
    
    Args:
        parametro (int): Un número entero para ser procesado.
    
    Returns:
        str: Una cadena que indica el resultado del procesamiento.
    """
    # Código de la función...
    return resultado
```

- Los comentarios son útiles para hacer que tu código sea más comprensible y mantenible.
- Es importante encontrar un equilibrio, evitando comentarios innecesarios o redundantes.
- Los comentarios excesivos pueden hacer que el código sea difícil de leer. Un código claro y autodescriptivo es preferible siempre que sea posible.

## Variables y constantes.

En Python, las variables y constantes son formas de almacenar y manipular datos en un programa. Aunque Python no tiene un tipo de dato estricto llamado "constante" como algunos otros lenguajes, se sigue la convención de utilizar nombres en mayúsculas para indicar que una variable debe tratarse como una constante (es decir, que su valor no debería cambiar).

### Variables:

En Python, las variables se utilizan para almacenar datos y se crean mediante la asignación de un valor a un nombre. Puedes asignar cualquier tipo de dato a una variable, y no es necesario declarar explícitamente el tipo de la variable.

Ejemplo de variable:

```python
# Crear una variable llamada 'edad' y asignarle el valor 25
edad = 25

# Modificar el valor de la variable
edad = edad + 1
```

### Constantes:

Aunque Python no tiene un tipo de dato constante, se utiliza la convención de usar nombres en mayúsculas para indicar que una variable no debe cambiar su valor. Esto es una convención y no una restricción del lenguaje.

Ejemplo de constante (convención):

```python
# Crear una "constante" llamada PI y asignarle el valor de pi
PI = 3.14159
```

Es importante tener en cuenta que, a pesar de la convención, el valor de `PI` podría modificarse en el código. La convención simplemente indica que no debería cambiarse intencionalmente.

### Uso práctico:

```python
# Ejemplo de uso de variables y "constantes"

# Variables
nombre = "Juan"
edad = 30

# Constante (convención)
PI = 3.14159

# Imprimir información utilizando variables y constantes
print(f"{nombre} tiene {edad} años.")
print(f"El valor de PI es aproximadamente {PI}.")
```
## Tipos de datos.

Python es un lenguaje de programación dinámico y de tipado fuerte, lo que significa que las variables pueden cambiar de tipo durante la ejecución del programa, pero una vez que se asigna un tipo a una variable, se espera que su tipo no cambie de manera incoherente. Aquí están algunos de los tipos de datos principales en Python: 

1. **Numéricos:**
   - `int`: Números enteros, como -5, 0, 42.
   - `float`: Números de punto flotante, como 3.14, -0.5.
   - `complex`: Números complejos, como 1 + 2j.

    ```python
    numero_entero = 10
    numero_decimal = 3.14
    numero_complejo = 1 + 2j
    ```

2. **Secuencias:**
   - `str`: Cadenas de texto, como "Hola, mundo!".
   - `bytes`: Secuencias de bytes, utilizadas para representar datos binarios.

    ```python
    mensaje = "Hola, mundo!"
    datos_binarios = b'\x01\x02\x03'
    ```

3. **Booleanos:**
   - `bool`: Valores de verdad, `True` o `False`.

    ```python
    es_verdadero = True
    es_falso = False
    ```

4. **Secuencias mutables:**
   - `list`: Listas, secuencias ordenadas de elementos.
   - `bytearray`: Secuencias de bytes mutables.

    ```python
    lista_numeros = [1, 2, 3, 4, 5]
    byte_array = bytearray(b'\x01\x02\x03')
    ```

5. **Secuencias inmutables:**
   - `tuple`: Tuplas, secuencias inmutables.
   - `str`: Cadenas de texto son inmutables.

    ```python
    coordenadas = (3, 4)
    ```

6. **Conjuntos:**
   - `set`: Conjuntos, colecciones no ordenadas de elementos únicos.

    ```python
    conjunto_colores = {"rojo", "verde", "azul"}
    ```

7. **Diccionarios:**
   - `dict`: Diccionarios, pares clave-valor.

    ```python
    diccionario_persona = {"nombre": "Juan", "edad": 30, "ciudad": "Ejemplo"}
    ```

8. **Ningún tipo:**
   - `NoneType`: Representa la ausencia de valor o un valor nulo.

    ```python
    valor_nulo = None
    ```

9. **Booleano extendido:**
   - `True` y `False` son instancias de `bool`, pero también son equivalentes a `1` y `0` respectivamente.

    ```python
    verdadero_es_uno = True == 1
    falso_es_cero = False == 0
    ```
## Convirtiendo datos.

La conversión entre tipos de datos en Python se realiza mediante funciones o constructores específicos para cada tipo de dato. A continuación algunos ejemplos de cómo realizar conversiones entre tipos comunes:

1. **De entero a punto flotante:**

    ```python
    entero = 42
    flotante = float(entero)
    ```

2. **De punto flotante a entero (se trunca, no redondea):**

    ```python
    flotante = 3.14
    entero = int(flotante)
    ```

3. **De cadena a entero o punto flotante:**

    ```python
    cadena_entero = "123"
    entero_desde_cadena = int(cadena_entero)

    cadena_flotante = "3.14"
    flotante_desde_cadena = float(cadena_flotante)
    ```

4. **De entero o punto flotante a cadena:**

    ```python
    entero = 42
    cadena_desde_entero = str(entero)

    flotante = 3.14
    cadena_desde_flotante = str(flotante)
    ```

5. **De cadena a lista:**

    ```python
    cadena = "Hola"
    lista_desde_cadena = list(cadena)
    ```

6. **De lista a cadena:**

    ```python
    lista = ['H', 'o', 'l', 'a']
    cadena_desde_lista = ''.join(lista)
    ```

7. **De entero a carácter Unicode:**

    ```python
    entero = 65
    caracter_unicode = chr(entero)
    ```

8. **De carácter Unicode a entero:**

    ```python
    caracter_unicode = 'A'
    entero_desde_unicode = ord(caracter_unicode)
    ```

9. **De lista/tupla a conjunto:**

    ```python
    lista = [1, 2, 3, 4, 5]
    conjunto_desde_lista = set(lista)
    
    tupla = (1, 2, 3, 4, 5)
    conjunto_desde_tupla = set(tupla)
    ```

10. **De conjunto a lista:**

    ```python
    conjunto = {1, 2, 3, 4, 5}
    lista_desde_conjunto = list(conjunto)
    ```
## Operadores.

En Python, hay varios tipos de operadores que te permiten realizar diversas operaciones en variables y valores. Aquí están los tipos de operadores más comunes:

### 1. Operadores Aritméticos:

Realizan operaciones matemáticas básicas.

- Suma (`+`): Suma dos valores.
- Resta (`-`): Resta el segundo valor del primero.
- Multiplicación (`*`): Multiplica dos valores.
- División (`/`): Divide el primer valor por el segundo.
- División entera (`//`): Devuelve la parte entera de la división.
- Módulo (`%`): Devuelve el residuo de la división.
- Potenciación (`**`): Eleva el primer valor a la potencia del segundo.

```python
a = 5
b = 2

suma = a + b
resta = a - b
multiplicacion = a * b
division = a / b
division_entera = a // b
modulo = a % b
potenciacion = a ** b
```

### 2. Operadores de Comparación:

Comparan dos valores y devuelven un resultado booleano (`True` o `False`).

- Igual a (`==`): Comprueba si dos valores son iguales.
- No igual a (`!=`): Comprueba si dos valores son diferentes.
- Mayor que (`>`): Comprueba si el primer valor es mayor que el segundo.
- Menor que (`<`): Comprueba si el primer valor es menor que el segundo.
- Mayor o igual que (`>=`): Comprueba si el primer valor es mayor o igual que el segundo.
- Menor o igual que (`<=`): Comprueba si el primer valor es menor o igual que el segundo.

```python
x = 5
y = 10

igual = x == y
diferente = x != y
mayor_que = x > y
menor_que = x < y
mayor_o_igual = x >= y
menor_o_igual = x <= y
```

### 3. Operadores Lógicos:

Combina expresiones booleanas.

- `and`: Devuelve `True` si ambas expresiones son `True`.
- `or`: Devuelve `True` si al menos una de las expresiones es `True`.
- `not`: Devuelve `True` si la expresión es `False`, y viceversa.

```python
a = True
b = False

resultado_and = a and b
resultado_or = a or b
resultado_not = not a
```

### 4. Operadores de Pertenencia:

Comprueban si un valor está presente en una secuencia.

- `in`: Devuelve `True` si el valor está presente.
- `not in`: Devuelve `True` si el valor no está presente.

```python
lista = [1, 2, 3, 4, 5]

pertenece = 3 in lista
no_pertenece = 6 not in lista
```

### 5. Operadores de Identidad:

Comprueban si dos variables apuntan al mismo objeto en memoria.

- `is`: Devuelve `True` si ambas variables apuntan al mismo objeto.
- `is not`: Devuelve `True` si las variables no apuntan al mismo objeto.

```python
x = [1, 2, 3]
y = [1, 2, 3]
z = x

misma_referencia = x is z
distinta_referencia = x is not y
```
## Estructuras de control de flujo.

### Identación en Python:

Python utiliza la **identación** (sangría) en lugar de llaves o palabras clave para delimitar bloques de código. La identación es fundamental en Python y se utiliza para indicar la estructura y la jerarquía del código. Por ejemplo, en un bloque `if`, `else` o `for`, el código dentro del bloque debe estar indentado para indicar que pertenece a ese bloque.

```python
if condicion:
    # Bloque de código indentado
    # ...
else:
    # Otro bloque de código indentado
    # ...
```

La identación consiste generalmente en cuatro espacios, pero puede ser cualquier cantidad de espacios o tabuladores, siempre que sea consistente en todo el código. La identación clara y consistente es una práctica esencial en Python y facilita la lectura del código.

### Encoding en Python:

El **encoding** se refiere a la codificación de caracteres utilizada en un archivo de código fuente de Python. Específicamente, se trata de la forma en que se representan los caracteres en el archivo, y es importante para manejar correctamente caracteres especiales y caracteres no ASCII.

Por convención, al comienzo de un archivo de código fuente de Python, se puede especificar la codificación utilizando un comentario especial llamado "magic comment". Un ejemplo común es el siguiente:

```python
# -*- coding: utf-8 -*-
```

Esto indica que el archivo está codificado en UTF-8, que es una codificación ampliamente utilizada y compatible con caracteres internacionales.

La inclusión de este comentario no es estrictamente necesaria en muchos casos, ya que Python 3 utiliza UTF-8 como predeterminado. Sin embargo, en situaciones donde se pueden usar caracteres especiales, es una buena práctica incluirlo para evitar posibles problemas de codificación.

En Python, las estructuras de control de flujo permiten modificar el orden de ejecución de las instrucciones en un programa. Las principales estructuras de control de flujo en Python son:

### 1. Condicionales (if, elif, else):

La estructura condicional `if` permite ejecutar un bloque de código si una condición es verdadera. También puedes usar `elif` (abreviatura de "else if") para evaluar múltiples condiciones y `else` para proporcionar un bloque de código que se ejecutará si ninguna de las condiciones anteriores es verdadera.

```python
if condicion_1:
    # Bloque de código si condicion_1 es verdadera
elif condicion_2:
    # Bloque de código si condicion_2 es verdadera
else:
    # Bloque de código si ninguna condición es verdadera
```

### 2. Bucles (for, while):

- **Bucle `for`:** Se utiliza para iterar sobre una secuencia (como una lista, tupla o cadena) o sobre otros objetos iterables.

    ```python
    for elemento in secuencia:
        # Bloque de código a ejecutar para cada elemento
    ```

- **Bucle `while`:** Se ejecuta mientras una condición sea verdadera.

    ```python
    while condicion:
        # Bloque de código a ejecutar mientras la condición sea verdadera
    ```

### 3. Bucles con Control de Flujo (break, continue):

- **`break`:** Rompe el bucle actual antes de que se complete normalmente.

    ```python
    for elemento in secuencia:
        if condicion:
            break  # Sale del bucle si se cumple la condición
    ```

- **`continue`:** Salta a la siguiente iteración del bucle, omitiendo el resto del código en el bucle para esa iteración.

    ```python
    for elemento in secuencia:
        if condicion:
            continue  # Salta a la siguiente iteración si se cumple la condición
    ```

### 4. Gestión de Excepciones (try, except, finally):

La gestión de excepciones permite manejar errores y excepciones de manera controlada.

```python
try:
    # Bloque de código susceptible a generar una excepción
except TipoDeExcepcion as nombre_excepcion:
    # Bloque de código a ejecutar si se produce una excepción del tipo especificado
except OtroTipoDeExcepcion as otro_nombre:
    # Bloque de código a ejecutar si se produce otra excepción
else:
    # Bloque de código a ejecutar si no se produce ninguna excepción
finally:
    # Bloque de código que se ejecutará siempre, haya o no excepción
```

### 5. `pass`:

La instrucción `pass` no realiza ninguna acción y se utiliza como marcador de posición donde se requiere sintácticamente una declaración.

```python
if condicion:
    pass  # No hace nada, se utiliza como marcador de posición
else:
    # Otro bloque de código
```
## Ejemplo especificos sobre la estructuras de control iterativa `while` .

A continuación algunos ejemplos de cómo utilizar un bucle `while` en Python en diferentes situaciones:

### 1. Bucle `while` simple:

```python
contador = 0
while contador < 5:
    print("Iteración:", contador)
    contador += 1
```

Este bucle se ejecutará mientras la condición `contador < 5` sea verdadera.

### 2. Bucle `while` con `break`:

```python
contador = 0
while True:
    print("Iteración:", contador)
    contador += 1
    if contador >= 5:
        break
```

En este caso, el bucle se ejecutará indefinidamente hasta que se alcance la condición `contador >= 5`, momento en el que se utiliza `break` para salir del bucle.

### 3. Bucle `while` con `continue`:

```python
contador = 0
while contador < 5:
    contador += 1
    if contador == 3:
        continue  # Salta la iteración actual cuando contador es 3
    print("Iteración:", contador)
```

El bucle omitirá la impresión cuando `contador` sea igual a 3 debido a la instrucción `continue`.

### 4. Bucle `while` con entrada de usuario:

```python
respuesta = ""
while respuesta.lower() != "salir":
    respuesta = input("Escribe 'salir' para terminar: ")
    print("Tu respuesta:", respuesta)
```

Este bucle solicitará continuamente al usuario que ingrese una respuesta hasta que escriban "salir". La comparación `respuesta.lower() != "salir"` garantiza que sea insensible a mayúsculas y minúsculas.

### 5. Bucle `while` con límite de tiempo:

```python
import time

tiempo_inicial = time.time()
tiempo_limite = 5  # segundos
while time.time() - tiempo_inicial < tiempo_limite:
    print("El tiempo sigue siendo válido.")
    time.sleep(1)  # Hace que el bucle espere 1 segundo entre iteraciones
```

Este ejemplo utiliza el módulo `time` para limitar el tiempo de ejecución del bucle.

### 6. Bucle `while` con múltiples condiciones:

```python
contador = 0
suma = 0
while contador < 5 and suma < 10:
    suma += contador
    contador += 1
    print("Iteración:", contador, "Suma:", suma)
```

Este bucle se ejecutará mientras ambas condiciones `contador < 5` y `suma < 10` sean verdaderas.

Estos son solo ejemplos básicos; la flexibilidad de `while` permite adaptarlo a una variedad de situaciones en las que necesitas repetir un bloque de código hasta que se cumpla una condición específica.















## Libros recomendados

- [Clean Code](https://www.amazon.es/Clean-Code-Handbook-Software-Craftsmanship-ebook/dp/B001GSTOAM)\*
- [The Best Python Books](https://realpython.com/best-python-books/)

## _Awesome_ Python

Una [lista curada de las mejores bibliotecas de Python](https://github.com/vinta/awesome-python).