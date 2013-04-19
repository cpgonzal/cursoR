---
title       : Curso de introducción y manejo de R 
subtitle    : HTML 5
author      : Carlos Pérez González
job         : Departamento de Estadística, Investigación Operativa y Computación (ULL) - Fundación Universidad Empresa (FEULL)
logo: Rlogo.jpg
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
theme       : default
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax, bootstrap, quiz]           # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
github:
 user: cpgonzal
 repo: cursoR
---

## La librería ggplot2

> 1. Es un paquete que permite generar gráficos estadísticos.
> 2. Se diferencia de otras librerías en el aspecto de controlar una gran número de componentes gráficos ("gramática de gráficos").
> 3. Los gráficos se pueden construir añadiéndole sucesivamente más atributos o capas ("layers").  <center>
<cite>*H.Wickham, ggplot2, Use R, DOI 10.1007/978-0-387-98141_1*</cite></center>
<center>http://had.co.nz/ggplot2</center>





--- &twocol w1:50% w2:50%

## Introducción a la librería ggplot2   
    
*** =left


```r
#cargar la librería 
library(ggplot2)
#un gráfico sencillo
qplot(data=data.geo.municipios, x=Superficie,   
      main="Histograma de superficie")
```

![plot of chunk plot01](figure/plot01.png) 


*** =right

Los comandos gráficos disponibles en ggplot2 son:
* qplot() - para "quick plots" 
* ggplot() - para mejor ajuste y control de todo


---

## Introducción a la librería ggplot2


```r
qplot(data=data.geo.islas,x=Superficie,main="Histograma de superficie",binwidth=10000)

qplot(data=data.geo.islas,x=Superficie,y=Altitud, main="Gráfico de superficie vs. altitud")

qplot(data=data.geo.islas,x=Superficie,y=Altitud, main="Gráfico de superficie vs. altitud", 
xlab="Superficie", ylab="Altitud")

qplot(data=data.geo.municipios,x=Superficie,y=Altitud, main="Gráfico de superficie vs. altitud", 
xlab="Superficie", ylab="Altitud",
xlim=c(0,2500),ylim=c(0,1500))
```



---

## Introducción a la librería ggplot2

### Color, tamaño, forma (aspectos estéticos)

Con el comando clásico plot(), si queremos representar  variables categóricas (e.g. una variable de tipo sexo, "Hombre","Mujer") con colores, debemos realizar nosotros mismos la 
correspondencia entre categoría y color.


En qplot() se puede especificar varios argumentos: colour, size, shape 

#### la vida en color

```r
qplot(data = data.geo.islas, x = Superficie, y = Altitud, colour = Isla, main = "Gráfico de superficie vs. altitud", 
    xlab = "Superficie", ylab = "Altitud")
```


#### el tamaño sí importa


```r
qplot(data = data.geo.islas, x = Superficie, y = Altitud, size = Isla, main = "Gráfico de superficie vs. altitud", 
    xlab = "Superficie", ylab = "Altitud")
```


#### dando forma a los puntos


```r
qplot(data = data.geo.islas, x = Superficie, y = Altitud, shape = Isla, main = "Gráfico de superficie vs. altitud", 
    xlab = "Superficie", ylab = "Altitud")
```



--- &twocol w1:45% w2:50%

## Introducción a la librería ggplot2   
    
*** =left

### Color, tamaño, forma (aspectos estéticos)

Con el comando clásico plot(), si queremos representar  variables categóricas (e.g. una variable de tipo sexo, "Hombre","Mujer") con colores, debemos realizar nosotros mismos la 
correspondencia entre categoría y color.

En qplot() se puede especificar varios argumentos: colour, size, shape 


*** =right

#### la vida en color

```r
qplot(data=data.geo.islas,x=Superficie,y=Altitud, colour = Isla,
main="Gráfico de superficie vs. altitud", 
xlab="Superficie", ylab="Altitud") 
```


#### el tamaño sí importa


```r
qplot(data=data.geo.islas,x=Superficie,y=Altitud, size = Isla,
main="Gráfico de superficie vs. altitud", 
xlab="Superficie", ylab="Altitud") 
```


#### sin perder las formas


```r
qplot(data=data.geo.islas,x=Superficie,y=Altitud, shape = Isla,
main="Gráfico de superficie vs. altitud", 
xlab="Superficie", ylab="Altitud") 
```


---

## Introducción a la librería ggplot2

### Objetos geométricos

qplot no está limitado a gráficos de dispersión (scatterplot), 
sino que puede producir casi cualquier tipo de gráfico variando 
el argumento geom.


* geom = "point" representa puntos para producir un scatterplot. Esta es la opción por 
defecto cuando se pasan argumentos x e y a qplot().
* geom = "boxplot" produce un gráfico box-and-whisker plot de resumen de la distribución
de un conjunto de puntos.
* geom = "smooth" ajusta una curva suavizada a los datos (smoother) y su
error estándar. Esta opción se combina con un argumento method %in% c("loess","gam","lm","rlm")
(ver http://docs.ggplot2.org/0.9.3/stat_smooth.html)
* geom = "path" and geom = "line" representa lineas entre los puntos.

---

## Introducción a la librería ggplot2


```r
qplot(data=data.geo.municipios,x=Superficie,y=Altitud, geom = "point")

qplot(data=data.geo.municipios,x=Superficie,y=Altitud, geom = "boxplot", colour = Isla)    # cuidado con el tipo de variables
qplot(data=data.geo.municipios,x=Isla,y=Altitud, geom = "boxplot")

qplot(data=data.geo.municipios,x=Superficie,y=Altitud, geom = "smooth", method="loess")
qplot(data=data.geo.municipios,x=Superficie,y=Altitud, geom = c("point", "smooth"), method="lm")

qplot(data=data.geo.municipios,x=Superficie,y=Altitud, geom = "path")
qplot(data=data.geo.municipios,x=Superficie,y=Altitud, geom = "line")
```


---

## Introducción a la librería ggplot2

Otros argumentos para geom para gráficos 1D (de una variable) son:

* geom = "histogram" representa un histograma.
* geom = "density"   representa un gráfico de densidad.
* geom = "bar"       representa un gráfico de barras.


```r
qplot(data=data.espacios.nat, x=Superficie, geom = "histogram")
qplot(data=data.espacios.nat, x=Superficie, geom = "density")

qplot(data=data.espacios.nat, x=Superficie, geom = "density", colour = Isla)   # las densidades son superpuestas
qplot(data=data.espacios.nat, x=Superficie, geom = "histogram", colour = Isla) # los histogramas son apilados y se colorea el borde
qplot(data=data.espacios.nat, x=Superficie, geom = "histogram", fill = Isla)   # los histogramas son apilados y se colorea el interior


qplot(data=data.espacios.nat, x=Espacio.natural, geom = "bar", fill = Isla) # también los gráficos de barras son apilados
qplot(data=data.espacios.nat, x=Espacio.natural, geom = "bar", fill = Isla, position="dodge") 
qplot(data=data.espacios.nat, x=Espacio.natural, geom = "bar", stat="identity", fill = Isla, position="dodge") 
```


---

## Introducción a la librería ggplot2

Veamos otros ejemplos con estos tipos de objetos geométricos


```r
qplot(data=data.geo.municipios, x=Provincia, geom = "bar")
qplot(data=data.geo.municipios, x=Provincia, geom = "bar", fill = Isla)

qplot(data=data.geo.municipios, x=Superficie, geom = "histogram")
qplot(data=data.geo.municipios, x=Superficie, geom = "density")

qplot(data=data.geo.municipios, x=Superficie, geom = "density", colour = Provincia)   # las densidades son superpuestas
qplot(data=data.geo.municipios, x=Superficie, geom = "histogram", colour = Provincia) # los hist. son apilados y se colorea el borde
qplot(data=data.geo.municipios, x=Superficie, geom = "histogram", fill = Provincia)   # los hist. son apilados y se colorea el interior

# las barras se pueden representar sin apilar  
qplot(data=data.geo.municipios, x=Superficie, geom = "histogram", fill = Provincia, position="dodge")  

```


---

## Introducción a la librería ggplot2


---

## Introducción a la librería ggplot2


---

## Introducción a la librería ggplot2










---

## Introducción a la librería ggplot2

#cargar la librería 

```r
library(ggplot2)
```


#cargar los datos utilizando read.table (en local)

```r
setwd("D:\\Mis documentos\\Presentaciones\\CursoR\\data")
data.espacios.nat <- read.table(file = "superficie_espacios_naturales.txt", 
    header = T, sep = ";")
```


--- .class1 #id1

## Slide 2

Slide Contents


```r
x <- 1 + 1 + 3
x
```

```
## [1] 5
```

```r
rnorm(5)
```

```
## [1] -1.15256 -0.35002 -2.07061  0.37765 -0.04519
```



--- &radio

## Widgets: jQuery-Quiz ##

This is a multiple choice question

1. Choice 1
2. `Choice 2`
3. _Choice 3 (correct)_
4. Choice 4

*** .hint

This is a hint

*** .explanation

This is the explanation

## La librería ggplot2

..ul: build

* Point 1
* Point 2
* Point 3

---




