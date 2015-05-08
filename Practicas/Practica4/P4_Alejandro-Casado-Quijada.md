#Práctica 4. Comprobar el rendimiento de servidores web

El objetivo de esta práctica es medir el rendimiento de los servidores que se han montando en las prácticas anteriores.

Para ello se van a utilizar dos herramientas:

* Apache Benchmark
* Siege


Vamos a ejecutar cada herramienta un total de 10 veces para cada uno de los siguientes escenarios:

* Servidor final
* Balanceador con nginx
* Balanceador con haproxy

Para mas información sobre los resultados consultar el siguiente documento

##Resultados Apache Benchmark

### Media de los resultados

* Time taken for tests
![Resultados ab](Imagenes/ResultadosAB/ab-media-Time-taken.png "Media time taken")

* Failed requests
![Resultados ab](Imagenes/ResultadosAB/ab-media-failed.png "Media failed request")

* Requests per second
![Resultados ab](Imagenes/ResultadosAB/ab-media-request.png "Media request per second")

### Desviación de los resultados

* Time taken for tests

![Resultados ab](Imagenes/ResultadosAB/ab-desviacion-Time-taken.png "Desviación time taken")

* Failed requests

![Resultados ab](Imagenes/ResultadosAB/ab-desviacion-failed.png "Desviación failed request")

* Requests per second

![Resultados ab](Imagenes/ResultadosAB/ab-desviacion-request.png "Desviación request per second")

##Resultados Siege

### Media de los resultados

* Elapsed time
![Resultados haproxy](Imagenes/ResultadosHaproxy/haproxy-media-elapsed-time.png
 "Media elapsed time")

* Transaction rate

![Resultados haproxy](Imagenes/ResultadosHaproxy/haproxy-media-longest-transaction.png
 "Media longest transaction")

* Longest transaction

![Resultados haproxy](Imagenes/ResultadosHaproxy/haproxy-media-transaction-rate.png
 "Media transaction rate")

### Desviación de los resultados

* Elapsed time

![Resultados haproxy](Imagenes/ResultadosHaproxy/haproxy-desviacion-elapsed-time.png
 "Desviación elapsed time")
 
* Transaction rate

![Resultados haproxy](Imagenes/ResultadosHaproxy/haproxy-desviacion-longest-transaction.png "Desviación longest transaction")

* Longest transaction

![Resultados haproxy](Imagenes/ResultadosHaproxy/haproxy-desviacion-transaction-rate.png "Desviación transaction rate")
