Title: Ramer-Douglas-Peucker
Date: 2017-01-19 13:00
Category: Algoritmos

#�Demasiados puntos!

Hace un tiempo tuve que leer desde Python unos archivos hechos en [AutoCad](https://es.wikipedia.org/wiki/DWG). B�sicamente tuve que leer la geometr�a de distintos pol�gonos para luego continuar mi an�lisis. Sin embargo, no sospechaba la cantidad de puntos que pod�an estar contenidos en cada uno de los pol�gonos. Claramente para un amante del detalle, como yo, era genial tener una informaci�n tan precisa. Lamentablemente, el n�mero de puntos era tan grande que mis rutinas se demoraban much�simo m�s de lo que pod�a esperar.

Si uno observaba la geometr�a de los pol�gonos, f�cilmente se pod�a dar cuenta que muchos puntos podr�an ser simplificados a trav�s de una recta. Obviamente ser�a una aproximaci�n, pero el resultado final no afectar�a a mi modelizaci�n completa.

#Ideas al aire

La primera idea que tuve para solucionar este problema fue determinar los �ngulos entre cada segmento del pol�gono e ir eliminando los puntos que estuvieran asociados a un �ngulo menor a un umbral previamente definido. Para ejemplificarlo, consideremos que los puntos est�n ordenados en un arreglo [NumPy](http://www.numpy.org/) de tama�o $(n2)$, con $n$ el n�mero de puntos del pol�gono. Si es horario o anti-horario no nos afecta.