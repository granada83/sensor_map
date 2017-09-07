
## Estructura BD
Aqui se describe una propuesta para la estructura de la base de datos. De esta forma se podrán almacenar los datos en Linaria y se podrán visualizar con la aplicacion que hemos creado. 

![](/img/schema_db.png)

* Tablas para la base de datos y para la visualización 

### `spatial_sensor` 
Tabla de información espacial, con los siguientes atributos

* `id_spatial`: identificador para la localización espacial del objeto que pongamos en el campo 
* `long`, `lat`: coordenas de las balizas
* `elev`: elevación (proporcionada por el GPS, :red_circle: cautela con esto)
* `date_collect`: fecha y hora en la que se tomaron los datos de la localización (proporcionada por el GPS)
* `habitat`: factor con varios niveles (hábitats): `Robledal`, `Claro`, `Piornal`
* `replica`: factor con tres varios niveles (`réplicas`): `R1`, `R2`, `R3`
* `type`: factor referente al tipo de terminal instalado en la localización. Dos niveles: `sensor` y `repetidor` 
* `cota`: factor con varios niveles (gradiente de elevación): `1600`, `1750`, `1900`, `2000` y `2200`. Las cifras son orientativas y se corresponden con: cota baja, estación, treeline, etc. 

### `terminales`
Se trata de otra tabla que contendrá información de los terminales. Tendrá los siguientes atributos: 

* `id`
* `terminal`: identificador del terminal (i.e.: `A136`)
* `id_spatial`: código de identificación de la localización espacial, para relacionar ambas tablas. 

### `sensores`
Cada uno de los terminales tiene varios sensores (uno mide la humedad y temperatura del aire, otro la temperatura del suelo y otro la humedad del suelo). Asi que por cada terminal tendremos varios sensores que estarán asociados a un tipo diferente de nivel dentro del experiemto: bajo roca, bajo hojarasca, en profundidad, etc, etc. 

* `id_sensor`: identificador
* `terminal`: identificador del terminal en el que está el sensor 
* `microhabitat`: factor que indica el microhábitat, con varios niveles: `profundidad`, `superficie`, `bajo roca`, `45 cm sobre el suelo`, etc (:red_circle: tenemos que definirlo)

### `dicc_variables`
Diccionario de variables a medir: 
* `id_variable`: identificador
* `codeVariable`: código de la variable (air_temp, air_humidity, soil_moisture, soil_temp) :red_circle: por determinar. 
* `descVariable: nombre de la variable (algo mas descriptivo)
* `EnvThes`: código del tesauro de la variable (ver LTER, o USLTER)

### `dicc_microhábitats`
* `id_variable`: identificador
* `codeVariable`: código de la variable (air_temp, air_humidity, soil_moisture, soil_temp) :red_circle: por determinar. 
* `descVariable: nombre de la variable (algo mas descriptivo)
* `EnvThes`: código del tesauro de la variable (ver LTER, o USLTER)

### `sensores_valores`
tabla para almacenar los valores que toma el sensor 

* `id`: identificador
* `sensor`: identificador del sensor (viene de la tabla `sensores`)
* `variable: nombre de la variable (viene del diccionario `variables`)
* `dateTime`: fecha y hora en la que el sensor mide la variable
* `value`: valor de la variable 






* `id`
* `terminal`: identificador del terminal (i.e.: `A136`)
* `id_spatial`: código de identificación de la localización espacial, para relacionar ambas tablas. 



