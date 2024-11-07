# Sistemas de Ecuaciones Lineales: Resolución y Aplicaciones en Python

Los sistemas de ecuaciones lineales son conjuntos de ecuaciones que deben resolverse de manera simultánea. Resolver estos sistemas es una de las aplicaciones más importantes del álgebra lineal y se utiliza en múltiples campos, desde la ingeniería hasta la economía y las ciencias de la computación.

## Representación de Sistemas de Ecuaciones

Un sistema de ecuaciones lineales puede representarse de manera general como:

\[
\begin{cases}
a_{11}x_1 + a_{12}x_2 + \dots + a_{1n}x_n = b_1 \\
a_{21}x_1 + a_{22}x_2 + \dots + a_{2n}x_n = b_2 \\
\vdots \\
a_{m1}x_1 + a_{m2}x_2 + \dots + a_{mn}x_n = b_m
\end{cases}
\]

Donde los coeficientes \(a_{ij}\) y los términos independientes \(b_i\) son conocidos, y se busca encontrar los valores de \(x_1, x_2, \ldots, x_n\).

## Representación Matricial

El sistema anterior puede representarse de forma matricial como:

\[
\mathbf{A} \mathbf{x} = \mathbf{b}
\]

Donde:
- \(\mathbf{A}\) es la matriz de coeficientes.
- \(\mathbf{x}\) es el vector de incógnitas.
- \(\mathbf{b}\) es el vector de términos independientes.

## Resolución de Sistemas de Ecuaciones en Python

Python, a través de la biblioteca **NumPy**, permite resolver sistemas de ecuaciones lineales de manera eficiente utilizando la función `np.linalg.solve()`. Esta función es capaz de encontrar la solución exacta de un sistema si la matriz de coeficientes es cuadrada y no es singular.

Ejemplo de resolución de un sistema:

```python
import numpy as np

# Definición de la matriz de coeficientes
A = np.array([[2, 1, -1], [1, 3, 2], [1, -1, 2]])

# Definición del vector de términos independientes
b = np.array([8, 13, 3])

# Resolución del sistema
solucion = np.linalg.solve(A, b)
print("Solución del sistema:", solucion)
```

## Métodos Alternativos

Además del método directo con `np.linalg.solve()`, existen otros métodos para resolver sistemas de ecuaciones:

### Método de Eliminación de Gauss
Este método consiste en transformar la matriz de coeficientes en una matriz triangular superior para luego resolver por sustitución hacia atrás.

### Método de Gauss-Jordan
Es una extensión del método de Gauss que lleva la matriz a la forma de identidad, obteniendo la solución directamente.

## Consideraciones Numéricas

Al resolver sistemas de ecuaciones numéricamente, es importante considerar la estabilidad y precisión de los métodos. Las matrices mal condicionadas pueden provocar errores significativos en los resultados debido a la acumulación de errores de redondeo.

Ejemplo de verificación del condicionamiento de una matriz:

```python
condicion = np.linalg.cond(A)
print("Número de condición de la matriz A:", condicion)
```

Un número de condición elevado indica que el sistema puede ser sensible a pequeñas perturbaciones en los datos.

## Conclusión

La resolución de sistemas de ecuaciones lineales es una habilidad esencial en álgebra lineal y Python, junto con NumPy, proporciona herramientas robustas para abordar estos problemas de manera eficiente. En los próximos apartados, exploraremos métodos iterativos y cómo se aplican en casos donde la matriz no es cuadrada o cuando el sistema es sobredeterminado.

