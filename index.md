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

## El entorno de R

R es un lenguaje de alto nivel y un entorno para la manipulación de datos, cálculo y gráficos.

> 1. Almacenamiento y manipulación efectiva de datos
> 2. Operadores para cálculo sobre variables indexadas y matrices
> 3. Amplia, coherente e integrada colección de herramientas para análisis de
datos
> 4. Grandes posibilidades gráficas
> 5. Lenguaje de programación orientado a objetos bien desarrollado, simple y efectivo
> 6. Lenguaje interpretado, no compilado. Posibilidad de usar scripts
> 7. Es de código abierto: se distribuye bajo la GPL (General Public License), que no impone ninguna restricción al uso de R (tanto académico como comercial). 
<br>
Website: http://www.r-project.org/
<br>


---

## ¿Por qué R?

Para alumnos:
> 1. Dispone de las herramientas clásicas de la estadistica
> 2. Es multiplataforma y gratis
> 3. Ofertas de trabajo

Para investigadores:
> 1. Desarrollos estadísticos avanzados
> 2. Proliferación de código R en muchos trabajos científicos

Para universidades:
> 1. Ahorro de licencias campus de software propietario (SPSS)
> 2. Implica menos problemas de soporte técnico

---

## Ventajas de R

> 1. Posibilidad de combinar análisis "empaquetados" en librerías con desarrollos propios "ad-hoc"
> 2. Gráficos de alta calidad exportables a distintos formatos
> 3. Consume pocos recursos informáticos
> 4. Puede ejecutarse remotamente y conectarse con otros programa (llamar a librerías de R desde PROC IML)

## Desventajas de R

> 1. Interfaz gráfica limitada (aunque se dispone de varios GUI que suplen esta deficiencia desde el punto de vista docente)

> 2. No hay soporte comercial 

> 3. El lenguaje de comandos es un lenguaje de programación


---

## Estructura de un sistema R

R consta de un sistema base (instalación primaria) pero se pueden extender las funcionalidades mediante librerías o paquetes (se instalan bajo demanda). Algunos de estos paquetes son:

mva: Classical multivariate analysis

maptools: Herramientas para el manejo de objetos geoespaciales

googleVis: Librería que sirve de interfaz entre R y Google chart tools

....


---

## Sesión de R


Se puede iniciar una sesión de R en modo terminal (en sistemas Linux) o empleando un R GUI (en sistemas windows). 

La interfaz de R para windows proporciona un menú muy básico para gestionar algunos aspectos de sesión de R:

> 1. El histórico de comandos (.Rhistory)
> 2. El espacio de trabajo de la sesión (.RData)
> 3. La instalación de librerías desde un repositorio CRAN


---

## Uso básico de R

<style>
pre {
  margin-bottom: -10px;
}
</style>


```r
(4 - 3) * 2/3
```

```
## [1] 0.6667
```

```r
sqrt(9)
```

```
## [1] 3
```

```r
sin(pi/2)
```

```
## [1] 1
```

```r
factorial(3)
```

```
## [1] 6
```


---

## Uso básico de R


```r
1/0
```

```
## [1] Inf
```

```r
0/0
```

```
## [1] NaN
```

```r
log(-1)
```

```
## Warning: Se han producido NaNs
```

```
## [1] NaN
```

```r
sqrt(-9)
```

```
## Warning: Se han producido NaNs
```

```
## [1] NaN
```


---

## Almacenar resultados en variables

El operador de asignación (<-) permite almacenar valores:

```r
a <- log(10)
a <- log(10)
a = log(10)  #¿cual usar: = o <-?
a <- rnorm(4, mean = 10, sd = 1)  # en R se utiliza = para asignar valores a los argumentos de las funciones
```


Al introducir los comandos anteriores, hemos creado un objeto en R: la variable "a". Este objeto se almacena en una zona de memoria llamada "espacio de trabajo".

```r
ls()
```

```
## [1] "a"
```


---

## La librería maptools

Para representar una variable en un mapa, lo más común es asociar al slot "data" los valores de la variable utilizando el comando merge(). Por ejemplo:


```r
censal.hombres <- data.comarcas.censal[data.comarcas.censal$sexo == "men", ]
```

```
## Error: objeto 'data.comarcas.censal' no encontrado
```

```r
canary.tmp <- merge(canary.counties@data, censal.hombres, by.x = "CODCOM", by.y = "comarca", 
    sort = FALSE)
```

```
## Error: objeto 'canary.counties' no encontrado
```

```r
canary.counties@data$sexoH <- canary.tmp$sexo
```

```
## Error: objeto 'canary.tmp' no encontrado
```

```r
canary.counties@data$censoH <- canary.tmp$censo
```

```
## Error: objeto 'canary.tmp' no encontrado
```


Tambien se puede utilizar el comando match(). Por ejemplo:

```r
censal.mujeres <- data.comarcas.censal[data.comarcas.censal$sexo == "women", 
    ]
```

```
## Error: objeto 'data.comarcas.censal' no encontrado
```

```r
idx <- match(canary.counties@data$CODCOM, censal.mujeres$comarca)
```

```
## Error: objeto 'canary.counties' no encontrado
```

```r
canary.counties@data$sexoM <- censal.mujeres$sexo[idx]
```

```
## Error: objeto 'censal.mujeres' no encontrado
```

```r
canary.counties@data$censoM <- censal.mujeres$censo[idx]
```

```
## Error: objeto 'censal.mujeres' no encontrado
```


---

## La librería maptools

Para representar un mapa de intensidad, necesitamos definir una paleta de colores y luego el comando spplot();


```r
library(classInt)
library(RColorBrewer)
n = 7
# obtener una paleta de 7 colores
pal <- brewer.pal(n, "Blues")
# obtener intervalos de clase para 7 colores
int <- classIntervals(canary.counties@data$censoH, n, style = "jenks")
```

```
## Error: objeto 'canary.counties' no encontrado
```

```r

p <- spplot(canary.counties["censoH"], col.regions = pal, at = signif(int$brks, 
    digits = 2), lwd = 0.4, col = "black")
```

```
## Error: no se pudo encontrar la función "spplot"
```

```r
p
```

```
## Error: objeto 'p' no encontrado
```


---

## La librería maptools

La comarca con menor valor del censo se puede quedar de color blanco: 


```r
# corrección del primer color de la escala
int$brks[1] <- 1000
# comprobar el orden de representación
canary.counties@data[order(canary.counties@data$censoH), ]
```


Podemos utilizar otras paletas:


```r
# Paletas

# display.brewer.pal(n, 'Blues')
pie(rep(1, n), col = brewer.pal(n, "Blues"))
pie(rep(1, n), col = brewer.pal(n, "YlOrRd"))
pie(rep(1, n), col = heat.colors(n))
pie(rep(1, n), col = terrain.colors(n))
```


---

## La librería maptools


```r
pal <- heat.colors(n)
p <- spplot(canary.counties["censoH"], col.regions = pal, at = signif(int$brks, 
    digits = 2), lwd = 0.4, col = "black")
```

```
## Error: no se pudo encontrar la función "spplot"
```

```r
p
```

```
## Error: objeto 'p' no encontrado
```


---

## La librería maptools

Se pueden utilizar otros métodos para los intervalos de clase:


```r
# Intervalos de clase
int <- classIntervals(canary.counties@data$censoH, n, style = "quantile")
```

```
## Error: objeto 'canary.counties' no encontrado
```

```r
int <- classIntervals(canary.counties@data$censoH, n, style = "pretty")
```

```
## Error: objeto 'canary.counties' no encontrado
```

```r
int <- classIntervals(canary.counties@data$censoH, n, style = "jenks")
```

```
## Error: objeto 'canary.counties' no encontrado
```


---

## La librería maptools

Podemos utilizar otros métodos de representación, plot() + legend():


```r
# Representaciones alternativas
plot(canary.counties, col = pal[findInterval(canary.counties@data$censoH, int$brks, 
    all.inside = TRUE)], axes = TRUE)
```

```
## Error: objeto 'canary.counties' no encontrado
```

```r
legend(x = -18, y = 30.5, legend = leglabs(round(int$brks)), cex = 0.9, fill = pal, 
    bty = "n", x.intersp = 0.5)
```

```
## Error: no se pudo encontrar la función "leglabs"
```


---

## La librería maptools

Otros métodos de representación, fortify()+ggplot2():
 

```r
# Otra mas
library(ggplot2)

# convertir el objeto 'SpatialPolygons' en data.frame
canary.fort <- fortify(canary.counties, region = "IDCOM27")
head(canary.fort)

canary.fort <- merge(canary.fort, canary.counties@data[, c("IDCOM27", "censoH")], 
    by.x = "id", by.y = "IDCOM27", sort = FALSE)

ggplot(data = canary.fort, aes(long, lat, group = group)) + geom_polygon(colour = "black", 
    fill = "white")
```


---

## La librería maptools

Entonces:


```
## Error: objeto 'canary.counties' no encontrado
```

```
## Error: objeto 'canary.fort' no encontrado
```

 

```r
map <- ggplot(data = canary.fort, aes(long, lat, group = group, fill = censoH)) + 
    geom_polygon() + geom_path(color = "white")
```

```
## Error: objeto 'canary.fort' no encontrado
```

```r
map
```

```
## Error: objeto 'map' no encontrado
```



---

## La librería maptools

Otras variantes con ggplot2():


```r
map + scale_fill_gradient(low = "white", high = "black")

map + scale_fill_gradient(name = "censo", breaks = c(10000, 50000, 90000))

map + scale_fill_gradientn(colours = brewer.pal(7, "Blues"), limits = c(1000, 
    1e+05))
```



---

## La librería maptools

Podemos utilizar escalas discretas en el gráfico:


```r
canary.fort$censoH.discreto <- cut(canary.fort$censoH, breaks = c(1000, 3000, 
    6000, 9000, 12000, 15000, 18000, 21000, Inf), labels = c("1000-3000", "3000-6000", 
    "6000-9000", "9000-12000", "12000-15000", "15000-18000", "18000-21000", 
    ">21000"), include.lowest = TRUE)

head(canary.fort)
```



```
## Error: objeto 'canary.fort' no encontrado
```


---

## La librería maptools

Entonces:


```r
map <- ggplot(data = canary.fort, aes(long, lat, group = group, fill = censoH.discreto)) + 
    geom_polygon() + geom_path(color = "white")
```

```
## Error: objeto 'canary.fort' no encontrado
```

```r

map
```

```
## Error: objeto 'map' no encontrado
```

```r
# map + scale_fill_brewer('Censo hombres total')
```



---

## La librería maptools

Podemos representar las comarcas de una isla:


```r
# canary.counties@data[canary.counties@data$CODISLA=='GC',]
idx <- canary.fort$id %in% canary.counties@data[canary.counties@data$CODISLA == 
    "GC", "IDCOM27"]
```

```
## Error: objeto 'canary.fort' no encontrado
```

```r
canary.fort2 <- canary.fort[idx, ]
```

```
## Error: objeto 'canary.fort' no encontrado
```

```r

map <- ggplot(data = canary.fort2, aes(long, lat, group = group, fill = censoH.discreto)) + 
    geom_polygon() + geom_path(color = "white")
```

```
## Error: objeto 'canary.fort2' no encontrado
```

```r

map
```

```
## Error: objeto 'map' no encontrado
```


---

## La librería maptools

Podemos representar con ggplot:


```r
canary.fort <- merge(canary.fort, canary.counties@data[, c("IDCOM27", "IDPROV", 
    "PROV", "CODISLA", "ISLA")], by.x = "id", by.y = "IDCOM27", sort = FALSE)
```

```
## Error: objeto 'canary.fort' no encontrado
```

```r

idx <- canary.fort$id %in% canary.counties@data[canary.counties@data$PROV == 
    "Santa Cruz de Tenerife", "IDCOM27"]
```

```
## Error: objeto 'canary.fort' no encontrado
```

```r

canary.fort2 <- canary.fort[idx, ]
```

```
## Error: objeto 'canary.fort' no encontrado
```

```r

map <- ggplot(data = canary.fort2, aes(long, lat, group = group, fill = censoH.discreto)) + 
    geom_polygon() + geom_path(color = "white")
```

```
## Error: objeto 'canary.fort2' no encontrado
```

```r

map + facet_grid(PROV ~ ISLA, scales = "free_x")
```

```
## Error: objeto 'map' no encontrado
```







