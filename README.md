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
- [Introducción](#introduccion)
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
