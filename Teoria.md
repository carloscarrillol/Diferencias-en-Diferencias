<br><br><br>



<div align="center">
  <h1>Diferencias en diferencias</h1>
</div>

<br><br><br><br><br><br>



### 1. Introducción

Al igual que en las entradas anteriores, a lo largo de esta entrada tomaré como referencia uno de los artículos más utilizados (en el campo de la economía) para (tratar de) explicar como funciona el método de
estimación por diferencias en diferencias (DID). En general, la mayor parte de esta entrada serán fragmentos traducidos (casi literalmente) del Capítulo V de *Mostly Harmless Econometrics: An Empiricist's Companion* de Jörn-Steffen 
Pischke y Joshua D. Angrist. Posteriormente, quizá en otra entreada me gustaría resumir el paper de Nancy Qian (2008) *"Missing Women and the Price of Tea in China: The Effect of Sex-Specific Earnings on Sex Imbalance"* o
*"Does Compulsory Schooling Affect Schooling and Earnings?"* de Joshua D. Angrist y Alan B. Krueger (1991), para comprender de mejor manera como se utilizan estos métodos en el mundo real y de manera práctica.

En vez de pasar directamente a la estrategia de identificación de diferencias en diferencias, revisaremos las estrategias de estimación por efectos fijos (FE). Ambas estrategias se basan en comparaciones de niveles, 
mientras que requieren que el comportamiento de tendencia contrafactual de los grupos de tratamiento y control sea el mismo (*parallel trends*). También analizamos la idea de controlar por variables dependientes 
rezagadas, otra estrategia que aprovecha el tiempo.

### 2.1 Efectos Fijos por Individuo

Una de las preguntas más antiguas en la economía del trabajo es la conexión entre las afiliaciones sindicales y los salarios. ¿Los salarios de los trabajadores que negocian colectivamente son más altos 
debido a que se negocian colectivamente? (a lo largo de toda la entrada seré redundante con el objetivo de ser más claro, espero no conseguir el efecto contrario), desde luego este incremento se debe a otros 
factores. Es posible que aquellos trabajadores con salarios más altos sean más experimentados o más habiles en su trabajo, sin embargo, también es posible que esas características sean deseables para una organización
sindical. Para establecer esta pregunta, sea $Y_{it}$ el logaritmo de los salarios del trabajador $i$ al tiempo $t$, y sea $D_{it}$ el estado de su afiliación sindical de mismo trabajador en ese mismo momento. 
El $Y_{it}$ observado puede ser $Y_{0it}$ o $Y_{1it}$ dependiendo del estado del trabajador. Supongamos, además, que

<br>

$$E(Y_{0it}| A_{i}, X_{it}, t, D_{it}) = E(Y_{0it}| A_{i}, X_{it}, t) \tag{2.1}$$

<br>

la ecuación (2.1) sugiere que la variable de tratamiento $D_{it}$ no tiene un impacto sistemático o diferencial en el valor esperado de $Y_{0it}$ después de controlar por las habilidades no observadas del trabajador $i$ $A_{i}$, otras variables obseradas $X_{it}$ como edad y escolaridad,  y $t$.

La clave para la estimación por efectos fijos es el supuesto de que $A_{i}$ aparece sin el subíndice temporal en un modelo lineal para $E(Y_{0it}|A_{i},X_{it},t)$:

<br>

$$E(Y_{0it}| A_{i}, X_{it}, t) = \alpha + \lambda_{t} + A_{i}'\gamma + X_{it}\delta \tag{2.2}$$

<br>

Finalmente, suponemos que el efecto causal de la afiliación sindical es aditiva y constante:

<br>

$$E(Y_{1it}| A_{i}, X_{it}, t) = E(Y_{0it}| A_{i}, X_{it}, t) + \rho$$

<br>

Esto implica que 

<br>

$$E(Y_{it}| A_{i}, X_{it}, t, D_{it}) = \alpha + \lambda_{t} + \rho D_{it} + A_{i}'\gamma + X_{it}\delta \tag{2.3}$$

<br>

donde $\rho$ es el efecto causal de interés.

La ecuación (2.3) implica que

<br>

$$Y_{it} = \alpha_{i} + \lambda_{t} + \rho D_{it} + X_{it}\delta + \varepsilon_{it} \tag{2.4}$$

<br>

donde, 

<br>

$$\alpha_{i} \equiv \alpha + A_{i}'\gamma$$

<br>

Esto es un modelo de *efectos fijos*. Dados los datos de panel (i.e., datos repetidos por individuos) el efecto causal del estado sindical del individuo sobre los salarios pueden ser estimados tratando $\alpha_{i}$, el efecto fijo, como un parámetro a estimar. El *efecto año* $\lambda_{t}$ es otro parametro a estimar. Los efectos individuales no observados son coeficientes sobre variables *dummies* para cada individuo, mientras que los efectos anuales son coeficientes sobre variables *dummies* de tiempo.

Podría parecer que hay muchísimos parámetros que estimar en el modelo de efectos fijos. Por ejemplo, el *Panel Survey of Income Dynamics* un conjunto de datos de panel ampliamente utilizado, incluye alrededor de 5'000 hombres en edad de trabajar observados durante unos 20 años, por lo que hay aproximadamente 5'000 efectos fijos. En la practica, sin embargo, esto no importa. Tratar los efectos individuales como parámetros a estimar es algebraicamente lo mismo que estimar en desviaciones de las medias. En otras palabras, primero calculamos los promedios individuales:

<div>

$$\overline{Y}_{i} = \alpha_i + \overline{\lambda} + \rho\overline{D}_i + \overline{X}_i\delta + \overline{\varepsilon}_i$$

<div>

restando la ecuación anterior de la ecuación (2.4) tenemos,














.
.
.

