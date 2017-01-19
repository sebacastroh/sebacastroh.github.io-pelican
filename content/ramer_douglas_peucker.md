Title: Ramer-Douglas-Peucker
Date: 2017-01-19 13:00
Category: Algoritmos

## ¡Demasiados puntos!

Hace un tiempo tuve que leer desde Python unos archivos hechos en [AutoCad](https://es.wikipedia.org/wiki/DWG). Básicamente tuve que leer la geometría de distintos polígonos para luego continuar mi análisis. Sin embargo, no sospechaba la cantidad de puntos que podían estar contenidos en cada uno de los polígonos. Claramente para un amante del detalle, como yo, era genial tener una información tan precisa. Lamentablemente, el número de puntos era tan grande que mis rutinas se demoraban muchísimo más de lo que podía esperar.

Si uno observaba la geometría de los polígonos, fácilmente se podía dar cuenta que muchos puntos podrían ser simplificados a través de una recta. Obviamente sería una aproximacion, pero el resultado final no afectaría a mi modelización completa.

## Ideas al aire

La primera idea que tuve para solucionar este problema fue determinar los ángulos entre cada segmento del polígono e ir eliminando los puntos que estuvieran asociados a un ángulo menor a un umbral previamente definido. Para ejemplificarlo, consideremos que los puntos están ordenados en un arreglo [NumPy](http://www.numpy.org/) de tamaño $(n,2)$, con $n$ el número de puntos del polígono. Si es horario o anti-horario no nos afecta.

## Algo más serio

Considerando los problemas que tenía