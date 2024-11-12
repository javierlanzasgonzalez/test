# Práctica 2: Configuración de sistemas de ficheros. "Benchmarking":

* Parte A: AWS Academy Cloud Foundations

    [Pincha aquí para ir a la Parte A](ParteA/README.md)

*  Parte B: Oracle Cloud.

    [Pincha aquí para ir a la Parte B](/ParteB/README.md)

-------

## Diferencia entre Acceso Secuencial y Acceso Aleatorio

Cuando realizamos pruebas de rendimiento en almacenamiento con herramientas como FIO, es importante entender la diferencia entre dos tipos principales de patrones de acceso: **secuencial** y **aleatorio**. Estos patrones afectan el rendimiento de lectura y escritura y determinan qué tipo de carga el sistema de almacenamiento puede manejar eficientemente. A continuación se explica cada tipo, acompañado de una descripción de los esquemas que ilustran cómo funcionan en un disco duro.

### Acceso Secuencial

El acceso secuencial (o “sequential”) implica que los datos se leen o escriben en bloques contiguos del almacenamiento, uno tras otro en orden. Este tipo de acceso es ideal para operaciones de gran tamaño, como la transferencia de archivos grandes o la carga de bases de datos completas, ya que permite que el cabezal de lectura/escritura del disco se mueva de manera continua sin saltos.

* Los datos se escriben o leen de manera continua, sector tras sector, en una sola dirección.
* El cabezal del disco realiza un movimiento fluido y continuo, minimizando el tiempo de búsqueda.

### Acceso Aleatorio

El acceso aleatorio (o “random”) implica que los datos se leen o escriben en bloques que están dispersos en distintas ubicaciones del almacenamiento. En lugar de acceder a los datos en un orden lineal, el cabezal del disco salta de un sector a otro en ubicaciones no contiguas. Este patrón es común en aplicaciones que requieren acceso a múltiples archivos pequeños o en sistemas que realizan muchas operaciones de entrada/salida simultáneas, como bases de datos de alta concurrencia.

* Los datos se escriben o leen en sectores no contiguos, lo que obliga al cabezal a moverse constantemente de un lugar a otro.
* Este tipo de acceso es más lento en discos mecánicos, ya que el cabezal necesita reposicionarse frecuentemente, aumentando el tiempo de búsqueda.

### Esquema del funcionamiento del Acceso Secuencial y Aleatorio (Random)

![HDD](/ParteB/Windows/img/acceso.png)

### Comparación de Rendimiento

En discos mecánicos, el acceso secuencial suele ser mucho más rápido que el acceso aleatorio, ya que el cabezal del disco realiza movimientos continuos y no tiene que reposicionarse. Sin embargo, en almacenamiento basado en flash (como SSDs), la diferencia entre acceso secuencial y aleatorio es menor, ya que no hay partes móviles. Aun así, el acceso secuencial puede ser más eficiente debido a la forma en que los datos se organizan y manejan a nivel de controladora.

-------