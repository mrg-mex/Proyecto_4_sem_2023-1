# Implementacion

### Armado del Robot

#### Material Faltante

* Separador roscado hembra hexagonal de 6mm M3 18mm largo

### Instalaci�n del sistema operativo

Para el sistema embebido Jetson nano de Nvidia, es necesario usar una imagen para el sistema operativo dise�ada espec�ficamente para esta plataforma. Se usa un sistema operativo Ubuntu en su versi�n 18.03, esta imagen se puede encontrar en la documentaci�n de Nvidia en la siguiente p�gina :

- [get-start-jetson-nano-devkit](https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit#write)

se debe seleccionar las instrucciones para el sistema operativo que est�s usando para instalarlo.

Para instalarlo en este proyecto se us� el programa Rufus con una memoria microSD de 64BG y adaptador a USB, es importante recalcar que lo que est� escrito en la microSD se borrar� al instalar el sistema operativo.

### Isaack SDK

El NVIDIA Isaac SDK es un kit de herramientas que incluye bloques de construcci�n y herramientas que aceleran los desarrollos de robots que requieren una mayor percepci�n y caracter�sticas de navegaci�n habilitadas por la IA

1.- Descargar Isaac SDK de la p�gina de nvidia
* Se tiene que crear una cuenta
* Se tiene que registrar en el proyecto, sin el registro no se dar� acceso a la imagen

2.- Descomprimir el archivo SDK en home

3.- Instalar jetpack 4.5.1
	sudo apt update
	sudo apt install nvidia-jetpack

4.- Installing Dependencies on the Desktop

	./engine/build/scripts/install_dependencies.sh
	gcc-aarch64-linux-gnu g++-aarch64-linux-gnu

5.- Nvidia GPU Driver: En esta parte se marca un error ya que no se encuentra la versi�n que se requiere

	sudo add-get-repository ppa:graphics-drivers/ppa
	sudo apt-get update
	sudo apt-get install nvidia-driver-440 (aqui nos quedamos)

6.- Instalaci�n de Bazel. Esta librer�a es necesaria para ejecutar programas, pero se tienen errores de instalaci�n porque la librer�a ya no se encuentra en el repositorio, por lo que hay que optar por los archivos binarios de nuevo.

	sudo apt install apt-transport-https curl gnupg
	curl -fsSL https://bazel.build/bazel-release.pub.gpg | gpg --dearmor >bazel-archive-keyring.gpg
	sudo mv bazel-archive-keyring.gpg /usr/share/keyrings
	echo "deb [arch=amd64 signed-by=/usr/share/keyrings/bazel-archive-keyring.gpg] https://storage.googleapis.com/bazel-apt stable jdk1.8" | sudo tee /etc/apt/sources.list.d/bazel.list

Para ver el error se puede consultar:

- [unable-to-install-bazel-on-ubuntu](https://stackoverflow.com/questions/45767275/unable-to-install-bazel-on-ubuntu-14-04-using-apt-get)



### Recomendaciones

Para encender la jetson nano asegure de tener la microSD en su respectiva ranura, y si se alimenta la tarjeta a trav�s del Jack y eliminador el jumper J48 se debe tener puesto, si la alimenta es a trav�s del puerto microusb entonces no deber� tener el jumper puesto.



En este readme va:

	Armado del Robot
	Material Faltante 

		Falta separador roscado hembra de aluminio hexagonal de 6mm M3 18mm largo 

	Instalación del sistema operativo
		Donde se encoentró la imagen
		Cómo se obtuvo la imagen
		Pasos a seguir para instalación
	Control de motores
		Instalación de Dynamixel Wizard 2.0
		Escaneo
		ID
		Configuración de Baudrate defalutl(1M) 57600 (tutoriales)
		Tabla de Memoria

		Repositorio de Dynamixel SDK
		Liga de github
		Liga a videos y tutoriales
		¿Por qué no funcionó?
		
		Alternativa
		
		
