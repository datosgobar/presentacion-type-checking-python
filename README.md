# presentacion-tipado-estatico-python
Una nueva forma de tener tipos estáticos en python (PEP 484), usando una notación vieja (PEP 3107).

## Outline

1. Function Annotations - PEP 3107 (2006)
2. Type Hints - PEP 484 (2014)
3. Librerías de terceros para hacer type checking
    * `mypy` en Python 3
    * `mypy` en Python 2
    * `typeguard` en Python 3 (con Jupyter)

## Ejemplos

* **`foo_py2.py`**: Ejemplo de type checking para correr con `mypy` en Python 2 (`mypy --py2 examples/foo_py2.py`)
* **`foo_py3.py`**: Ejemplo de type checking para correr con `mypy` en Python 3 (`mypy examples/foo_py3.py`)
* **Funciones anotadas (python 3).ipynb**: Ejemplo para correr en jupyter con `typeguard`.
