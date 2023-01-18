
# Instrucciones para la instalación del Visor Realsense 

El objetivo de este README es describir la instalación del visor Realsense que funciona con la cámara Intel D435i, con la que tendrémos la posibilidad de adquirir un sensado robusto en la profundidad de las imagenes aún estando en movimiento, esto gracias a la IMU que la cámara tiene integrada lo cual permite una calibración rápida cuando existe movimiento en el robot. Esta cámara es ideal para aplicaciones de seguimiento y reconocimiento de diversos elementos. 

Al término de esta instalación será posible comenzar a hacer pruebas en ROS.

## Instalación del Intercambiador de archivos (Swapfile)

Esto se realiza con la finalidad de evitar problemas en la demanda de la memoria en la Jetson Nano al momento de ejecutar el script de interés. 

Para su instalación será necesario abrir la terminal y copiar el respositorio de JetsonHacksNano (Autor del cual nos apoyamos para la instalación) llamado installSwapfile (Link: https://github.com/JetsonHacksNano/installSwapfile) y colocamos la siguiente instrucción: 

     $ git clone https://github.com/JetsonHacksNano/installSwapfile.git

Posteriormente tenemos que ejecutar las siguientes instrucciones: 

     $ cd installSwapfile/
     $ ./installSwapfile.sh

NOTA: Para esta instalación ocurría un problema similar al siguiente:

     Error: fallocate: fallocate failed: Text file busy.
     
Para su solución fue necesario emplear el siguiente comando: 

     sudo swapoff -a

Y posteriormente volver a colocar el comando $ ./installSwapfile.sh, así se solucionó este problema. 

## Instalación del Visor Realsense

Para esta instalación será necesario copiar de nuevo otro repositorio del mismo autor, el cual es installLibrealsense (Link: https://github.com/JetsonHacksNano/installLibrealsense), es un procedimiento bastante similar a lo anterior. Para eso colocaremos la sieuinte instrucción: 

     $ git clone https://github.com/JetsonHacksNano/installLibrealsense.git
     
Para posteriormente ejecutar la siguiente línea de código: 

     $ cd installLibrealsense/ 

En mi caso el comando para la instalación $ ./installLibrealsense.sh no se completó con éxito, lo cuál me detuvo totalmente en la instalación de la aplicación para poder visualizar las imagenes por parte de la cámara. Sin embargo una alternativa que funcionó con éxito fue el sigiuente comando: 

     $ ./buildLibrealsense.sh
    
Lo cual automáticamente instalaría este visor junto con todos su módulos y complementos. Esto tardó aproximadamente 1 hora. Cuando finalice la instalación será necesario reiniciar la placa para que todo funcione exitosamente. Para eso no es necesario utilizar la terminal, basta con ir al último icono de la parte superior derecha, colocar Shut Down y posteriormente "Reiniciar". 

Finalmente para poder ejecutar la aplicación se coloca la siguiente instrucción: 

     $ cd /usr/local/bin
     
Una ves dentro de esta ubicación colocamos la siguiente instrucción: 

     $ ./realsense-viewer/
     
La aplicación procedera a ejecutarse y verémos la siguiente interfaz:

![image](https://user-images.githubusercontent.com/107418635/213064186-c411e289-11bf-4f63-88c1-1079c2f7ea69.png)

Para esto tenemos que tener conectada la cámara mediante algún puerto USB y automáticamente se reconocerá este dispositivo.

Del lado izquiero vemos la opción "RGB Camera", la resolución la cambiaremos a 1920 x 1080 y en "Avaiable Strams" en la opción "Color" seleccionaremos YUYV. Esto se ve de la siguiente manera: 

![image](https://user-images.githubusercontent.com/107418635/213065376-0fa27b32-63ff-416d-861b-115b92f15f29.png)

Finalmente para activar la visualización tenemos que colocar "ON" en "RGB Camera", de la siguiente manera: 

![image](https://user-images.githubusercontent.com/107418635/213066216-3c4f71db-dbec-4089-a982-0e8791749b6c.png)
