
## Estructura BD

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





