Programación en R
========================================================
author: Rubén Sánchez Sancho
date: https://datasciencesexy.wordpress.com

![](presentation-figure/DATA-SCIENCE-USING-R-PROGRAMMING.jpg)

[https://datasciencesexy.wordpress.com/](https://datasciencesexy.wordpress.com/)

Introducción
========================================================
type: section

- [Instalación R y R Studio](#/id1)
- [Interfaz R Studio](#/id2)
- [Paquetes](#/id3)
- [Asignación de variables](#/id4)
- [Números, strings y booleanos](#/id5)
- [Operaciones en el workspace](#/id6)
- [Acceso a los archivos de trabajo](#/id7)

Instalación de R y RStudio
========================================================
id: id1
type: sub-section
source: 


Para instalar __R__ en nuestro equipo visitaremos el siguiente enlace:  


<https://www.r-project.org/>

Para instalar el IDE R Studio visitaremos el siguiente enlace:

<https://www.rstudio.com/>


Interfaz de R Studio
========================================================
id: id2
type: sub-section
source: 

Paquetes
========================================================
id: id3
type: sub-section
source: 

Los paquetes son colecciones de funciones __R__, datos y código compilado en un formato definido. El directorio dónde los paquetes están almacenados se llama _library_. __R__ viene con un conjunto de paquetes estandard. Existen otros muchos para la descarga e instalación. Una vez son descargados, tienen que ser cargados en la sesión.


Slide 0
========================================================
title: false


```r
.libPaths() #Localización de la libreria
```


```r
library() # Listar todos los paquetes instalados
```


```r
search() # Buscar los paquetes actualmente cargados
```


Añadiendo  paquetes
========================================================

Podemos expandir el tipo de análisis añadiendo paquetes. Una lista completa de paquetes disponibles se encuentra en:

[https://cran.r-project.org/web/packages/](https://cran.r-project.org/web/packages/)

Sigue estos pasos:

* Descarga e instala el paquete (sólo una vez)


```r
install.packages("MASS")
```


*  Para usar el paquete invoca __library(paquete)__ para cargarlo en la sesión (tienes que hacerlo en cada sesión)


```r
library(MASS)
```

Añadiendo  paquetes en R Studio
========================================================

  
1. Selecciona __Install__ desde la pestaña  __Packages__ 
2. Selecciona un __CRAN Mirror__
3. Elige un paquete (ej: swirl)
4. Carga el paquete invocando __library(paquete)__


Resumen
========================================================

* Hemos aprendido a descargar paquetes
* Cargarlos en la sesión
* Listar los paquetes disponibles
* Soporte de R studio para la gestión de paquetes

Asignación de variables
========================================================
id: id4
type: sub-section
source: 

* Uso del operador de asignación __<-__
* Impresión implícita y explícita
* Uso de la función __assign__

Slide 0
========================================================
title: false

En el _prompt_ de __R__ escribiremos las expresiones. El símbolo __<-__ és el operador de asignación.


```r
x <- 1
print(x)
```

```
[1] 1
```

```r
x
```

```
[1] 1
```

```r
msg <- "hello"
print(msg)
```

```
[1] "hello"
```

Slide 1
========================================================
title: false

Cuando un expresión correcta es introducida en la consola, esta es evaluada y el resultado de la expresión es devuelto.


```r
x <- 5 ## No se imprime en pantalla
x ## por auto-printing se imprime en pantalla
```

```
[1] 5
```

```r
print(x) ## impresión explícita
```

```
[1] 5
```

En [1] se muestra que _x_ es un vector y que su primer elemento es _5_.


Slide 2
========================================================
title: false

Tipícamente con un trabajo interactivo, nosotros no imprimeros los objetos de forma explícita ya que es mucho más cómodo sólo escribir el nombre del objeto y presionar la tecla __Enter__. Sin embargo, cuándo escribamos scripts, funciones o programas muchos más largos, nos veremos con la necesidad de imprimir objetos y es entonce cuándo utilizaremos el modo explícito, ya que el modo ímplicito no trabaja en esas circunstáncias.

Slide 3
========================================================
title: false

Cuándo un vector __R__ es mostrado en la consola obsérvese que el índice del vector es mostrado en []. Por ejemplo:


```r
x <- 10:30
x
```

```
 [1] 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30
```

Los números entre corchetes no forman parte del vector en sí mismo, sino que se trata únicamente de información para la impresión por pantalla.

En __R__ es de vital importáncia entender la diferéncia que existe en el objeto __R__ y la manera en que estos objetos son mostrados en la consola. Normalmente, la información en la consola puede tener información adicional para hacerla más agradable al usuario.

> __Nota:__ El operador __:__ es utilizado para crear secuencias de enteros.



Slide 4
========================================================
title: false

Podemos utilizar la función __assign__ (dentro de un loop for)


```r
assign("x", 2)
x
```

```
[1] 2
```
Números, strings y booleanos
========================================================
id: id5
type: sub-section
source: 

### Contenido

* tipos básicos en R
* uso de la función __class__
* uso de la función __is.X__ (donde X es un tipo de objeto)
* uso de la función __as.X__ (donde X es un tipo de objeto)
* operadores de comparación
