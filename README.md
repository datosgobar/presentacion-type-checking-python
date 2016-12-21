# presentacion-type-checking-python

Una nueva forma de tener type checking en python (PEP 484), usando una notación vieja (PEP 3107) - PyConAR 2016. [Ver presentación](https://datosgobar.github.io/presentacion-type-checking-python)

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Outline](#outline)
- [Ejemplos](#ejemplos)
- [Referencias](#referencias)
- [Herramientas usadas en la presentación](#herramientas-usadas-en-la-presentaci%C3%B3n)
- [Duración recomendada](#duraci%C3%B3n-recomendada)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Outline

1. Function Annotations - PEP 3107 (2006)
2. Type Hints - PEP 484 (2014)
3. Librerías de terceros para hacer type checking
    * `mypy` en Python 3
    * `mypy` en Python 2
    * `typeguard` en Python 3 (con Jupyter)
4. Tipos más complejos

## Ejemplos

* **`foo_py2.py`**: Ejemplo de type checking para correr con `mypy` en Python 2 (`mypy --py2 examples/foo_py2.py`)
* **`foo_py3.py`**: Ejemplo de type checking para correr con `mypy` en Python 3 (`mypy examples/foo_py3.py`)
* **`Funciones anotadas (python 3).ipynb`**: Ejemplo para correr en jupyter con `typeguard`.

## Referencias

*Nota: varios ejemplos de la presentación fueron tomados de las referencias.*

* [PEP 3107](https://www.python.org/dev/peps/pep-3107/): Esta PEP introduce una sintaxis para añadir anotaciones de metadata arbitrarias a funciones de Python.
* [PEP 484](https://www.python.org/dev/peps/pep-0484/): Esta PEP introduce un módulo provisional que define estándares y herramientas para implementar el chequeo de tipado en funciones de python usando la sintaxis propuesta en PEP 3107 para anotar funciones.

## Herramientas usadas en la presentación

* [Cleaver: 30-sec slideshows for Hackers](https://github.com/jdan/cleaver). Se escribe en Markdown y renderiza en html.

## Duración recomendada

5 minutos
