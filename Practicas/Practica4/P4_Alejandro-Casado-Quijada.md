#Práctica 4. Comprobar el rendimiento de servidores web

El objetivo de esta práctica es medir el rendimiento de los servidores que se han montando en las prácticas anteriores.

Para ello se van a utilizar dos herramientas:

* Apache Benchmark
* Siege


Vamos a ejecutar cada herramienta un total de 10 veces para cada uno de los siguientes escenarios:

* Servidor final
* Balanceador con nginx
* Balanceador con haproxy

Para mas información sobre los resultados consultar [aqui](Resultados/ "Resultados")

##Resultados Apache Benchmark

### Media de los resultados

![Resultados ab](Imagenes/ResultadosAB/ab-media-Time-taken.png "Media time taken")
![Resultados ab](Imagenes/ResultadosAB/ab-media-failed.png "Media failed request")
![Resultados ab](Imagenes/ResultadosAB/ab-media-request.png "Media request per second")

### Desviación de los resultados

![Resultados ab](Imagenes/ResultadosAB/ab-desviacion-Time-taken.png "Desviación time taken")
![Resultados ab](Imagenes/ResultadosAB/ab-desviacion-failed.png "Desviación failed request")
![Resultados ab](Imagenes/ResultadosAB/ab-desviacion-request.png "Desviación request per second")

##Resultados Siege

### Media de los resultados

![Resultados haproxy](Imagenes/ResultadosHaproxy/haproxy-media-elapsed-time.png
 "Media elapsed time")
![Resultados haproxy](Imagenes/ResultadosHaproxy/haproxy-media-longest-transaction.png
 "Media longest transaction")
![Resultados haproxy](Imagenes/ResultadosHaproxy/haproxy-media-transaction-rate.png
 "Media transaction rate")

### Desviación de los resultados

![Resultados haproxy](Imagenes/ResultadosHaproxy/haproxy-desviacion-elapsed-time.png
 "Desviación elapsed time")
![Resultados haproxy](Imagenes/ResultadosHaproxy/haproxy-desviacion-longest-transaction.png "Desviación longest transaction")
![Resultados haproxy](Imagenes/ResultadosHaproxy/haproxy-desviacion-transaction-rate.png "Desviación transaction rate")
