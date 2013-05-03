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

## La librería googleVis  


> 1. googleVis es una librería que proporciona una interfaz entre R y las herramientas Google Chart.  
> 2. Las funciones de la librería permiten representar datos con Google Chart Tools sin necesidad de hacer un "upload" de los datos a Google. Lo que sí se hace es referenciar a funciones javascript alojadas en Google.  
> 3. La salida de las funciones googleVis es un código html que contiene los datos y referencias a las funciones javascript. Por tanto, para ver la salida se necesita un navegador con Flash y conexión a internet para renderizar el gráfico.  
<br>
Website : http://code.google.com/p/google-motion-charts-with-r/
<br>
Website (blog): http://www.r-bloggers.com/search/googlevis  





---

## La librería googleVis



```r
library(googleVis)
data.pob.capitales <- data.pob.municipios[data.pob.municipios$Indicador == "Cifras absolutas" & 
    data.pob.municipios$CodMunicipio %in% c("ES705", "ES709"), ]
motion.capitales <- gvisMotionChart(data.pob.capitales, idvar = "Municipio", 
    timevar = "Anio", options = list(height = 350, width = 400))
# Display chart
plot(motion.capitales)
# print(motion.capitales,tag='chart')
```


<!-- MotionChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Fri May 03 22:05:50 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataMotionChartID21b45c4061fe () {
  var data = new google.visualization.DataTable();
  var datajson =
[
 [
 " GRAN CANARIA",
2012,
"2012",
"ES705",
"000000",
"Cifras absolutas",
852225 
],
[
 " GRAN CANARIA",
2011,
"2011",
"ES705",
"000000",
"Cifras absolutas",
850391 
],
[
 " GRAN CANARIA",
2010,
"2010",
"ES705",
"000000",
"Cifras absolutas",
845676 
],
[
 " GRAN CANARIA",
2009,
"2009",
"ES705",
"000000",
"Cifras absolutas",
838397 
],
[
 " GRAN CANARIA",
2008,
"2008",
"ES705",
"000000",
"Cifras absolutas",
829597 
],
[
 " GRAN CANARIA",
2007,
"2007",
"ES705",
"000000",
"Cifras absolutas",
815379 
],
[
 " GRAN CANARIA",
2006,
"2006",
"ES705",
"000000",
"Cifras absolutas",
807049 
],
[
 " GRAN CANARIA",
2005,
"2005",
"ES705",
"000000",
"Cifras absolutas",
802247 
],
[
 " GRAN CANARIA",
2004,
"2004",
"ES705",
"000000",
"Cifras absolutas",
790360 
],
[
 " GRAN CANARIA",
2003,
"2003",
"ES705",
"000000",
"Cifras absolutas",
789908 
],
[
 " GRAN CANARIA",
2002,
"2002",
"ES705",
"000000",
"Cifras absolutas",
771333 
],
[
 " GRAN CANARIA",
2001,
"2001",
"ES705",
"000000",
"Cifras absolutas",
755489 
],
[
 " GRAN CANARIA",
2000,
"2000",
"ES705",
"000000",
"Cifras absolutas",
741161 
],
[
 " TENERIFE",
2012,
"2012",
"ES709",
"000000",
"Cifras absolutas",
898680 
],
[
 " TENERIFE",
2011,
"2011",
"ES709",
"000000",
"Cifras absolutas",
908555 
],
[
 " TENERIFE",
2010,
"2010",
"ES709",
"000000",
"Cifras absolutas",
906854 
],
[
 " TENERIFE",
2009,
"2009",
"ES709",
"000000",
"Cifras absolutas",
899833 
],
[
 " TENERIFE",
2008,
"2008",
"ES709",
"000000",
"Cifras absolutas",
886033 
],
[
 " TENERIFE",
2007,
"2007",
"ES709",
"000000",
"Cifras absolutas",
865070 
],
[
 " TENERIFE",
2006,
"2006",
"ES709",
"000000",
"Cifras absolutas",
852945 
],
[
 " TENERIFE",
2005,
"2005",
"ES709",
"000000",
"Cifras absolutas",
838877 
],
[
 " TENERIFE",
2004,
"2004",
"ES709",
"000000",
"Cifras absolutas",
812839 
],
[
 " TENERIFE",
2003,
"2003",
"ES709",
"000000",
"Cifras absolutas",
799889 
],
[
 " TENERIFE",
2002,
"2002",
"ES709",
"000000",
"Cifras absolutas",
778071 
],
[
 " TENERIFE",
2001,
"2001",
"ES709",
"000000",
"Cifras absolutas",
744076 
],
[
 " TENERIFE",
2000,
"2000",
"ES709",
"000000",
"Cifras absolutas",
709365 
] 
];
data.addColumn('string','Municipio');
data.addColumn('number','Anio');
data.addColumn('string','CodAnio');
data.addColumn('string','CodMunicipio');
data.addColumn('string','CodIndicador');
data.addColumn('string','Indicador');
data.addColumn('number','Valor');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartMotionChartID21b45c4061fe() {
  var data = gvisDataMotionChartID21b45c4061fe();
  var options = {};
options["width"] =    400;
options["height"] =    350;

     var chart = new google.visualization.MotionChart(
       document.getElementById('MotionChartID21b45c4061fe')
     );
     chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  var chartid = "motionchart";

  // Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
  var i, newPackage = true;
  for (i = 0; newPackage && i < pkgs.length; i++) {
    if (pkgs[i] === chartid)
      newPackage = false;
  }
  if (newPackage)
    pkgs.push(chartid);

  // Add the drawChart function to the global list of callbacks
  callbacks.push(drawChartMotionChartID21b45c4061fe);
})();
function displayChartMotionChartID21b45c4061fe() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
    var pkgCount = pkgs.length;
    google.load("visualization", "1", { packages:pkgs, callback: function() {
      if (pkgCount != pkgs.length) {
        // Race condition where another setTimeout call snuck in after us; if
        // that call added a package, we must not shift its callback
        return;
      }
      while (callbacks.length > 0)
        callbacks.shift()();
    } });
  }, 100);
}
 
// jsFooter
 </script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartMotionChartID21b45c4061fe"></script>
 
<!-- divChart -->
  
<div id="MotionChartID21b45c4061fe"
  style="width: 400px; height: 350px;">
</div>



---   


## La librería maptools

> 1. Esta librería es un conjunto de herramientas para leer y manejar objetos espaciales. 
> 2. En particular, permite cargar archivos ESRI shapefiles (.shp).
> 3. Esta librería se suele utilizar en combinación con otras: sp (clases y métodos para datos geo-espaciales), RColorBrewer (paletas de colores) y ggplot2 (libraría gráfica).
<br>
Website (blog): http://rspatialtips.org.uk/
<br>
Tutorial: https://dl.dropbox.com/u/9577903/broomspatial.pdf





---

## La librería maptools

Cargamos los archivos de las 27 comarcas de canarias:



```r
library(maptools)
canary.counties <- readShapeLines(fn = "ISTAC_comarcas27_R.shp")
plot(canary.counties, axes = TRUE, col = "red")
```


![plot of chunk loadmap03](figure/loadmap03.png) 





---

## La librería maptools

Vamos a cargar el mapa en forma de polígonos (Poly Shape):



```r
canary.counties <- readShapePoly(fn = "ISTAC_comarcas27_R.shp")
plot(canary.counties, axes = TRUE, col = "red")
```


![plot of chunk loadmap06](figure/loadmap06.png) 



---

## La librería maptools

Para examinar el objeto canary.counties que hemos cargado:


```r
canary.counties
summary(canary.counties)

slotNames(canary.counties)
canary.counties@data
canary.counties@polygons[[1]]
```


Observamos que los ejes representados no corresponden a las escalas de latitud y longitud de un mapa:


```r
print(proj4string(canary.counties))
proj4string(canary.counties) <- "+proj=longlat +datum=WGS84"
print(proj4string(canary.counties))
plot(canary.counties, axes = TRUE)
```


---

## La librería maptools

Representar una variable en un mapa es algo que se puede hacer de múltiples formas. Por ejemplo:




---

## La librería maptools

---

## La librería maptools








---

## La librería ggplot2

> 1. Es un paquete que permite generar gráficos estadísticos.
> 2. Se diferencia de otras librerías en el aspecto de controlar una gran número de componentes gráficos ("gramática de gráficos").
> 3. Los gráficos se pueden construir añadiéndole sucesivamente más atributos o capas ("layers").  
<br>
Libro: <cite>H.Wickham (2009). ggplot2: Elegant Graphics for Data Analysis
123, Use R!, Springer</cite>
<br>
Website: http://had.co.nz/ggplot2
<br>
Tutorial: 
http://www.ceb-institute.org/bbs/wp-content/uploads/2011/09/handout_ggplot2.pdf





--- &twocol w1:50% w2:50%

## Introducción a la librería ggplot2   
    
*** =left


```r
#cargar la librería 
library(ggplot2)
#un gráfico sencillo
qplot(data=data.geo.municipios, x=Isla,   
      main="Municipios por isla")
```

![plot of chunk plot01](figure/plot01.png) 


*** =right

Los comandos gráficos disponibles en ggplot2 son:
* qplot() - para "quick plots" 
* ggplot() - para mejor ajuste y control de todo


---

## Introducción a la librería ggplot2

Veamos algunos ejemplos:


```r
qplot(data=data.geo.municipios,x=Superficie,main="Histograma de superficie",binwidth=50)

qplot(data=data.geo.islas,x=Superficie,y=Altitud, main="Gráfico de superficie vs. altitud")

qplot(data=data.geo.islas,x=Superficie,y=Altitud, main="Gráfico de superficie vs. altitud", 
xlab="Superficie de la isla", ylab="Altitud de la isla")

qplot(data=data.geo.islas,x=Superficie,y=Altitud, main="Gráfico de superficie vs. altitud", 
xlab="Superficie de la isla", ylab="Altitud de la isla",
xlim=c(0,2500),ylim=c(0,1500))
```



--- &twocol w1:45% w2:50%

## Introducción a la librería ggplot2   
    
*** =left

### Color, tamaño, forma (aspectos estéticos)

Con el comando clásico plot(), si queremos representar  variables categóricas (e.g. una variable de tipo sexo, "Hombre","Mujer") con colores, debemos realizar nosotros mismos la 
correspondencia entre categoría y color.

En qplot() se puede especificar varios argumentos: colour, size, shape 


*** =right

<!--- #### la vida en color
-->

```r
qplot(data=data.geo.islas,x=Superficie,y=Altitud, colour = Isla,
main="Gráfico de superficie vs. altitud", 
xlab="Superficie", ylab="Altitud") 
```


<!--- #### el tamaño sí importa
-->

```r
qplot(data=data.geo.islas,x=Superficie,y=Altitud, size = Isla,
main="Gráfico de superficie vs. altitud", 
xlab="Superficie", ylab="Altitud") 
```


<!--- #### sin perder las formas
-->

```r
qplot(data=data.geo.islas,x=Superficie,y=Altitud, shape = Isla,
main="Gráfico de superficie vs. altitud", 
xlab="Superficie", ylab="Altitud") +
scale_shape_manual(values=1:7)
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

Vemos algunos ejemplos:


```r
qplot(data=data.geo.municipios,x=Superficie,y=Altitud, geom = "point")

qplot(data=data.geo.municipios,x=Superficie,y=Altitud, geom = "boxplot", colour = Isla)    # cuidado con el tipo de variables
qplot(data=data.geo.municipios,x=Isla,y=Altitud, geom = "boxplot")

qplot(data=data.geo.municipios,x=Superficie,y=Altitud, geom = "smooth", method="loess")
qplot(data=data.geo.municipios,x=Superficie,y=Altitud, geom = c("point", "smooth"), method="lm")

qplot(data=data.geo.municipios,x=Superficie,y=Altitud, geom = "path")
qplot(data=data.geo.municipios,x=Superficie,y=Altitud, geom = "line")

qplot(data=data.geo.municipios, x=Provincia, geom = "bar")
qplot(data=data.geo.municipios, x=Superficie, geom = "histogram")
qplot(data=data.geo.municipios, x=Superficie, geom = "density")
```


---

## Introducción a la librería ggplot2

### Comprensión de la gramática de capas

* Podemos usar sólo qplot() pero la verdadera potencia de ggplot2 está en el manejo de 
los gráficos por capas (gramática de capas) mediante ggplot(). 

* El qplot recorta bastantes detalles de ggplot() a pesar que permite una sintaxis 
más familiar y cercana al plot().

* Con ggplot(), sin embargo, es posible incorporar a un gráfico diferentes niveles de detalle
mediante sucesivas capas (layers).

                        ggplot(data, mapping) +
                        layer( 
                              geom = "",  
                              stat = "",  
                              position = "", ....  
                             )


---

## Introducción a la librería ggplot2


### Algunos objetos geométricos en ggplot2

Name | Description  
------------- | -------------
abline | Line, specified by slope and intercept 
area | Area plots  
bar | Bars, rectangles with bases on y-axis  
boxplot | Box-and-whisker plot  
contour | Display contours of a 3d surface in 2d  
errorbar | Error bars  
histogram | Histogram  
line | Connect observations, in order of x value  
point | Points, as for a scatterplot  
polygon | Polygon, a filled path  
step | Connect observations by stairs  
text | Textual annotations  


---

## Introducción a la librería ggplot2

### Algunas transformaciones estadísticas en ggplot2

Name | Description  
------------- | -------------
bin | Bin data
boxplot | Calculate components of box-and-whisker plot
contour | Contours of 3d data
density | Density estimation
function | Superimpose a function
identity | Dont transform data
quantile | Continuous quantiles
smooth | Add a smoother
step | Create stair steps
sum | Sum unique values. Useful for overplotting on scatterplots
summary | Summarise y values at every unique x
unique | Remove duplicates  

--- 

## Introducción a la librería ggplot2

Un scatterplot:


```r
ejemplo1<-qplot(data=data.geo.municipios,x=Superficie,y=Altitud, colour = Isla)
```

se compone de (http://docs.ggplot2.org/current/index.html): 

* Un conjunto de datos por defecto (data).

* Una asignación de variables del conjunto de datos a atributos gráficos (aesthetics).


```r
  ejemplo1<-ggplot(data=data.geo.municipios, mapping=aes(x=Superficie,y=Altitud, colour=Isla))
```


--- 

## Introducción a la librería ggplot2

Y de las siguientes capas o layers:

* El tipo de objeto geométrico (punto, línea, barra, ...) utilizado para la representación (geom). 


```r
  ejemplo1 + layer(geom="point")  # o tambien: ejemplo1 + geom_point() 
```


* Una transformación estadística (suma, densidad, boxplot,..) de los datos (stat).


```r
  ejemplo1 + layer(geom="point", stat="identity" ) # o tambien: ejemplo1 + geom_point(stat="identity")  
# o tambien: ejemplo1 + geom_point()  
```


<img src="figure/unnamed-chunk-8.png" title="plot of chunk unnamed-chunk-8" alt="plot of chunk unnamed-chunk-8" style="display:block; margin:auto;" />


---

## Introducción a la librería ggplot2

Además, se puede

* Controlar cómo se asignan las variables del conjunto de datos a los atributos aesthetics (scales). 
Por ejemplo, la forma (shape) o el tamaño (size) de los objetos puede cambiar según el valor de las variables. 


```r
  ejemplo1<-ggplot(data=data.geo.municipios, mapping=aes(x=Superficie,y=Altitud, colour=Isla))

  ejemplo1 + geom_point(mapping=aes(shape=Provincia) ) + scale_shape(solid = FALSE)  # cambiar la forma
  
  ejemplo1 + geom_point(mapping=aes(size=Provincia) ) + scale_size_discrete(range = c(2, 4) ) # cambiar el tamaño
```



---

## Introducción a la librería ggplot2

Además, se puede

* Cambiar el sistema de representación de coordenadas (coord)


```r
  ejemplo1 + geom_point() + coord_polar()
```

* Especificar la visualización de subconjuntos de los datos en diferentes paneles (facet)


```r
  ejemplo1 + geom_point() + facet_grid(. ~ Provincia)
```


---

## Introducción a la librería ggplot2

Un diagrama de barras:


```r
ejemplo2<-qplot(data=data.geo.municipios,x=Provincia, geom = "bar", fill = Isla)
```


* La asignación o mapping de variables (atributos aesthetics):


```r
  ejemplo2<-ggplot(data=data.geo.municipios, mapping=aes(x=Provincia, fill=Isla))
```


* El tipo de objeto geom: 


```r
  ejemplo2 + layer(geom="bar")    # o tambien: ejemplo2 + geom_bar()  
```


---

## Introducción a la librería ggplot2

* La transformación estadística stat:


```r
  ejemplo2 + layer(geom="bar", stat="bin" )  
  # o tambien:  ejemplo2 + geom_bar(stat="bin")  
  # o tambien: ejemplo2 + geom_bar()
```

* El ajuste de posición en el gráfico (position):  


```r
  ejemplo2 + layer(geom="bar", stat="bin", position="dodge")  
  # o tambien:  ejemplo2 + geom_bar(position=position_dodge() )   
```


---

## Introducción a la librería ggplot2

Algunos ejemplos mas (densidad e histograma):


```r
qplot(data=data.espacios.nat, x=Superficie, geom = "density", colour = Isla)   
# las densidades son superpuestas
 
ggplot(data=data.espacios.nat, mapping=aes(x=Superficie,colour=Isla)) +geom_density()
```



```r
qplot(data=data.espacios.nat, x=Superficie, geom = "histogram", colour = Isla) 
# los histogramas son apilados y se colorea el borde

ggplot(data=data.espacios.nat, mapping=aes(x=Superficie,colour=Isla)) +geom_histogram()
```



```r
qplot(data=data.espacios.nat, x=Superficie, geom = "histogram", fill = Isla)   
# los histogramas son apilados y se colorea el interior

ggplot(data=data.espacios.nat, mapping=aes(x=Superficie,fill=Isla)) +geom_histogram()
```


---

## Introducción a la librería ggplot2

Algunos ejemplos mas (gráficos de barras):



```r
qplot(data=data.espacios.nat, x=Espacio.natural, geom = "bar", fill = Isla) 
# también los gráficos de barras son apilados

ggplot(data=data.espacios.nat, mapping=aes(x=Espacio.natural,fill=Isla)) +geom_bar(position=position_dodge() )

```

```r
qplot(data=data.espacios.nat, x=Espacio.natural, geom = "bar", fill = Isla, position="dodge") 
# barras colocadas unas al lado de otras

ggplot(data=data.espacios.nat, mapping=aes(x=Espacio.natural,fill=Isla)) +geom_bar()
```


---

## Introducción a la librería ggplot2

Algunos ejemplos mas:


```r
qplot(data=data.geo.municipios, x=Provincia, geom = "bar")

ggplot(data=data.geo.municipios, mapping=aes(x=Provincia)) +geom_bar()
```



```r
qplot(data=data.geo.municipios, x=Provincia, geom = "bar", fill = Isla)

ggplot(data=data.geo.municipios, mapping=aes(x=Provincia,fill = Isla)) +geom_bar()
```


---

## Introducción a la librería ggplot2

Algunos ejemplos mas:


```r
qplot(data=data.geo.municipios, x=Superficie, geom = "histogram")

ggplot(data=data.geo.municipios, mapping=aes(x=Superficie) +geom_histogram()

qplot(data=data.geo.municipios, x=Superficie, geom = "density")

ggplot(data=data.geo.municipios, mapping=aes(x=Superficie) +geom_density()
       
qplot(data=data.geo.municipios, x=Superficie, geom = "density", colour = Provincia)   # las densidades son superpuestas

ggplot(data=data.geo.municipios, mapping=aes(x=Superficie, colour = Provincia)) +geom_density()
```


---

## Introducción a la librería ggplot2

Algunos ejemplos mas:


```r
qplot(data=data.geo.municipios, x=Superficie, geom = "histogram", colour = Provincia)  
# los histogramas son apilados y se colorea el borde
       
       
qplot(data=data.geo.municipios, x=Superficie, geom = "histogram", fill = Provincia)  
# los histogramas son apilados y se colorea el interior

qplot(data=data.geo.municipios, x=Superficie, geom = "histogram", fill = Provincia, position="dodge")  
# las barras se pueden representar sin apilar
       
```



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
## [1] -2.010  1.560  1.150 -1.021 -1.655
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

## Introducción a la librería ggplot2

Otros argumentos de geom para gráficos 1D (de una variable) son:
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


