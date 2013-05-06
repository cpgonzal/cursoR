Curso de introducción y manejo de R
========================================================

La librería googleVis
-------------------------------------------------------  
 

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
plot(motion.capitales)
# print(motion.capitales,tag='chart')
```



<!-- MotionChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 06 13:58:01 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataMotionChartID17444273df2 () {
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
function drawChartMotionChartID17444273df2() {
  var data = gvisDataMotionChartID17444273df2();
  var options = {};
options["width"] =    350;
options["height"] =    250;

     var chart = new google.visualization.MotionChart(
       document.getElementById('MotionChartID17444273df2')
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
  callbacks.push(drawChartMotionChartID17444273df2);
})();
function displayChartMotionChartID17444273df2() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartMotionChartID17444273df2"></script>
 
<!-- divChart -->
  
<div id="MotionChartID17444273df2"
  style="width: 350px; height: 250px;">
</div>


--- 

## La librería googleVis



```r
# create gagdet
cat(createGoogleGadget(motion.capitales), file = "motionchart.xml")
# se sube el gadget a algún repositorio y se vincula en alguna página
# https://sites.google.com/site/cpgonzal/
```




--- 

## La librería googleVis



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


--- 

## La librería googleVis



```r
data.pob.capitales$Tip <- paste("Poblacion:", data.pob.capitales$Valor)

map.capitales <- gvisMap(data.pob.capitales[data.pob.capitales$Anio == "2012", 
    ], "LatLong", "Tip", options = list(enableScrollWheel = TRUE, mapType = "terrain", 
    useMapTypeControl = TRUE))
# Display chart
plot(map.capitales)
```



<!-- Map generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 06 13:58:01 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataMapID174453bf2d52 () {
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
function drawChartMapID174453bf2d52() {
  var data = gvisDataMapID174453bf2d52();
  var options = {};
options["showTip"] = true;
options["enableScrollWheel"] = true;
options["mapType"] = "terrain";
options["useMapTypeControl"] = true;

     var chart = new google.visualization.Map(
       document.getElementById('MapID174453bf2d52')
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
  callbacks.push(drawChartMapID174453bf2d52);
})();
function displayChartMapID174453bf2d52() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartMapID174453bf2d52"></script>
 
<!-- divChart -->
  
<div id="MapID174453bf2d52"
  style="width: 600px; height: 500px;">
</div>


---   

## La librería googleVis



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
<!-- Mon May 06 13:58:01 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataTableID17448586acc () {
  var data = new google.visualization.DataTable();
  var datajson =
[
 [
 "ES705",
" GRAN CANARIA",
"2012",
2012,
"000000",
"Cifras absolutas",
852225,
"28.1157:-15.4408",
"Poblacion: 852225" 
],
[
 "ES705",
" GRAN CANARIA",
"2011",
2011,
"000000",
"Cifras absolutas",
850391,
"28.1157:-15.4408",
"Poblacion: 850391" 
],
[
 "ES705",
" GRAN CANARIA",
"2010",
2010,
"000000",
"Cifras absolutas",
845676,
"28.1157:-15.4408",
"Poblacion: 845676" 
],
[
 "ES705",
" GRAN CANARIA",
"2009",
2009,
"000000",
"Cifras absolutas",
838397,
"28.1157:-15.4408",
"Poblacion: 838397" 
],
[
 "ES705",
" GRAN CANARIA",
"2008",
2008,
"000000",
"Cifras absolutas",
829597,
"28.1157:-15.4408",
"Poblacion: 829597" 
],
[
 "ES705",
" GRAN CANARIA",
"2007",
2007,
"000000",
"Cifras absolutas",
815379,
"28.1157:-15.4408",
"Poblacion: 815379" 
],
[
 "ES705",
" GRAN CANARIA",
"2006",
2006,
"000000",
"Cifras absolutas",
807049,
"28.1157:-15.4408",
"Poblacion: 807049" 
],
[
 "ES705",
" GRAN CANARIA",
"2005",
2005,
"000000",
"Cifras absolutas",
802247,
"28.1157:-15.4408",
"Poblacion: 802247" 
],
[
 "ES705",
" GRAN CANARIA",
"2004",
2004,
"000000",
"Cifras absolutas",
790360,
"28.1157:-15.4408",
"Poblacion: 790360" 
],
[
 "ES705",
" GRAN CANARIA",
"2003",
2003,
"000000",
"Cifras absolutas",
789908,
"28.1157:-15.4408",
"Poblacion: 789908" 
],
[
 "ES705",
" GRAN CANARIA",
"2002",
2002,
"000000",
"Cifras absolutas",
771333,
"28.1157:-15.4408",
"Poblacion: 771333" 
],
[
 "ES705",
" GRAN CANARIA",
"2001",
2001,
"000000",
"Cifras absolutas",
755489,
"28.1157:-15.4408",
"Poblacion: 755489" 
],
[
 "ES705",
" GRAN CANARIA",
"2000",
2000,
"000000",
"Cifras absolutas",
741161,
"28.1157:-15.4408",
"Poblacion: 741161" 
],
[
 "ES709",
" TENERIFE",
"2012",
2012,
"000000",
"Cifras absolutas",
898680,
"28.4687:-16.252",
"Poblacion: 898680" 
],
[
 "ES709",
" TENERIFE",
"2011",
2011,
"000000",
"Cifras absolutas",
908555,
"28.4687:-16.252",
"Poblacion: 908555" 
],
[
 "ES709",
" TENERIFE",
"2010",
2010,
"000000",
"Cifras absolutas",
906854,
"28.4687:-16.252",
"Poblacion: 906854" 
],
[
 "ES709",
" TENERIFE",
"2009",
2009,
"000000",
"Cifras absolutas",
899833,
"28.4687:-16.252",
"Poblacion: 899833" 
],
[
 "ES709",
" TENERIFE",
"2008",
2008,
"000000",
"Cifras absolutas",
886033,
"28.4687:-16.252",
"Poblacion: 886033" 
],
[
 "ES709",
" TENERIFE",
"2007",
2007,
"000000",
"Cifras absolutas",
865070,
"28.4687:-16.252",
"Poblacion: 865070" 
],
[
 "ES709",
" TENERIFE",
"2006",
2006,
"000000",
"Cifras absolutas",
852945,
"28.4687:-16.252",
"Poblacion: 852945" 
],
[
 "ES709",
" TENERIFE",
"2005",
2005,
"000000",
"Cifras absolutas",
838877,
"28.4687:-16.252",
"Poblacion: 838877" 
],
[
 "ES709",
" TENERIFE",
"2004",
2004,
"000000",
"Cifras absolutas",
812839,
"28.4687:-16.252",
"Poblacion: 812839" 
],
[
 "ES709",
" TENERIFE",
"2003",
2003,
"000000",
"Cifras absolutas",
799889,
"28.4687:-16.252",
"Poblacion: 799889" 
],
[
 "ES709",
" TENERIFE",
"2002",
2002,
"000000",
"Cifras absolutas",
778071,
"28.4687:-16.252",
"Poblacion: 778071" 
],
[
 "ES709",
" TENERIFE",
"2001",
2001,
"000000",
"Cifras absolutas",
744076,
"28.4687:-16.252",
"Poblacion: 744076" 
],
[
 "ES709",
" TENERIFE",
"2000",
2000,
"000000",
"Cifras absolutas",
709365,
"28.4687:-16.252",
"Poblacion: 709365" 
] 
];
data.addColumn('string','CodMunicipio');
data.addColumn('string','Municipio');
data.addColumn('string','CodAnio');
data.addColumn('number','Anio');
data.addColumn('string','CodIndicador');
data.addColumn('string','Indicador');
data.addColumn('number','Valor');
data.addColumn('string','LatLong');
data.addColumn('string','Tip');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartTableID17448586acc() {
  var data = gvisDataTableID17448586acc();
  var options = {};
options["allowHtml"] = true;
options["width"] =    800;
options["height"] =    470;
options["page"] = "enable";

     var chart = new google.visualization.Table(
       document.getElementById('TableID17448586acc')
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
  callbacks.push(drawChartTableID17448586acc);
})();
function displayChartTableID17448586acc() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartTableID17448586acc"></script>
 
<!-- divChart -->
  
<div id="TableID17448586acc"
  style="width: 800px; height: 470px;">
</div>


---   

## La librería googleVis



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
<!-- Mon May 06 13:58:01 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataAnnotatedTimeLineID17446a8d428e () {
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
function drawChartAnnotatedTimeLineID17446a8d428e() {
  var data = gvisDataAnnotatedTimeLineID17446a8d428e();
  var options = {};
options["width"] =    600;
options["height"] =    550;
options["legendPosition"] = "newRow";
options["displayExactValues"] = "TRUE";

     var chart = new google.visualization.AnnotatedTimeLine(
       document.getElementById('AnnotatedTimeLineID17446a8d428e')
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
  callbacks.push(drawChartAnnotatedTimeLineID17446a8d428e);
})();
function displayChartAnnotatedTimeLineID17446a8d428e() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartAnnotatedTimeLineID17446a8d428e"></script>
 
<!-- divChart -->
  
<div id="AnnotatedTimeLineID17446a8d428e"
  style="width: 600px; height: 550px;">
</div>


--- 


## La librería googleVis



```r
## Bar chart
bar.capitales <- gvisBarChart(data.pob.capitales2, xvar = "Anio", yvar = c("TENERIFE", 
    "GRAN_CANARIA"), options = list(legend = "right", width = 600, height = 400))

plot(bar.capitales)
```


<!-- BarChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 06 13:58:01 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataBarChartID17441a8611a () {
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
function drawChartBarChartID17441a8611a() {
  var data = gvisDataBarChartID17441a8611a();
  var options = {};
options["allowHtml"] = true;
options["legend"] = "right";
options["width"] =    600;
options["height"] =    400;

     var chart = new google.visualization.BarChart(
       document.getElementById('BarChartID17441a8611a')
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
  callbacks.push(drawChartBarChartID17441a8611a);
})();
function displayChartBarChartID17441a8611a() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartBarChartID17441a8611a"></script>
 
<!-- divChart -->
  
<div id="BarChartID17441a8611a"
  style="width: 600px; height: 400px;">
</div>


--- 

## La librería googleVis



```r
## Column chart
col.capitales <- gvisColumnChart(data.pob.capitales2, xvar = "Anio", yvar = c("TENERIFE", 
    "GRAN_CANARIA"), options = list(legend = "right", width = 600, height = 400))
plot(col.capitales)

```


<!-- ColumnChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 06 13:58:02 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataColumnChartID174437895cff () {
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
function drawChartColumnChartID174437895cff() {
  var data = gvisDataColumnChartID174437895cff();
  var options = {};
options["allowHtml"] = true;
options["legend"] = "right";
options["width"] =    600;
options["height"] =    400;

     var chart = new google.visualization.ColumnChart(
       document.getElementById('ColumnChartID174437895cff')
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
  callbacks.push(drawChartColumnChartID174437895cff);
})();
function displayChartColumnChartID174437895cff() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartColumnChartID174437895cff"></script>
 
<!-- divChart -->
  
<div id="ColumnChartID174437895cff"
  style="width: 600px; height: 400px;">
</div>


--- 

## La librería googleVis



```r
## Area chart
area.capitales <- gvisAreaChart(data.pob.capitales2, xvar = "Anio", yvar = c("TENERIFE", 
    "GRAN_CANARIA"), options = list(legend = "right", width = 600, height = 400))
plot(area.capitales)

```


<!-- AreaChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 06 13:58:02 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataAreaChartID174468ba1777 () {
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
function drawChartAreaChartID174468ba1777() {
  var data = gvisDataAreaChartID174468ba1777();
  var options = {};
options["allowHtml"] = true;
options["legend"] = "right";
options["width"] =    600;
options["height"] =    400;

     var chart = new google.visualization.AreaChart(
       document.getElementById('AreaChartID174468ba1777')
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
  callbacks.push(drawChartAreaChartID174468ba1777);
})();
function displayChartAreaChartID174468ba1777() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartAreaChartID174468ba1777"></script>
 
<!-- divChart -->
  
<div id="AreaChartID174468ba1777"
  style="width: 600px; height: 400px;">
</div>


--- 


## La librería googleVis



```r
## Stepped Area Chart
step.capitales <- gvisSteppedAreaChart(data.pob.capitales2, xvar = "Anio", yvar = c("TENERIFE", 
    "GRAN_CANARIA"), options = list(isStacked = TRUE, width = 600, height = 400))
plot(step.capitales)
```


<!-- SteppedAreaChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 06 13:58:02 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataSteppedAreaChartID1744287922be () {
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
function drawChartSteppedAreaChartID1744287922be() {
  var data = gvisDataSteppedAreaChartID1744287922be();
  var options = {};
options["allowHtml"] = true;
options["isStacked"] = true;
options["width"] =    600;
options["height"] =    400;

     var chart = new google.visualization.SteppedAreaChart(
       document.getElementById('SteppedAreaChartID1744287922be')
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
  callbacks.push(drawChartSteppedAreaChartID1744287922be);
})();
function displayChartSteppedAreaChartID1744287922be() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartSteppedAreaChartID1744287922be"></script>
 
<!-- divChart -->
  
<div id="SteppedAreaChartID1744287922be"
  style="width: 600px; height: 400px;">
</div>


--- 

## La librería googleVis



```r
data.pob.canarias <- data.pob.municipios[data.pob.municipios$Indicador %in% 
    c("Cifras absolutas", "Variación interanual") & data.pob.municipios$CodMunicipio %in% 
    c("ES70"), ]

data.pob.canarias2 <- data.frame(CIFRAS_ABSOLUTAS = data.pob.canarias[data.pob.canarias$Indicador == 
    "Cifras absolutas", "Valor"], VAR_INTERANUAL = data.pob.canarias[data.pob.canarias$Indicador == 
    "Variación interanual", "Valor"])

## Scatter chart
scatter.canarias <- gvisScatterChart(data.pob.canarias2, options = list(legend = "none", 
    lineWidth = 2, pointSize = 0, vAxis = "{title:'Variacion interanual'}", 
    hAxis = "{title:'Poblacion absoluta'}", title = "Comparacion de poblacion absoluta y var. inter.", 
    width = 600, height = 600))
plot(scatter.canarias)
```



--- 

## La librería googleVis


<!-- ScatterChart generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 06 13:58:02 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataScatterChartID17445008463 () {
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
function drawChartScatterChartID17445008463() {
  var data = gvisDataScatterChartID17445008463();
  var options = {};
options["allowHtml"] = true;
options["legend"] = "none";
options["lineWidth"] =      2;
options["pointSize"] =      0;
options["vAxis"] = {title:'Variacion interanual'};
options["hAxis"] = {title:'Poblacion absoluta'};
options["title"] = "Comparacion de poblacion absoluta y var. inter.";
options["width"] =    400;
options["height"] =    400;

     var chart = new google.visualization.ScatterChart(
       document.getElementById('ScatterChartID17445008463')
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
  callbacks.push(drawChartScatterChartID17445008463);
})();
function displayChartScatterChartID17445008463() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartScatterChartID17445008463"></script>
 
<!-- divChart -->
  
<div id="ScatterChartID17445008463"
  style="width: 400px; height: 400px;">
</div>


--- 


## La librería googleVis



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
<!-- Mon May 06 13:58:02 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataBubbleChartID1744d2a1ae1 () {
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
function drawChartBubbleChartID1744d2a1ae1() {
  var data = gvisDataBubbleChartID1744d2a1ae1();
  var options = {};
options["width"] =    300;
options["height"] =    300;

     var chart = new google.visualization.BubbleChart(
       document.getElementById('BubbleChartID1744d2a1ae1')
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
  callbacks.push(drawChartBubbleChartID1744d2a1ae1);
})();
function displayChartBubbleChartID1744d2a1ae1() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartBubbleChartID1744d2a1ae1"></script>
 
<!-- divChart -->
  
<div id="BubbleChartID1744d2a1ae1"
  style="width: 300px; height: 300px;">
</div>


--- 


## La librería googleVis



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


## La librería googleVis



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
<!-- Mon May 06 13:58:02 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataPieChartID174479cd6943 () {
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
function drawChartPieChartID174479cd6943() {
  var data = gvisDataPieChartID174479cd6943();
  var options = {};
options["allowHtml"] = true;
options["width"] =    300;
options["height"] =    200;

     var chart = new google.visualization.PieChart(
       document.getElementById('PieChartID174479cd6943')
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
  callbacks.push(drawChartPieChartID174479cd6943);
})();
function displayChartPieChartID174479cd6943() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartPieChartID174479cd6943"></script>
 
<!-- divChart -->
  
<div id="PieChartID174479cd6943"
  style="width: 300px; height: 200px;">
</div>


--- 


## La librería googleVis



```r
## Gauge
gauge.canarias <- gvisGauge(data.pob.canarias2, options = list(fontSize = 9, 
    min = 2e+06, max = 2200000, redFrom = 2e+06, redTo = 2100000, yellowFrom = 2100000, 
    yellowTo = 2150000, greenFrom = 2150000, greenTo = 2200000, width = 800, 
    height = 320))
plot(gauge.canarias)
```


<!-- Gauge generated in R 3.0.0 by googleVis 0.4.2 package -->
<!-- Mon May 06 13:58:03 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataGaugeID1744e07609f () {
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
function drawChartGaugeID1744e07609f() {
  var data = gvisDataGaugeID1744e07609f();
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
       document.getElementById('GaugeID1744e07609f')
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
  callbacks.push(drawChartGaugeID1744e07609f);
})();
function displayChartGaugeID1744e07609f() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartGaugeID1744e07609f"></script>
 
<!-- divChart -->
  
<div id="GaugeID1744e07609f"
  style="width: 400px; height: 160px;">
</div>


--- 

## La librería googleVis



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
<!-- Mon May 06 13:58:03 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataOrgChartID174426e61ea9 () {
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
function drawChartOrgChartID174426e61ea9() {
  var data = gvisDataOrgChartID174426e61ea9();
  var options = {};
options["width"] =    200;
options["height"] =     80;
options["size"] = "small";
options["allowCollapse"] = true;

     var chart = new google.visualization.OrgChart(
       document.getElementById('OrgChartID174426e61ea9')
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
  callbacks.push(drawChartOrgChartID174426e61ea9);
})();
function displayChartOrgChartID174426e61ea9() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartOrgChartID174426e61ea9"></script>
 
<!-- divChart -->
  
<div id="OrgChartID174426e61ea9"
  style="width: 200px; height: 80px;">
</div>



