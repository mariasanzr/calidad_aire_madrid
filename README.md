## Calidad del aire Madrid

![Madrid](/data/madrid.jpg)

### Introducción

Para este reto partía de datos acerca de las sustancias en el aire de Madrid y que por tanto determinan su calidad. 

El CSV descargado del Portal de datos abiertos del Ayuntamiento de Madrid contiene datos de las 24 estaciones de medición distribuidas por la ciudad, así como de las diversas sustancias que contiene el aire. Estos datos están clasificados de tal manera que hay un dato por cada hora de cada día del 2018. 

### Transformación de los datos

Me he centrado en las mediciones de NO2 y para ello, he realizado la siguiente transformación de los datos: 

- 'PROVINCIA': Todas las celdas de esta columna contienen el número '28'ya que es el código de provincia de la Comunidad de Madrid. 
- 'MUNICIPIO': Todas las celdas de esta columna contienen el número '79' ya que es el código de provincia de Madrid.
- 'MAGNITUD': Todas las celdas de esta columna, después de la transformación, contienen el número '8' ya que es el correspondiente al NO2
- 'TECNICA_MUESTREO': Todas las celdas de esta columna contienen el número '8' ya que se utilizó la misma técnica para la obtención de los datos. 
- 'ESTACION': Esta columna contiene 24 valores únicos, 9 dígitos por cada casilla que corresponden a un código de una estación de muestreo.
- 'NOMBRE': Esta columna también contiene tan solo 24 valores únicos que se corresponden con el número de estaciones, y son nombres de calles/zonas en las que están situadas.
- 'FECHA_HORA': Esta columna contiene la fecha y hora en formato 'datetime'
- 'DATOS': contiene dígitos con la concentración de NO2 en el aire. 

### Predicción

Como los datos tienen mediciones horarias a lo largo de todo 2018, es probable que la serie temporal exhiba cierto grado de estacionalidad y autocorrelación, lo cual hace que el modelo ARIMA sea una opción razonable y por lo que he querido aplicarlo en este caso. 

### Conclusiones

El NO2 es un contaminante atmosférico, de origen principalmente antropogénico, cuyas fuentes fundamentales son el tráfico rodado, así como las emisiones de determinadas industrias y grandes instalaciones de combustión.

Sabiendo eso, el gráfico elaborado para la interpretación de los datos cobra más sentido. Empezando por que las zonas con menos concentración de NO2 son El Pardo y la Casa de Campo, zonas verdes en las que el tráfico está muy limitado. Por otro lado, se ve un aumento de la presencia de esta sustancia en el aire entre los meses de octubre y febrero, meses en los que llueve mucho y hace frío, por lo que es más cómodo transportarse en coche. Además de que en los meses más soleados mucha gente toma de alternativa caminar o ir en bicicleta de un lado a otro, también mucha gente se va de vacaciones, por lo que tiene sentido también esta bajada. 

Tal y como comentaba anteriormente, creo que sería interesante implementar datos de tráfico o condiciones meteorológicas en la visualización para analizar numéricamente y no solo como suposición su relación con los niveles de NO2.
