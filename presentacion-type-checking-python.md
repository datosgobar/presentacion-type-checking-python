title: Type checking en Python
output: index.html
controls: false
style: style.css

--
# Type checking en Python

-- separator
# "Function Annotations"
## Tiempo atrás, alguien propuso una **notación**...
## PEP 3107 (2006)

--
### Function Annotations - PEP 3107 (2006)

**Parámetros:**

```python
def foo(a: expression, b: expression = 5):
    ...
```

**Valores de retorno:**

```python
def sum() -> expression:
    ...
```

-- separator
# "Type Hints"
## Tiempo adelante, alguien propuso **usarla**...
## PEP 484 (2014)

--
### Type Hints - PEP 484 (2014)

**Se pueden anotar los tipos esperados de las variables**

```python
def greeting(name: str) -> str:
    return 'Hello ' + name
```

**Annotations en Python 3**

```python
def foo(a: str, b: int) -> str:
    return a + str(b)

foo.__annotations__
{'a': str, 'b': int, 'return': str}
```

--
### Type Hints - PEP 484 (2014)

**Podríamos tipar sólo algunas variables**

```python
def foo(a: str, b) -> str:
    # "b" puede ser cualquier cosa con un __str__
    return a + str(b)

foo.__annotations__
{'a': str, 'return': str}
```

-- separator
# Libs para type checking
## De terceros

--
### `mypy` en Python 3

`pip install mypy-lang`

**Si tengo un script como este en `foo_py3.py`:**

```python
def foo(a: str, b: int) -> str:
    return a + str(b)

print(foo("arbol", "manzana"))
```

**Lo puedo correr usando mypy para chequear tipos:**

```
mypy foo_py3.py

foo_py3.py:5: error: Argument 2 to "foo" has incompatible type "str"; expected "int"
```

--
### `mypy` en Python 2

**Con una sintaxis diferente, si tengo un script como este en `foo_py2.py`:**

```python
def foo(a, b):  # type: (str, int) -> str
    return a + " " + str(b)

print foo("arbol", "manzana")
```

**También lo puedo correr usando mypy para chequear tipos:**

```
mypy --py2 foo_py2.py

foo_py2.py:5: error: Argument 2 to "foo" has incompatible type "str"; expected "int"
```

--
### `typeguard` para hacer type checking en el intérprete

```
pip install typeguard
```

**Usando un decorador:**

```python
from typeguard import typechecked

@typechecked
def foo(a: str, b: int) -> str:
    return a + str(b)

foo("arbol", "manzana")

...

TypeError: type of argument b must be int; got str instead
```

-- separator
# El módulo `typing`
## Soporte para type checking en Python 3

--
### El módulo `typing`

**Tiene tipos más complejos**

*Iterable*

```python
from typing import Iterable

def greet_all(names: Iterable[str]) -> None:
    for name in names:
        print('Hello, {}'.format(name))
```

*Tuple*

```python
from typing import Tuple

def f(t: Tuple[int, str]) -> None:
    t = 1, 'foo'    # OK
    t = 'foo', 1    # Type check error
```

--
### El módulo `typing`

**Permite crear abstracciones convenientes**

*Un punto, un vector...*
```python
from typing import Tuple, List

Point = Tuple[float, float]
def distance(point: Point) -> float: ...

Vector = List[float]
def scale(scalar: float, vector: Vector) -> Vector: ...
```

*Una conexión a un servidor*
```python
from typing import Dict, Tuple, List

ConnectionOptions = Dict[str, str]
Address = Tuple[str, int]
Server = Tuple[Address, ConnectionOptions]
def broadcast_message(message: str, servers: List[Server]) -> None: ...
```

-- separator
# ¡Gracias!

<p align="center">**@agustinbenassi** de **@datosgobar**</p>

<p align="center">**https://github.com/datosgobar/presentacion-type-checking-python**</p>







