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

..ul: build

* Point 1
* Point 2
* Point 3

---

## La librería ggplot2

> 1. Es un paquete que permite generar gráficos estadísticos.
> 2. Se diferencia de otras librerías en el aspecto de controlar una gran número de componentes gráficos ("gramática de gráficos").
> 3. Los gráficos se pueden construir añadiéndole sucesivamente más atributos o capas ("layers").  <center>
<cite>*H.Wickham, ggplot2, Use R, DOI 10.1007/978-0-387-98141_1*</cite></center>
<center>http://had.co.nz/ggplot2</center>

---

## Aspectos de la librería ggplot2

#cargar la librería  

```r
library(ggplot2)
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
## [1] -0.8689 -0.2288  0.3083 -2.3512  0.3996
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




