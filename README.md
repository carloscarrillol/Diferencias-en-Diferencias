<br><br><br>



<div align="center">
  <h1>EFECTOS FIJOS</h1>
</div>
 <br><br><br>
<div align="center">
  <p><em> ¡HOLA! 
    
  Soy yo de nuevo, vengo a borrar el README porque planeo empezar de nuevo, no por el modelo de Diferencias en diferencias, sino con un modelo de estimacion con efectos fijos. Esto responde a una llamada de atención de mi parte hacia mí mismo, Tuve una entrevista de trabajo y no supe la respuesta, creo que intentaron humillarme, así que aquí viene mi reivindicación. 
  
  Saludos, nos vemos pronto ;)</em></p>
</div>
<div align="center">
  <p>-C</p>
</div>


<br><br><br><br><br><br>




## Datos Panel

En econometría el término de "datos panel" se refiere a datos que combinan una dimensión temporal con una dimensión transversal. 

Una **serie temporal** es un conjunto de datos que recoge observaciones de un fenómeno en distintos momentos a lo largo del tiempo. Aquí, lo importante es cómo cambia el fenómeno en el tiempo. 

Por otro lado, un **conjunto transversal de datos** reúne observaciones sobre varios fenómenos en un solo momento. En este tipo de datos, el orden de las observaciones no tiene importancia.

Un **conjunto de datos de panel** recoge observaciones sobre varios fenómenos a lo largo de varios períodos de tiempo. La dimensión temporal añade riqueza a estos datos, permitiendo extraer información que no se podría obtener con solo un momento específico.

En un **modelo de datos de sección cruzada** o **transversal**, el objetivo es analizar y comparar diferentes unidades (como personas, empresas o países) en un momento específico. Esto permite identificar patrones o relaciones entre variables sin considerar cambios a lo largo del tiempo.


#### Modelo con conjunto transversal de datos
En el modelo de regresión lineal, la relación entre la variable dependiente $Y$ y las variables explicativas $X$ se representa como:

$$Y = X'\beta + \varepsilon$$

donde:


  * $X\in\mathbb{R}^{p+1}$ es una matriz de $p$ variables explicativas junto con una columna de unos para el término independiente,
  * $\beta \in \mathbb{R}^{p+1}$ es un vector de $p+1$ coeficientes, que incluye tanto los coeficientes de las variables explicativas como el intercepto,
  * $\varepsilon$ es un término de error aleatorio, con la propiedad no correlacionado con las variables explicativas.
  


En este modelo, toda la capacidad explicativa de la variable $Y$ se deriva de las observaciones de las $p$ variables explicativas. De forma escalar, la ecuación se puede expresar como:

$$Y = \beta_{0} + \sum_{i=0}^{p}\beta_{i}x_{i} + \varepsilon$$


En un modelo de sección cruzada, no se incorpora la dimensión temporal, ya que todas las observaciones corresponden a un mismo momento en el tiempo. Esto significa que el modelo refleja únicamente la variación entre diferentes unidades (como individuos o empresas) en ese instante específico, sin capturar su evolución a lo largo del tiempo. La única fuente de variabilidad proviene de las diferencias en las variables explicativas $X$ entre las unidades, no del cambio temporal. Por lo tanto, este tipo de modelo es útil para estudiar relaciones instantáneas entre variables, pero no para analizar cómo estas relaciones cambian o evolucionan con el tiempo.

$$\vdots$$

