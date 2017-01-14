Title: Cython
Date: 2017-01-14 11:37
Category: Review

Una de las ventajas de Python es su sencillez al momento de escribir un c\'odigo. Sin mebargo, no todo es tan maravilloso, hay un costo que pagar. Tal vez no nos damos cuenta porque la mayor\'ia de las veces no requerimos hacer c\'alculos muy pesados, pero las veces que los hacemos, no nos parece que la operaci\'on es demasiado lenta? Esto se debe a que, b\'asicamente, Python es un lenguaje interpretado.

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