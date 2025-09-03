<h1 align="center">
Lab 1: Tipos de Datos Avanzados y Archivos en Python (RA 1, RA 3 y RA 4) <br />
 </h1>
 <p align="center">
Alexander López-Parrado, PhD. <br />
Programación, II-2025 <br />
GDSPROC <br />
Uniquindío <br />
</p>

Con esta práctica de laboratorio se iniciará el desarrollo del código fuente en Python del proyecto del espacio académico. En este caso, y de acuerdo a la arquitectura mostrada en la siguiente figura, se construirá el código del lado del servidor para la gestión de usuarios y citas para el sistema de teleconsulta médica.

<p align="center">
<img  src="Programación-II-2025.png" width="800" >
</p>

En ese sentido, la práctica de laboratorio tiene como propósito la creación de funciones que permitan realizar la gestión de los usuarios (pacientes y médicos) y de las consultas mediante el uso de tipos de datos avanzados como: diccionarios, connjuntos y tuplas; también se usarán archivos de texto y las demás estructuras de programación y tipos de datos estudiados hasta el momento.

## Requerimientos básicos

El sistema de teleconsulta médica debe contar con la capacidad de gestionar pacientes, médicos y citas. Para esto, y en el caso de los pacientes y médicos, el sistema debe contar con las siguientes características minimas:

* Registro de usuarios con la siguiente información:
 - Número de cédula.
 - Nombre y apellidos.
 - Contraseña
 - Rol (paciente o médico)
* Inicio de sesión en el sistema con almacenamiento de dirección IP (*Internet Protocol*)  [[1]](#1)

Esta IP será utilizada para el establecimiento de la videollamada de la teleconsulta, cuya implementación se realizará en la segunda entrega del proyecto. En todo caso, desde ya se debe considerar el almacenamiento de la IP  [[1]](#1).

De otro lado, para el caso de las consultas médicas, el sistema debe contar con las siguientes características mínimas:

* Creación de consultas con la siguiente información:
 - Número de cédula del paciente.
 - Número de cédula del médico.
 - Fecha y hora de la consulta.
* Registro de la prescripción médica al finalizar la consulta.

Considerando lo anterior, se recomienda que la gestión de la información de usuarios y citas se realice mediante archivos de texto almacenando objetos JSON (*JavaScript Object Notation*) [[2]](#2) desde diccionario de Python. No se permite el uso de bibliotecas adicionales o bases de datos.

## Representación de infomración de usuarios

Para este reto se debe codificar un programa que permita representar la información de usuarios mediante diccionarios Desde el punto de vista de la visión por computadora, las imágenes son representadas como matrices o arreglos bidimensionales, en donde el número de columnas corresponde al ancho de la imagen en pixeles y el número de filas corresponde al alto de la imagen en pixeles. Por ejemplo, en la siguiente ecuación

$$
I = \begin{pmatrix}
  121 & 240 & 30 \\
  1784 & 58 & 161 \\
  75 & 18 & 93
\end{pmatrix}
$$

$I$ representa una imagen de 3x3 pixeles en escala de grises, donde los valores cercanos a 255 tienen un nivel de intensidad cercano al blanco y los valores más cercanos a 0 tienen un valor de intensidad cercano al negro. En general, los pixeles tienen valores de intensidad entre 0 y 255.

Para lo anterior, considere el programa [test_gray.py](test_gray.py) y la imagen [gray.bmp](gray.bmp). Ejecute el programa, analice su código fuente e identifique lo que realiza así como la salida en la terminal.

De otro lado, para el almacenamiento y visualización de imágenes a color se requiere el uso de tres matrices: una matriz correspondiente al plano de color azul (*blue*), una matriz correspondiente al plano de color verde (*green*) y una matriz correspondiente al plano de color rojo (*red*). Este modelo se conoce como BGR. 

La representación BGR se deriva de los colores primarios de la luz, en ese sentido los demás colores se obtienen a partir de mezclas de los tres colores primarios. Por ejemplo, el color amarillo se obtiene con una mezcla de la siguiente manera: valor de azul (*blue*) B=0, verde (*green*) G=255 y rojo (*red*) R=255. De forma similar, un color violeta puede ser obtenido con la siguiente mezcla: valor de azul (*blue*) B=255, verde (*green*) G=0 y rojo (*red*) R=255.

Para lo anterior, considere el programa [test_image.py](test_image.py) y la imagen [blue_car.jfif](blue_car.jfif). Ejecute el programa, analice su código fuente e identifique lo que realiza así como la salida en la terminal.

## Reto 1: Generación de una imagen monocromática

Construya un programa que genere una imagen de tamaño 640x480 pixeles que contenga en el centro un cuadrado blanco de 200x200 pixeles, el resto de la imagen debe ser negra.

## Reto 2: Identificación de colores

Modifique el programa [test_image.py](test_image.py) para calcular los valores promedio de cada plano de color.

A partir del programa modificado, construya un nuevo programa que le solicite al usuario el nombre de una de las imágenes  [blue_car.jfif](blue_car.jfif),  [red_car.jfif](red_car.jfif) o  [yellow_car.jfif](yellow_car.jfif) e identifique el color del automovil.

Asegúrese que la identificación se realice a través de una función llamada `identifyColor`


## Reto 3: Operadores para detección de bordes

Para este reto requiere que usted construya un programa que identifique correctamente en las imágenes [blue_car.jfif](blue_car.jfif),  [red_car.jfif](red_car.jfif),  [yellow_car.jfif](yellow_car.jfif) o [empty.jfif](empty.jfif) si el puesto de parqueo correspondiente se encuentra ocupado o disponible. Ayuda: Consulte el funcionamiento de la función `Canny` de OpenCV.

Asegúrese que la identificación se realice a través de una función llamada `identifySpot`

## Retor 4: Construcción de maqueta

En este último reto usted deberá construir la maqueta del proyecto y verificar el funcionamiento del programa del punto anterior haciendo uso de una cámara, para esto considere el programa [VerCamara.py](VerCamara.py).

## Entrega del laboratorio

El laboratorio debe ser presentado mediante:

1. Repositorio en GitHub.
2. Informe de laboratorio.

El informe de laboratorio y el enlace al repositorio de GitHub deben ser compartidos en el enlace dispuesto para tal fin en la plataforma Google Classroom.

## Referencias

<a id="1">[1]</a> 
Geeks for Geeks, "Javascript JSON",url=[https://www.w3schools.com/js/js_json.asp](https://www.w3schools.com/js/js_json.asp).

<a id="2">[2]</a> 
W3schools, "What is an IP Address?",url=[https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/
](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/
).
