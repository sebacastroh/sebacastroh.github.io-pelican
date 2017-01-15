Title: Cython
Date: 2017-01-14 11:37
Category: Review

Una de las ventajas de Python es su sencillez al momento de escribir un código. Sin embargo, no todo es tan maravilloso, hay un costo que pagar. Tal vez no nos damos cuenta porque la mayoría de las veces no requerimos hacer cálculos muy pesados, pero las veces que los hacemos, no nos parece que la operación es demasiado lenta? Esto se debe a que, básicamente, Python es un lenguaje interpretado.

```python
def sumcuad(x):
    s = 0.
    for i in xrange(len(x)):
        s += x[i]**2
    return s
```

Mientras que en Cython

```python
def sumcuad(double[::1] x):
    cdef double s = 0.
    cdef int i
    for i in xrange(len(x)):
        s += x[i]**2
    return s
```

Una integral $$\int_0^\infty e^{-x^2} dx$$

Otra prueba $\rm Hola$