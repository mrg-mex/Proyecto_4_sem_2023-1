# Proyecto_4_sem_2023-1
# Armado e implementación de un robot móvil Nvidia Kaya

| Código | Description |
| ------:| ----------- |
| ***Asignatura*** | Robótica *2135* | 
| **Robotica-2023-I**  | Proyecto Nvidia Kaya |
| **IT102321-C002** | Sistema Ciber-Físico - Proyecto - Módulo  |

## Contenido

- [Objetivo](#objetivo)
- [Metas](#metas)
- [Productos](#productos)
- [Introducción](#introducción)
- [Desarrollo](#desarrollo)
- [Autores](#autores)
- [Referencias](#referencias)

## Objetivo
Implementar un robot Nvidia Kaya para la implementación de algoritmos de esquemas de navegación autónoma en un espacio determinado.

## Metas

- Armar el robot Nvidia Kaya.
- Implementar las herramientas de simulación del robot desarrolladas para la plataforma.
- Realizar una prueba de funcionamiento de la plataforma del robot.

## Productos

- Robot Nvidia Kaya
- Repositorio con archivos de prueba del robot.
- Simulación del robot navegando en un ambiente determinado.*


## Introducción

Dentro de la automatización inteligente se ha observado que los robots se han vuelto cada vez más omnipresentes en la vida diaria desde su fabricación hasta su uso comercial e industrial. Sin embargo, su desarrollo se torna complejo, lento, desafiante y costoso debido a los entornos y escenarios no estructurados en casos de uso.
Por esta razón, la empresa NVIDIA se ha especializado en el desarrollo de unidades de procesamiento gráfico y tecnologías de circuitos integrados para estaciones de trabajo como lo es el robot móvil “Kaya”, el cual se ejecuta en la plataforma NVIDIA Jetson NANO para implementar sistemas de inteligencia artificial.[[1]](#1)

Entonces se puede decir que es un robot de código abierto, el cual es impulsado por una serie de aplicaciones empaquetadas con el SDK de Isaac y ejecutadas mediante la Jetson Nano para proporcionar un punto de partida accesible para el desarrollo de la robótica. Lo curioso de dicho robot es que se diseñó por medio de piezas impresas en 3D y componentes “básicos” con la finalidad de hacer un robot más accesible.

Kaya es un robot de tipo holonómico, es decir, es capaz de modificar su dirección de forma instantánea y sin la necesidad de rotar previamente gracias a que posee una unidad de tres ruedas[[2]](#2). Además, con ayuda de su cámara de profundidad RealSense le permite recibir información del entorno en el cual lo rodea con el fin de mapear, localizar y reconocer objetos. Aunado a lo anterior, la disposición de una IMU y de los motores de las ruedas permiten estimar la posición a través de la rotación de las ruedas a lo largo del tiempo. 

Existen diversas aplicaciones que puede realizar el robot, sin embargo, es de vital importancia conocer la manera en la cual se implementan las herramientas necesarias para su funcionamiento desde su cámara RealSense hasta el CAD requerido para simularlo en algún entorno de programación como lo es MATLAB. Por ello, el presente repositorio abordará dichas implementaciones para poner en funcionamiento al robot Kaya.


## Desarrollo

**Instalación del visor RealSense**

**Simplificación de polígonos sobre el CAD del ensamble**

Para este punto es necesario disminuir considerablemente los polígonos con la finalidad de ahorrar recursos gráficos y de memoria a la hora de implementar el CAD en diferentes softwares de simulación que permitan analizar el comportamiento del robot móvil. La simplificación se llevó a cabo mediante los siguientes pasos:
1.  El CAD completo se encuentra en OnShape [3], en el cual se descargaron únicamente las partes significativas del ensamble en formato “STEP”. Esto último es       esencial, pues las piezas se modificaron en SolidWorks para posteriormente realizar el urdf.
      Imagen
      
2.  En total se descargaron 4 piezas de subensamble, las cuales se debían modificar para lograr la disminución de polígonos. A la figura 1 se le retiró la plataforma de recogedor, tal y como se muestra en la figura 2.

3. La figura 3 contenía la parte electrónica del robot, esto es: 
- Kit de desarrollo NVIDIA Jetson Nano
- Placa IMU Bosch
- Concentrador de potencia de 6 puertos
- Batería de iones de litio
- Regulador reductor de CC-CC de 5V 
- Interruptor

    Por lo que modificar esta pieza fue fundamental a la hora de reducir polígonos.
    Cabe destacar que el regulador reductor de CC-CC de 12 V no se logró quitar del subensamble, debido a una restricción que venía desde la página OnShape, sin         embargo, la pieza no contenía polígonos considerables.

4. Con relación a la figura 5, solo se retiraron las antenas Wi-Fi de doble banda

5. Finalmente, el subensamble de las ruedas contenía la base del servomotor MX-12W unida a las llantas, por lo cual se tuvieron que separar con la finalidad de elaborar 2 archivos diferentes, los cuales permitieran generar movilidad en el entorno de simulación.

6. Al finalizar la modificación de las diferentes piezas, se procedió a ensamblar de tal forma que la “carcasa” y las “llantas” resultarán en dos ensambles diferentes listos para los archivos de simulación.


Cuando se obtuvieron las piezas deseadas se empleó el software Blender únicamente para corroborar la disminución de los polígonos trabajados. De esta manera, se realizó una comparativa del ensamble original al ensamble modificado, en el cual se observó una reducción de aproximadamente el 83% respecto al ensamble original, tal como lo muestran la figura 5 y 6.
Cabe mencionar que a lo largo del proyecto se estuvieron haciendo diversas pruebas para eliminar la mayor cantidad de polígonos presentes, por lo cual el presente repositorio tiene 2 carpetas de CAD. Sin embargo, las piezas finales y las descritas anteriormente se subieron como un Branch titulado “CAD-Simplificado-SOLIDWORKS” en la carpeta de “CAD-Simplificado” con el nombre de [`Kaya_STEP`](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/tree/CAD-Simplificado-SOLIDWORKS/CAD_simplificado/Kaya_STEP).

El siguiente paso para realizar es generar un archivo URDF, el cual permitirá describirlo mediante su modelo cinemático y dinámico del robot necesario para su simulación dinámica y control.
Unified Robot Description Format (URDF) se trata de un archivo XML que permite describir un robot. La descripción del robot consiste en eslabones o links rígidos conectados por medio de las articulaciones o joints. El modelo URDF permite representar un modelo cinemático y dinámico del robot necesario para su simulación dinámica y para su control. Es fundamental considerar que no permite describir robots que no sigan una estructura tipo árbol y sus elementos no sean rígidos. [referencia]
Por lo anterior, se adjunta un video para generar dicho archivo con el CAD generado en la presente documentación. https://www.youtube.com/watch?v=CKlK5H8EguA&t=2423s


## Conclusiones

## Autores

| Iniciales  | Description |
| ----------:| ----------- |
| **EPM**  | Erik Peña Medina [GitHub profile](https://github.com/ErikFiUNAM) |
| **YGJ**  | Yeshua González Jiménez [GitHub profile](https://github.com/YeshuaGonzalez) |
| **LDBV**  | Leslie Dayana Bolaños Viquez [GitHub profile](https://github.com/lessliebv04) |
| **EVS**  | Eduardo Vega Solorzano [GitHub profile](https://github.com/eduVega1) |
| **KDR**  | Kevin De la Rosa Romero [GitHub profile](https://github.com/KevinDLRR) |
| **VSJE**  | Velazquez Sanchez Jose Emiliano [GitHub profile](pendiente) |
| **RIJL**  | Rivera Ibarra Juan Luis [GitHub profile](pendiente) |


## Referencias

<a id="1">[1]</a>  "NVIDIA Isaac SDK". NVIDIA Developer. Available https://developer.nvidia.com/isaac-sdk (accedido el 17 de enero de 2023).

<a id="2">[2]</a>   SA. "Sistemas holonómicos". Electric Bricks. Available http://blog.electricbricks.com/2010/07/sistemas-holonomicos/ (accedido el 17 de enero de 2023).

<a id="3">[3]</a>   "NVIDIA Kaya — ISAAC 2021.1 documentation". NVIDIA Documentation Center | NVIDIA Developer. Available https://docs.nvidia.com/isaac/doc/tutorials/assemble_kaya.html (accedido el 17 de enero de 2023).
