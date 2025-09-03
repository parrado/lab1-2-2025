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

* Registro de usuarios mediante número de cédula y contraseña.
* Registro del rol del usuario, paciente o médico.
* Inicio de sesión en el sistema con almacenamiento de dirección IP (*Internet Protocol*)

De otro lado, para el caso de las citas médicas, el sistema debe contar con las siguientes características mínimas:

* Registro de la información del paciente y del médico (números de cédula).
* Registro de la fecha y hora de la cita.
* Registro de la prescripción médica.


Considerando lo anterior, se recomienda que la gestión de la información de usuarios y citas se realice mediante archivos de texto almacenando objetos JSON (*Javascript Object Notation*) [[1]](#1)

Para instalar la biblioteca OpenCV solo digite el siguiente comando desde una terminal: `python -m pip install opencv-contrib-python`. En todo caso, podrá encontrar una explicación detallada en el [siguiente video](https://www.youtube.com/watch?v=yYrWq3BfRuo). 

Si se genera algún error con `pip` solo tiene que actualizarlo, esta es la manera correcta de hacerlo desde una terminal: 

`python -m pip install --upgrade pip`\
`pip install --upgrade pip`

Puede usar el programa de prueba [OpenCv.py](OpenCv.py) para verificar que la biblioteca OpenCV se ha instalado correctamente, en particular el programa imprime en la terminal la versión de OpenCV instalada.

Finalmente, con el programa [VerCamara.py](VerCamara.py) se verificará el acceso correcto a la cámara, al ejecutarse deberá abrir una ventana en donde se visualiza la cámara frontal de su computador portátil, también puede usarlo para acceder a una cámara conectada a alguno de los puertos USB. Analice el funcionamiento del programa [VerCamara.py](VerCamara.py).


## Representación de imágenes en OpenCV

Desde el punto de vista de la visión por computadora, las imágenes son representadas como matrices o arreglos bidimensionales, en donde el número de columnas corresponde al ancho de la imagen en pixeles y el número de filas corresponde al alto de la imagen en pixeles. Por ejemplo, en la siguiente ecuación

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
W3schools, "Javascript JSON",url=[https://www.w3schools.com/js/js_json.asp](https://www.w3schools.com/js/js_json.asp).
