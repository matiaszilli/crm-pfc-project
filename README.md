<h1 align="center">Optimización de un código para la identificación de parámetros en modelos capacitivos-resistivos (CRM) de reservorios de petróleo</h1>

<h3 align="center">Proyecto Final de Carrera</h3>


* [Resumen](#overview)
* [Resultados](#achievements)
* [Full paper](#fullpaper)

___



<a name="overview"></a>
## Resumen

Actualmente en el campo de extracción de petróleo existe una tendencia
al uso de algoritmos computacionales para simular situaciones particulares y
estimar ciertos parámetros. Hoy día los simuladores basados en el método
CRM(Capacitive Resistive Method), utilizados en proyectos de recuperación
secundaria de petróleo, resuelven el problema de identificación de parámetros
sin tener en cuenta las relaciones existentes entre las diferentes etapas
(configuraciones de inyectores-productores). Es decir, si la configuración de
productores alrededor de un inyector cambia de una etapa a otra, los
parámetros de la nueva etapa se asumen completamente diferentes a los de la
etapa anterior. Sin embargo, en la práctica, las conductancias hidráulicas de
una nueva etapa serán prácticamente las mismas que las de la etapa anterior,
por lo tanto existen ciertas relaciones que se preservan. Estas últimas pueden
ser aprovechadas de manera tal de reducir la cantidad de parámetros a
identificar, lo cual da ciertas ventajas.
El presente trabajo propone implementar modificaciones a la librería
IDENT desarrollada por el [CIMEC](https://cimec.org.ar/), que implementa el método CRM, de
forma que este contemple las relaciones entre etapas y a la vez, que mejore la
los tiempos de ejecución.

<a name="achievements"></a>
## Resultados

Se desarrolló un algoritmo que permite identificar los
cambios en las conectividades entre dos etapas. Para esto se analizaron la
estructura y formato de los datos de entrada, luego se diseñaron las estructuras
de datos para contener la información a procesar, y finalmente con todos los
datos ya almacenados en las estructuras correspondientes, se implementó un
algoritmo que permite extraer las relaciones entre los distintos coeficientes de
flujo de un dado reservorio. Este algoritmo fue validado con casos de distintas
dimensiones y complejidades para evaluar su precisión y robustez.

Con el objetivo de lograr un incremento en el desempeño de la librería
IDENT se implementaron distintas mejoras a la misma sin utilizar
paralelización debido a la existencia de dependencias y bucles con un número
indeterminado de iteraciones. Las mejoras implementadas en el algoritmo
permitieron conseguir una notable mejora en el rendimiento de hasta 11X, es
decir 11 veces más rápido. Además se observó que a medida que el problema
se vuelve grande también aumenta el rendimiento obtenido con esta
optimización lo cual es de gran importancia ya que permite que la optimización
beneficie más a los casos que demandan gran cantidad de tiempo.

<a name="fullpaper"></a>
## Full Paper

Link al documento [aqui](./CRM-Informe.pdf).

