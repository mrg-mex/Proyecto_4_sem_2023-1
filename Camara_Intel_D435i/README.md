
# Instrucciones para la instalación del Visor Realsense 

EL objetivo de este README es describir la instalación del visor Realsense que funciona con la cámara Intel D435i, con la que tendrémos la posibilidad de adquirir un sensado robusto en la profundidad de las imagenes aún estando en movimiento, esto gracias a la IMU que la cámara tiene integrada lo cual permite una calibración rápida cuando existe movimiento en el robot. Esta cámara es ideal para aplicaciones de seguimiento y reconocimiento de diversos elementos. 

Al término de esta instalación será posible comenzar a hacer pruebas en ROS.

## Instalación del Intercambiador de archivos (Swapfile)

Esto se realiza con la finalidad de evitar problemas en la demanda de la memoria en la Jetson Nano al momento de ejecutar el script de interés. 

Para su instalación será necesario abrir la terminal y copiar el respositorio de JetsonHacksNano (Autor del cual nos apoyamos para la instalación) llamado installSwapfile colocando la siguiente instrucción:



