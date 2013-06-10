# La librer�a googleVis
 
1. googleVis es una librer�a que proporciona una interfaz entre R y las herramientas Google Chart.  
2. Las funciones de la librer�a permiten representar datos con Google Chart Tools sin necesidad de hacer un "upload" de los datos a Google. Lo que s� se hace es referenciar a funciones javascript alojadas en Google.  
3. La salida de las funciones googleVis es un c�digo html que contiene los datos y referencias a las funciones javascript. Por tanto, para ver la salida se necesita un navegador con Flash y conexi�n a internet para renderizar el gr�fico.  
<br>
Website : http://code.google.com/p/google-motion-charts-with-r/
<br>
Website (blog): http://www.r-bloggers.com/search/googlevis  





--- 

# Gr�fico gvisMotionChart()

Para representar un gr�fico din�mico que responda a los eventos 
de usuario:


```r
library(googleVis)
data.pob.capitales <- data.pob.municipios[data.pob.municipios$Indicador == "Cifras absolutas" & 
    data.pob.municipios$CodMunicipio %in% c("ES705", "ES709"), ]
motion.capitales <- gvisMotionChart(data.pob.capitales, idvar = "Municipio", 
    timevar = "Anio", options = list(height = 350, width = 400))
plot(motion.capitales)
# print(motion.capitales,tag='chart')
```

\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart00.pdf}
\end{center}

--- 

# Gr�fico gvisMotionChart(): c�digo XML

Podemos ver el c�digo XML que contiene este objeto y lo podemos insertar como un widget


```r
# create gagdet
cat(createGoogleGadget(motion.capitales), file = "motionchart.xml")
# se sube el gadget a alg�n repositorio y se vincula en alguna p�gina
# https://sites.google.com/site/cpgonzal/
```



```
## <?xml version="1.0" encoding="UTF-8" ?> 
## <Module>
##   <ModulePrefs title="MotionChartIDfec48b13dbd" />
##   <Content type="html">
##   <![CDATA[ 
##    <!-- MotionChart generated in R 3.0.0 by googleVis 0.4.2 pa
```




--- 

# Gr�fico gvisGeoMap()


Podemos representar datos geo-espaciales utilizando las funciones de mapas:



```r
data.coords <- read.table("datos_coordenadas_canarias.txt", header = TRUE, sep = ",")

idx <- match(data.pob.capitales$CodMunicipio, data.coords$cod)

data.pob.capitales$LatLong <- paste(data.coords[idx, "latitude"], data.coords[idx, 
    "longitude"], sep = ":")

map.capitales <- gvisGeoMap(data.pob.capitales[data.pob.capitales$Anio == "2012", 
    ], locationvar = "LatLong", numvar = "Valor", options = list(region = "ES", 
    dataMode = "markers", showLegend = FALSE))
# Display chart
plot(map.capitales)
```


Esta funci�n no es muy adecuada para regiones que no est�n codificadas como ISO 3166-1 (http://www.iso.org/iso/iso-3166-1_decoding_table.html)

\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart01.png}
\end{center}

--- 

# Gr�fico gvisMap()

Podemos mejorar la representaci�n utilizando gvisMap:


```r
data.pob.capitales$Tip <- paste("Poblacion:", data.pob.capitales$Valor)

map.capitales <- gvisMap(data.pob.capitales[data.pob.capitales$Anio == "2012", 
    ], "LatLong", "Tip", options = list(enableScrollWheel = TRUE, mapType = "terrain", 
    useMapTypeControl = TRUE))
# Display chart
plot(map.capitales)
```

\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart02.png}
\end{center}

---   

# Tabla gvisTable()

Tambi�n se puede mostrar una representaci�n tabular de datos


```r
table.capitales <- gvisTable(data.pob.capitales, options = list(width = 800, 
    height = 470))
# Display chart
plot(table.capitales)

table.capitales <- gvisTable(data.pob.capitales, options = list(width = 800, 
    height = 470, page = "enable"))
# Display chart
plot(table.capitales)
```

\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart03.png}
\end{center}

---   

# Gr�fico gvisAnnotatedTimeLine()

Vemos un ejemplo de gr�ficos con serie temporal o l�neas:


```r
data.pob.capitales$Date <- as.Date(paste(data.pob.capitales$Anio, "-01-01", 
    sep = ""))


line.capitales <- gvisAnnotatedTimeLine(data.pob.capitales, datevar = "Date", 
    numvar = "Valor", idvar = "Municipio", date.format = "%d/%m/%Y", options = list(legendPosition = "newRow", 
        displayExactValues = "TRUE", width = 600, height = 550))

# Display chart
plot(line.capitales)
```

\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart04.png}
\end{center}

--- 

# Gr�fico gvisLineChart()


Vemos un ejemplo de gr�ficos de l�neas:


```r
## Line chart
data.pob.capitales2<-data.frame(Anio=data.pob.capitales[data.pob.capitales$Municipio==" TENERIFE","Anio"],
                                TENERIFE=data.pob.capitales[data.pob.capitales$Municipio==" TENERIFE","Valor"],
  			GRAN_CANARIA=data.pob.capitales[data.pob.capitales$Municipio==" GRAN CANARIA","Valor"])


line.capitales <- gvisLineChart(data.pob.capitales2,xvar="Anio",yvar=c("TENERIFE","GRAN_CANARIA"),
                                options=list(legend='right', width=600, height=400))
plot(line.capitales)
```

\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart05.png}
\end{center}


--- 


# Gr�fico gvisBarChart()


Vemos un ejemplo de gr�ficos de barras:


```r
## Bar chart
bar.capitales <- gvisBarChart(data.pob.capitales2, xvar = "Anio", yvar = c("TENERIFE", 
    "GRAN_CANARIA"), options = list(legend = "right", width = 600, height = 400))

plot(bar.capitales)
```

\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart06.png}
\end{center}


--- 

# Gr�fico gvisColumnChart()

Podemos representar gr�ficos columnas:


```r
## Column chart
col.capitales <- gvisColumnChart(data.pob.capitales2, xvar = "Anio", yvar = c("TENERIFE", 
    "GRAN_CANARIA"), options = list(legend = "right", width = 600, height = 400))
plot(col.capitales)

```

\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart07.png}
\end{center}

--- 

# Gr�fico gvisAreaChart()

Y gr�ficos de �reas:


```r
## Area chart
area.capitales <- gvisAreaChart(data.pob.capitales2, xvar = "Anio", yvar = c("TENERIFE", 
    "GRAN_CANARIA"), options = list(legend = "right", width = 600, height = 400))
plot(area.capitales)

```

\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart08.png}
\end{center}


--- 


# Gr�fico gvisSteppedAreaChart()

Veamos los gr�ficos de escalera:


```r
## Stepped Area Chart
step.capitales <- gvisSteppedAreaChart(data.pob.capitales2, xvar = "Anio", yvar = c("TENERIFE", 
    "GRAN_CANARIA"), options = list(isStacked = TRUE, width = 600, height = 400))
plot(step.capitales)
```


\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart09.png}
\end{center}

--- 

# Gr�fico gvisScatterChart()


Tambi�n se pueden representar gr�ficos de dos variables:


```r
data.pob.canarias <- data.pob.municipios[data.pob.municipios$Indicador %in% 
    c("Cifras absolutas", "Variaci�n interanual") & data.pob.municipios$CodMunicipio %in% 
    c("ES70"), ]

data.pob.canarias2 <- data.frame(CIFRAS_ABSOLUTAS = data.pob.canarias[data.pob.canarias$Indicador == 
    "Cifras absolutas", "Valor"], VAR_INTERANUAL = data.pob.canarias[data.pob.canarias$Indicador == 
    "Variaci�n interanual", "Valor"])

## Scatter chart
scatter.canarias <- gvisScatterChart(data.pob.canarias2, options = list(legend = "none", 
    pointSize = 2, vAxis = "{title:'Variacion interanual'}", hAxis = "{title:'Poblacion absoluta'}", 
    title = "Comparacion de poblacion absoluta y var. inter.", width = 600, 
    height = 600))
plot(scatter.canarias)
```


\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart10.png}
\end{center}

--- 


# Gr�fico gvisBubbleChart()

Un gr�fico de burbujas:


```r
data.pob.canarias2 <- data.frame(CIFRAS_ABSOLUTAS = data.pob.canarias[data.pob.canarias$Indicador == 
    "Cifras absolutas", "Valor"], VAR_INTERANUAL = data.pob.canarias[data.pob.canarias$Indicador == 
    "Variaci�n interanual", "Valor"], ANIO = data.pob.canarias[data.pob.canarias$Indicador == 
    "Variaci�n interanual", "Anio"])

## Bubble chart
bubble.canarias <- gvisBubbleChart(data.pob.canarias2, idvar = "ANIO", xvar = "CIFRAS_ABSOLUTAS", 
    yvar = "VAR_INTERANUAL", options = list(width = 600, height = 600))

plot(bubble.canarias)
```


\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart11.png}
\end{center}


--- 


# Gr�fico gvisBubbleChart()

Otro ejemplo del gr�fico de burbujas:


```r
data.pob.capitales <- data.pob.municipios[data.pob.municipios$Indicador %in% 
    c("Cifras absolutas", "Variaci�n interanual") & data.pob.municipios$CodMunicipio %in% 
    c("ES705", "ES709") & data.pob.municipios$Anio %in% c("2010", "2011", "2012"), 
    ]

data.pob.capitales2 <- data.frame(CIFRAS_ABSOLUTAS = data.pob.capitales[data.pob.capitales$Indicador == 
    "Cifras absolutas", "Valor"], VAR_INTERANUAL = data.pob.capitales[data.pob.capitales$Indicador == 
    "Variaci�n interanual", "Valor"], ANIO = data.pob.capitales[data.pob.capitales$Indicador == 
    "Variaci�n interanual", "Anio"], ISLA = data.pob.capitales[data.pob.capitales$Indicador == 
    "Variaci�n interanual", "Municipio"])

bubble.canarias <- gvisBubbleChart(data.pob.capitales2, idvar = "ISLA", xvar = "CIFRAS_ABSOLUTAS", 
    yvar = "VAR_INTERANUAL", colorvar = "ANIO", sizevar = "VAR_INTERANUAL", 
    options = list(width = 300, height = 300))

plot(bubble.canarias)
```



--- 


# Gr�fico gvisPieChart()

Un gr�fico de sectores (o de tarta):


```r
data.pob.canarias <- data.pob.municipios[data.pob.municipios$Indicador %in% 
    c("Cifras absolutas") & data.pob.municipios$CodMunicipio %in% c("ES70") & 
    data.pob.municipios$Anio %in% c("2010", "2011", "2012"), ]

data.pob.canarias2 <- data.frame(ANIO = as.character(data.pob.canarias[, "Anio"]), 
    CIFRAS_ABSOLUTAS = data.pob.canarias[, "Valor"])

## Pie chart
pie.canarias <- gvisPieChart(data.pob.canarias2, labelvar = "ANIO", numvar = "CIFRAS_ABSOLUTAS", 
    options = list(width = 600, height = 400))
plot(pie.canarias)

```

\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart12.png}
\end{center}


--- 


# Gr�fico gvisGauge()

Y los gr�ficos de calibraci�n:


```r
## Gauge
gauge.canarias <- gvisGauge(data.pob.canarias2, options = list(fontSize = 9, 
    min = 2e+06, max = 2200000, redFrom = 2e+06, redTo = 2100000, yellowFrom = 2100000, 
    yellowTo = 2150000, greenFrom = 2150000, greenTo = 2200000, width = 800, 
    height = 320))
plot(gauge.canarias)
```

\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart13.png}
\end{center}



--- 

# Gr�fico gvisOrgChart()

Tambi�n se pueden representar esquemas organizativos:



```r
data.org.canarias <- data.frame(ISLA = c("CANARIAS", "LANZAROTE", "FUERTEVENTURA", 
    "GRAN CANARIA", "TENERIFE", "LA GOMERA", "LA PALMA", "EL HIERRO"), PARENT = c(NA, 
    "GRAN CANARIA", "GRAN CANARIA", "CANARIAS", "CANARIAS", "TENERIFE", "TENERIFE", 
    "TENERIFE"), CODE = c("ES70", "ES708", "ES704", "ES705", "ES709", "ES706", 
    "ES707", "ES703"))

## Org chart
org.canarias <- gvisOrgChart(data.org.canarias, idvar = "ISLA", parentvar = "PARENT", 
    tipvar = "CODE", options = list(width = 600, height = 210, size = "large", 
        allowCollapse = TRUE))

plot(org.canarias)
```

\begin{center}
\includegraphics[width=0.4\textwidth]{figure/chart14.png}
\end{center}




