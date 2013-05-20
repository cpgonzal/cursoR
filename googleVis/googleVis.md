# La librería googleVis
 
1. googleVis es una librería que proporciona una interfaz entre R y las herramientas Google Chart.  
2. Las funciones de la librería permiten representar datos con Google Chart Tools sin necesidad de hacer un "upload" de los datos a Google. Lo que sí se hace es referenciar a funciones javascript alojadas en Google.  
3. La salida de las funciones googleVis es un código html que contiene los datos y referencias a las funciones javascript. Por tanto, para ver la salida se necesita un navegador con Flash y conexión a internet para renderizar el gráfico.  
<br>
Website : http://code.google.com/p/google-motion-charts-with-r/
<br>
Website (blog): http://www.r-bloggers.com/search/googlevis  





--- 

# Gráfico gvisMotionChart()

Para representar un gráfico dinámico que responda a los eventos 
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



<!-- MotionChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 20 16:57:42 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataMotionChartIDfec48b13dbd () {
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
function drawChartMotionChartIDfec48b13dbd() {
  var data = gvisDataMotionChartIDfec48b13dbd();
  var options = {};
options["width"] =    450;
options["height"] =    350;

     var chart = new google.visualization.MotionChart(
       document.getElementById('MotionChartIDfec48b13dbd')
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
  callbacks.push(drawChartMotionChartIDfec48b13dbd);
})();
function displayChartMotionChartIDfec48b13dbd() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartMotionChartIDfec48b13dbd"></script>
 
<!-- divChart -->
  
<div id="MotionChartIDfec48b13dbd"
  style="width: 450px; height: 350px;">
</div>


--- 

# Gráfico gvisMotionChart(): código XML

Podemos ver el código XML que contiene este objeto y lo podemos insertar como un widget


```r
# create gagdet
cat(createGoogleGadget(motion.capitales), file = "motionchart.xml")
# se sube el gadget a algún repositorio y se vincula en alguna página
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

# Gráfico gvisGeoMap()


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


Esta función no es muy adecuada para regiones que no estén codificadas como ISO 3166-1 (http://www.iso.org/iso/iso-3166-1_decoding_table.html)


--- 

# Gráfico gvisMap()

Podemos mejorar la representación utilizando gvisMap:


```r
data.pob.capitales$Tip <- paste("Poblacion:", data.pob.capitales$Valor)

map.capitales <- gvisMap(data.pob.capitales[data.pob.capitales$Anio == "2012", 
    ], "LatLong", "Tip", options = list(enableScrollWheel = TRUE, mapType = "terrain", 
    useMapTypeControl = TRUE))
# Display chart
plot(map.capitales)
```



<!-- Map generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 20 16:57:42 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataMapIDfec3f8622cd () {
  var data = new google.visualization.DataTable();
  var datajson =
[
 [
 28.1157,
-15.4408,
"Poblacion: 852225" 
],
[
 28.4687,
-16.252,
"Poblacion: 898680" 
] 
];
data.addColumn('number','Latitude');
data.addColumn('number','Longitude');
data.addColumn('string','Tip');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartMapIDfec3f8622cd() {
  var data = gvisDataMapIDfec3f8622cd();
  var options = {};
options["showTip"] = true;
options["enableScrollWheel"] = true;
options["mapType"] = "terrain";
options["useMapTypeControl"] = true;

     var chart = new google.visualization.Map(
       document.getElementById('MapIDfec3f8622cd')
     );
     chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  var chartid = "map";

  // Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
  var i, newPackage = true;
  for (i = 0; newPackage && i < pkgs.length; i++) {
    if (pkgs[i] === chartid)
      newPackage = false;
  }
  if (newPackage)
    pkgs.push(chartid);

  // Add the drawChart function to the global list of callbacks
  callbacks.push(drawChartMapIDfec3f8622cd);
})();
function displayChartMapIDfec3f8622cd() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartMapIDfec3f8622cd"></script>
 
<!-- divChart -->
  
<div id="MapIDfec3f8622cd"
  style="width: 600px; height: 500px;">
</div>


---   

# Tabla gvisTable()

También se puede mostrar una representación tabular de datos


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



<!-- Table generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 20 16:57:42 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataTableIDfec50275462 () {
  var data = new google.visualization.DataTable();
  var datajson =
[
 [
 2000,
" GRAN CANARIA",
741161 
],
[
 2000,
" TENERIFE",
709365 
],
[
 2001,
" GRAN CANARIA",
755489 
],
[
 2001,
" TENERIFE",
744076 
],
[
 2002,
" GRAN CANARIA",
771333 
],
[
 2002,
" TENERIFE",
778071 
],
[
 2003,
" GRAN CANARIA",
789908 
],
[
 2003,
" TENERIFE",
799889 
],
[
 2004,
" GRAN CANARIA",
790360 
],
[
 2004,
" TENERIFE",
812839 
],
[
 2005,
" GRAN CANARIA",
802247 
],
[
 2005,
" TENERIFE",
838877 
],
[
 2006,
" GRAN CANARIA",
807049 
],
[
 2006,
" TENERIFE",
852945 
],
[
 2007,
" GRAN CANARIA",
815379 
],
[
 2007,
" TENERIFE",
865070 
],
[
 2008,
" GRAN CANARIA",
829597 
],
[
 2008,
" TENERIFE",
886033 
],
[
 2009,
" GRAN CANARIA",
838397 
],
[
 2009,
" TENERIFE",
899833 
],
[
 2010,
" GRAN CANARIA",
845676 
],
[
 2010,
" TENERIFE",
906854 
],
[
 2011,
" GRAN CANARIA",
850391 
],
[
 2011,
" TENERIFE",
908555 
],
[
 2012,
" GRAN CANARIA",
852225 
],
[
 2012,
" TENERIFE",
898680 
] 
];
data.addColumn('number','Anio');
data.addColumn('string','Municipio');
data.addColumn('number','Valor');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartTableIDfec50275462() {
  var data = gvisDataTableIDfec50275462();
  var options = {};
options["allowHtml"] = true;
options["width"] =    800;
options["height"] =    470;
options["page"] = "enable";

     var chart = new google.visualization.Table(
       document.getElementById('TableIDfec50275462')
     );
     chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  var chartid = "table";

  // Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
  var i, newPackage = true;
  for (i = 0; newPackage && i < pkgs.length; i++) {
    if (pkgs[i] === chartid)
      newPackage = false;
  }
  if (newPackage)
    pkgs.push(chartid);

  // Add the drawChart function to the global list of callbacks
  callbacks.push(drawChartTableIDfec50275462);
})();
function displayChartTableIDfec50275462() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartTableIDfec50275462"></script>
 
<!-- divChart -->
  
<div id="TableIDfec50275462"
  style="width: 800px; height: 470px;">
</div>


---   

# Gráfico gvisAnnotatedTimeLine()

Vemos un ejemplo de gráficos con serie temporal o líneas:


```r
data.pob.capitales$Date <- as.Date(paste(data.pob.capitales$Anio, "-01-01", 
    sep = ""))


line.capitales <- gvisAnnotatedTimeLine(data.pob.capitales, datevar = "Date", 
    numvar = "Valor", idvar = "Municipio", date.format = "%d/%m/%Y", options = list(legendPosition = "newRow", 
        displayExactValues = "TRUE", width = 600, height = 550))

# Display chart
plot(line.capitales)
```



<!-- AnnotatedTimeLine generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 20 16:57:42 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataAnnotatedTimeLineIDfec74697b80 () {
  var data = new google.visualization.DataTable();
  var datajson =
[
 [
 new Date(2012,0,1),
852225,
898680 
],
[
 new Date(2011,0,1),
850391,
908555 
],
[
 new Date(2010,0,1),
845676,
906854 
],
[
 new Date(2009,0,1),
838397,
899833 
],
[
 new Date(2008,0,1),
829597,
886033 
],
[
 new Date(2007,0,1),
815379,
865070 
],
[
 new Date(2006,0,1),
807049,
852945 
],
[
 new Date(2005,0,1),
802247,
838877 
],
[
 new Date(2004,0,1),
790360,
812839 
],
[
 new Date(2003,0,1),
789908,
799889 
],
[
 new Date(2002,0,1),
771333,
778071 
],
[
 new Date(2001,0,1),
755489,
744076 
],
[
 new Date(2000,0,1),
741161,
709365 
] 
];
data.addColumn('date','Date');
data.addColumn('number',' GRAN CANARIA');
data.addColumn('number',' TENERIFE');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartAnnotatedTimeLineIDfec74697b80() {
  var data = gvisDataAnnotatedTimeLineIDfec74697b80();
  var options = {};
options["width"] =    600;
options["height"] =    550;
options["legendPosition"] = "newRow";
options["displayExactValues"] = "TRUE";

     var chart = new google.visualization.AnnotatedTimeLine(
       document.getElementById('AnnotatedTimeLineIDfec74697b80')
     );
     chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  var chartid = "annotatedtimeline";

  // Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
  var i, newPackage = true;
  for (i = 0; newPackage && i < pkgs.length; i++) {
    if (pkgs[i] === chartid)
      newPackage = false;
  }
  if (newPackage)
    pkgs.push(chartid);

  // Add the drawChart function to the global list of callbacks
  callbacks.push(drawChartAnnotatedTimeLineIDfec74697b80);
})();
function displayChartAnnotatedTimeLineIDfec74697b80() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartAnnotatedTimeLineIDfec74697b80"></script>
 
<!-- divChart -->
  
<div id="AnnotatedTimeLineIDfec74697b80"
  style="width: 600px; height: 550px;">
</div>


--- 


# Gráfico gvisBarChart()


Vemos un ejemplo de gráficos de barras:


```r
## Bar chart
bar.capitales <- gvisBarChart(data.pob.capitales2, xvar = "Anio", yvar = c("TENERIFE", 
    "GRAN_CANARIA"), options = list(legend = "right", width = 600, height = 400))

plot(bar.capitales)
```


<!-- BarChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 20 16:57:42 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataBarChartIDfec64bd53fe () {
  var data = new google.visualization.DataTable();
  var datajson =
[
 [
 2012,
898680,
852225 
],
[
 2011,
908555,
850391 
],
[
 2010,
906854,
845676 
],
[
 2009,
899833,
838397 
],
[
 2008,
886033,
829597 
],
[
 2007,
865070,
815379 
],
[
 2006,
852945,
807049 
],
[
 2005,
838877,
802247 
],
[
 2004,
812839,
790360 
],
[
 2003,
799889,
789908 
],
[
 2002,
778071,
771333 
],
[
 2001,
744076,
755489 
],
[
 2000,
709365,
741161 
] 
];
data.addColumn('number','Anio');
data.addColumn('number','TENERIFE');
data.addColumn('number','GRAN_CANARIA');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartBarChartIDfec64bd53fe() {
  var data = gvisDataBarChartIDfec64bd53fe();
  var options = {};
options["allowHtml"] = true;
options["legend"] = "right";
options["width"] =    600;
options["height"] =    400;

     var chart = new google.visualization.BarChart(
       document.getElementById('BarChartIDfec64bd53fe')
     );
     chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  var chartid = "corechart";

  // Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
  var i, newPackage = true;
  for (i = 0; newPackage && i < pkgs.length; i++) {
    if (pkgs[i] === chartid)
      newPackage = false;
  }
  if (newPackage)
    pkgs.push(chartid);

  // Add the drawChart function to the global list of callbacks
  callbacks.push(drawChartBarChartIDfec64bd53fe);
})();
function displayChartBarChartIDfec64bd53fe() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartBarChartIDfec64bd53fe"></script>
 
<!-- divChart -->
  
<div id="BarChartIDfec64bd53fe"
  style="width: 600px; height: 400px;">
</div>


--- 

# Gráfico gvisColumnChart()

Podemos representar gráficos columnas:


```r
## Column chart
col.capitales <- gvisColumnChart(data.pob.capitales2, xvar = "Anio", yvar = c("TENERIFE", 
    "GRAN_CANARIA"), options = list(legend = "right", width = 600, height = 400))
plot(col.capitales)

```


<!-- ColumnChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 20 16:57:43 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataColumnChartIDfec2c0c38b9 () {
  var data = new google.visualization.DataTable();
  var datajson =
[
 [
 2012,
898680,
852225 
],
[
 2011,
908555,
850391 
],
[
 2010,
906854,
845676 
],
[
 2009,
899833,
838397 
],
[
 2008,
886033,
829597 
],
[
 2007,
865070,
815379 
],
[
 2006,
852945,
807049 
],
[
 2005,
838877,
802247 
],
[
 2004,
812839,
790360 
],
[
 2003,
799889,
789908 
],
[
 2002,
778071,
771333 
],
[
 2001,
744076,
755489 
],
[
 2000,
709365,
741161 
] 
];
data.addColumn('number','Anio');
data.addColumn('number','TENERIFE');
data.addColumn('number','GRAN_CANARIA');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartColumnChartIDfec2c0c38b9() {
  var data = gvisDataColumnChartIDfec2c0c38b9();
  var options = {};
options["allowHtml"] = true;
options["legend"] = "right";
options["width"] =    600;
options["height"] =    400;

     var chart = new google.visualization.ColumnChart(
       document.getElementById('ColumnChartIDfec2c0c38b9')
     );
     chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  var chartid = "corechart";

  // Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
  var i, newPackage = true;
  for (i = 0; newPackage && i < pkgs.length; i++) {
    if (pkgs[i] === chartid)
      newPackage = false;
  }
  if (newPackage)
    pkgs.push(chartid);

  // Add the drawChart function to the global list of callbacks
  callbacks.push(drawChartColumnChartIDfec2c0c38b9);
})();
function displayChartColumnChartIDfec2c0c38b9() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartColumnChartIDfec2c0c38b9"></script>
 
<!-- divChart -->
  
<div id="ColumnChartIDfec2c0c38b9"
  style="width: 600px; height: 400px;">
</div>


--- 

# Gráfico gvisAreaChart()

Y gráficos de áreas:


```r
## Area chart
area.capitales <- gvisAreaChart(data.pob.capitales2, xvar = "Anio", yvar = c("TENERIFE", 
    "GRAN_CANARIA"), options = list(legend = "right", width = 600, height = 400))
plot(area.capitales)

```


<!-- AreaChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 20 16:57:43 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataAreaChartIDfec53bf3e6a () {
  var data = new google.visualization.DataTable();
  var datajson =
[
 [
 2012,
898680,
852225 
],
[
 2011,
908555,
850391 
],
[
 2010,
906854,
845676 
],
[
 2009,
899833,
838397 
],
[
 2008,
886033,
829597 
],
[
 2007,
865070,
815379 
],
[
 2006,
852945,
807049 
],
[
 2005,
838877,
802247 
],
[
 2004,
812839,
790360 
],
[
 2003,
799889,
789908 
],
[
 2002,
778071,
771333 
],
[
 2001,
744076,
755489 
],
[
 2000,
709365,
741161 
] 
];
data.addColumn('number','Anio');
data.addColumn('number','TENERIFE');
data.addColumn('number','GRAN_CANARIA');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartAreaChartIDfec53bf3e6a() {
  var data = gvisDataAreaChartIDfec53bf3e6a();
  var options = {};
options["allowHtml"] = true;
options["legend"] = "right";
options["width"] =    600;
options["height"] =    400;

     var chart = new google.visualization.AreaChart(
       document.getElementById('AreaChartIDfec53bf3e6a')
     );
     chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  var chartid = "corechart";

  // Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
  var i, newPackage = true;
  for (i = 0; newPackage && i < pkgs.length; i++) {
    if (pkgs[i] === chartid)
      newPackage = false;
  }
  if (newPackage)
    pkgs.push(chartid);

  // Add the drawChart function to the global list of callbacks
  callbacks.push(drawChartAreaChartIDfec53bf3e6a);
})();
function displayChartAreaChartIDfec53bf3e6a() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartAreaChartIDfec53bf3e6a"></script>
 
<!-- divChart -->
  
<div id="AreaChartIDfec53bf3e6a"
  style="width: 600px; height: 400px;">
</div>


--- 


# Gráfico gvisSteppedAreaChart()

Veamos los gráficos de escalera:


```r
## Stepped Area Chart
step.capitales <- gvisSteppedAreaChart(data.pob.capitales2, xvar = "Anio", yvar = c("TENERIFE", 
    "GRAN_CANARIA"), options = list(isStacked = TRUE, width = 600, height = 400))
plot(step.capitales)
```


<!-- SteppedAreaChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 20 16:57:43 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataSteppedAreaChartIDfec30c03a23 () {
  var data = new google.visualization.DataTable();
  var datajson =
[
 [
 "2000",
709365,
741161 
],
[
 "2001",
744076,
755489 
],
[
 "2002",
778071,
771333 
],
[
 "2003",
799889,
789908 
],
[
 "2004",
812839,
790360 
],
[
 "2005",
838877,
802247 
],
[
 "2006",
852945,
807049 
],
[
 "2007",
865070,
815379 
],
[
 "2008",
886033,
829597 
],
[
 "2009",
899833,
838397 
],
[
 "2010",
906854,
845676 
],
[
 "2011",
908555,
850391 
],
[
 "2012",
898680,
852225 
] 
];
data.addColumn('string','Anio');
data.addColumn('number','TENERIFE');
data.addColumn('number','GRAN_CANARIA');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartSteppedAreaChartIDfec30c03a23() {
  var data = gvisDataSteppedAreaChartIDfec30c03a23();
  var options = {};
options["allowHtml"] = true;
options["isStacked"] = true;
options["width"] =    600;
options["height"] =    400;

     var chart = new google.visualization.SteppedAreaChart(
       document.getElementById('SteppedAreaChartIDfec30c03a23')
     );
     chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  var chartid = "corechart";

  // Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
  var i, newPackage = true;
  for (i = 0; newPackage && i < pkgs.length; i++) {
    if (pkgs[i] === chartid)
      newPackage = false;
  }
  if (newPackage)
    pkgs.push(chartid);

  // Add the drawChart function to the global list of callbacks
  callbacks.push(drawChartSteppedAreaChartIDfec30c03a23);
})();
function displayChartSteppedAreaChartIDfec30c03a23() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartSteppedAreaChartIDfec30c03a23"></script>
 
<!-- divChart -->
  
<div id="SteppedAreaChartIDfec30c03a23"
  style="width: 600px; height: 400px;">
</div>


--- 

# Gráfico gvisScatterChart()


También se pueden representar gráficos de dos variables:


```r
data.pob.canarias <- data.pob.municipios[data.pob.municipios$Indicador %in% 
    c("Cifras absolutas", "Variación interanual") & data.pob.municipios$CodMunicipio %in% 
    c("ES70"), ]

data.pob.canarias2 <- data.frame(CIFRAS_ABSOLUTAS = data.pob.canarias[data.pob.canarias$Indicador == 
    "Cifras absolutas", "Valor"], VAR_INTERANUAL = data.pob.canarias[data.pob.canarias$Indicador == 
    "Variación interanual", "Valor"])

## Scatter chart
scatter.canarias <- gvisScatterChart(data.pob.canarias2, options = list(legend = "none", 
    pointSize = 2, vAxis = "{title:'Variacion interanual'}", hAxis = "{title:'Poblacion absoluta'}", 
    title = "Comparacion de poblacion absoluta y var. inter.", width = 600, 
    height = 600))
plot(scatter.canarias)
```



<!-- ScatterChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 20 16:57:43 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataScatterChartIDfec61ad38bf () {
  var data = new google.visualization.DataTable();
  var datajson =
[
 [
 2118344,
-8425 
],
[
 2126769,
8250 
],
[
 2118519,
14527 
],
[
 2103992,
28024 
],
[
 2075968,
50017 
],
[
 2025951,
30118 
],
[
 1995833,
27553 
],
[
 1968280,
52740 
],
[
 1915540,
20672 
],
[
 1894868,
51113 
],
[
 1843755,
62389 
],
[
 1781366,
65090 
],
[
 1716276,
null 
] 
];
data.addColumn('number','CIFRAS_ABSOLUTAS');
data.addColumn('number','VAR_INTERANUAL');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartScatterChartIDfec61ad38bf() {
  var data = gvisDataScatterChartIDfec61ad38bf();
  var options = {};
options["allowHtml"] = true;
options["legend"] = "none";
options["pointSize"] =      4;
options["vAxis"] = {title:'Variacion interanual'};
options["hAxis"] = {title:'Poblacion absoluta'};
options["title"] = "Comparacion de poblacion absoluta y var. inter.";
options["width"] =    400;
options["height"] =    400;

     var chart = new google.visualization.ScatterChart(
       document.getElementById('ScatterChartIDfec61ad38bf')
     );
     chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  var chartid = "corechart";

  // Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
  var i, newPackage = true;
  for (i = 0; newPackage && i < pkgs.length; i++) {
    if (pkgs[i] === chartid)
      newPackage = false;
  }
  if (newPackage)
    pkgs.push(chartid);

  // Add the drawChart function to the global list of callbacks
  callbacks.push(drawChartScatterChartIDfec61ad38bf);
})();
function displayChartScatterChartIDfec61ad38bf() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartScatterChartIDfec61ad38bf"></script>
 
<!-- divChart -->
  
<div id="ScatterChartIDfec61ad38bf"
  style="width: 400px; height: 400px;">
</div>


--- 


# Gráfico gvisBubbleChart()

Un gráfico de burbujas:


```r
data.pob.canarias2 <- data.frame(CIFRAS_ABSOLUTAS = data.pob.canarias[data.pob.canarias$Indicador == 
    "Cifras absolutas", "Valor"], VAR_INTERANUAL = data.pob.canarias[data.pob.canarias$Indicador == 
    "Variación interanual", "Valor"], ANIO = data.pob.canarias[data.pob.canarias$Indicador == 
    "Variación interanual", "Anio"])

## Bubble chart
bubble.canarias <- gvisBubbleChart(data.pob.canarias2, idvar = "ANIO", xvar = "CIFRAS_ABSOLUTAS", 
    yvar = "VAR_INTERANUAL", options = list(width = 600, height = 600))

plot(bubble.canarias)
```


<!-- BubbleChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 20 16:57:43 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataBubbleChartIDfec4fa456cc () {
  var data = new google.visualization.DataTable();
  var datajson =
[
 [
 "2012",
2118344,
-8425 
],
[
 "2011",
2126769,
8250 
],
[
 "2010",
2118519,
14527 
],
[
 "2009",
2103992,
28024 
],
[
 "2008",
2075968,
50017 
],
[
 "2007",
2025951,
30118 
],
[
 "2006",
1995833,
27553 
],
[
 "2005",
1968280,
52740 
],
[
 "2004",
1915540,
20672 
],
[
 "2003",
1894868,
51113 
],
[
 "2002",
1843755,
62389 
],
[
 "2001",
1781366,
65090 
],
[
 "2000",
1716276,
null 
] 
];
data.addColumn('string','ANIO');
data.addColumn('number','CIFRAS_ABSOLUTAS');
data.addColumn('number','VAR_INTERANUAL');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartBubbleChartIDfec4fa456cc() {
  var data = gvisDataBubbleChartIDfec4fa456cc();
  var options = {};
options["width"] =    300;
options["height"] =    300;

     var chart = new google.visualization.BubbleChart(
       document.getElementById('BubbleChartIDfec4fa456cc')
     );
     chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  var chartid = "corechart";

  // Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
  var i, newPackage = true;
  for (i = 0; newPackage && i < pkgs.length; i++) {
    if (pkgs[i] === chartid)
      newPackage = false;
  }
  if (newPackage)
    pkgs.push(chartid);

  // Add the drawChart function to the global list of callbacks
  callbacks.push(drawChartBubbleChartIDfec4fa456cc);
})();
function displayChartBubbleChartIDfec4fa456cc() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartBubbleChartIDfec4fa456cc"></script>
 
<!-- divChart -->
  
<div id="BubbleChartIDfec4fa456cc"
  style="width: 300px; height: 300px;">
</div>


--- 


# Gráfico gvisBubbleChart()

Otro ejemplo del gráfico de burbujas:


```r
data.pob.capitales <- data.pob.municipios[data.pob.municipios$Indicador %in% 
    c("Cifras absolutas", "Variación interanual") & data.pob.municipios$CodMunicipio %in% 
    c("ES705", "ES709") & data.pob.municipios$Anio %in% c("2010", "2011", "2012"), 
    ]

data.pob.capitales2 <- data.frame(CIFRAS_ABSOLUTAS = data.pob.capitales[data.pob.capitales$Indicador == 
    "Cifras absolutas", "Valor"], VAR_INTERANUAL = data.pob.capitales[data.pob.capitales$Indicador == 
    "Variación interanual", "Valor"], ANIO = data.pob.capitales[data.pob.capitales$Indicador == 
    "Variación interanual", "Anio"], ISLA = data.pob.capitales[data.pob.capitales$Indicador == 
    "Variación interanual", "Municipio"])

bubble.canarias <- gvisBubbleChart(data.pob.capitales2, idvar = "ISLA", xvar = "CIFRAS_ABSOLUTAS", 
    yvar = "VAR_INTERANUAL", colorvar = "ANIO", sizevar = "VAR_INTERANUAL", 
    options = list(width = 300, height = 300))

plot(bubble.canarias)
```



--- 


# Gráfico gvisPieChart()

Un gráfico de sectores (o de tarta):


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


<!-- PieChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 20 16:57:44 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataPieChartIDfec4e3f24b1 () {
  var data = new google.visualization.DataTable();
  var datajson =
[
 [
 "2012",
2118344 
],
[
 "2011",
2126769 
],
[
 "2010",
2118519 
] 
];
data.addColumn('string','ANIO');
data.addColumn('number','CIFRAS_ABSOLUTAS');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartPieChartIDfec4e3f24b1() {
  var data = gvisDataPieChartIDfec4e3f24b1();
  var options = {};
options["allowHtml"] = true;
options["width"] =    300;
options["height"] =    200;

     var chart = new google.visualization.PieChart(
       document.getElementById('PieChartIDfec4e3f24b1')
     );
     chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  var chartid = "corechart";

  // Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
  var i, newPackage = true;
  for (i = 0; newPackage && i < pkgs.length; i++) {
    if (pkgs[i] === chartid)
      newPackage = false;
  }
  if (newPackage)
    pkgs.push(chartid);

  // Add the drawChart function to the global list of callbacks
  callbacks.push(drawChartPieChartIDfec4e3f24b1);
})();
function displayChartPieChartIDfec4e3f24b1() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartPieChartIDfec4e3f24b1"></script>
 
<!-- divChart -->
  
<div id="PieChartIDfec4e3f24b1"
  style="width: 300px; height: 200px;">
</div>


--- 


# Gráfico gvisGauge()

Y los gráficos de calibración:


```r
## Gauge
gauge.canarias <- gvisGauge(data.pob.canarias2, options = list(fontSize = 9, 
    min = 2e+06, max = 2200000, redFrom = 2e+06, redTo = 2100000, yellowFrom = 2100000, 
    yellowTo = 2150000, greenFrom = 2150000, greenTo = 2200000, width = 800, 
    height = 320))
plot(gauge.canarias)
```


<!-- Gauge generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 20 16:57:44 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataGaugeIDfec1cc86121 () {
  var data = new google.visualization.DataTable();
  var datajson =
[
 [
 "2012",
2118344 
],
[
 "2011",
2126769 
],
[
 "2010",
2118519 
] 
];
data.addColumn('string','ANIO');
data.addColumn('number','CIFRAS_ABSOLUTAS');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartGaugeIDfec1cc86121() {
  var data = gvisDataGaugeIDfec1cc86121();
  var options = {};
options["allowHtml"] = true;
options["fontSize"] =      9;
options["min"] =  2e+06;
options["max"] = 2.2e+06;
options["redFrom"] =  2e+06;
options["redTo"] = 2.1e+06;
options["yellowFrom"] = 2.1e+06;
options["yellowTo"] = 2.15e+06;
options["greenFrom"] = 2.15e+06;
options["greenTo"] = 2.2e+06;
options["width"] =    400;
options["height"] =    160;

     var chart = new google.visualization.Gauge(
       document.getElementById('GaugeIDfec1cc86121')
     );
     chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  var chartid = "gauge";

  // Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
  var i, newPackage = true;
  for (i = 0; newPackage && i < pkgs.length; i++) {
    if (pkgs[i] === chartid)
      newPackage = false;
  }
  if (newPackage)
    pkgs.push(chartid);

  // Add the drawChart function to the global list of callbacks
  callbacks.push(drawChartGaugeIDfec1cc86121);
})();
function displayChartGaugeIDfec1cc86121() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartGaugeIDfec1cc86121"></script>
 
<!-- divChart -->
  
<div id="GaugeIDfec1cc86121"
  style="width: 400px; height: 160px;">
</div>


--- 

# Gráfico gvisOrgChart()

También se pueden representar esquemas organizativos:



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


<!-- OrgChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 20 16:57:44 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataOrgChartIDfec59a7641f () {
  var data = new google.visualization.DataTable();
  var datajson =
[
 [
 "CANARIAS",
null,
"ES70" 
],
[
 "LANZAROTE",
"GRAN CANARIA",
"ES708" 
],
[
 "FUERTEVENTURA",
"GRAN CANARIA",
"ES704" 
],
[
 "GRAN CANARIA",
"CANARIAS",
"ES705" 
],
[
 "TENERIFE",
"CANARIAS",
"ES709" 
],
[
 "LA GOMERA",
"TENERIFE",
"ES706" 
],
[
 "LA PALMA",
"TENERIFE",
"ES707" 
],
[
 "EL HIERRO",
"TENERIFE",
"ES703" 
] 
];
data.addColumn('string','ISLA');
data.addColumn('string','PARENT');
data.addColumn('string','CODE');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartOrgChartIDfec59a7641f() {
  var data = gvisDataOrgChartIDfec59a7641f();
  var options = {};
options["width"] =    200;
options["height"] =     80;
options["size"] = "small";
options["allowCollapse"] = true;

     var chart = new google.visualization.OrgChart(
       document.getElementById('OrgChartIDfec59a7641f')
     );
     chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  var chartid = "orgchart";

  // Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
  var i, newPackage = true;
  for (i = 0; newPackage && i < pkgs.length; i++) {
    if (pkgs[i] === chartid)
      newPackage = false;
  }
  if (newPackage)
    pkgs.push(chartid);

  // Add the drawChart function to the global list of callbacks
  callbacks.push(drawChartOrgChartIDfec59a7641f);
})();
function displayChartOrgChartIDfec59a7641f() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartOrgChartIDfec59a7641f"></script>
 
<!-- divChart -->
  
<div id="OrgChartIDfec59a7641f"
  style="width: 200px; height: 80px;">
</div>



