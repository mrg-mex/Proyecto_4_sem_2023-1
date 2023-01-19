# Simplificación de polígonos sobre el CAD del ensamble

Para este punto es necesario disminuir considerablemente los polígonos con la finalidad de ahorrar recursos gráficos y de memoria a la hora de implementar el CAD en diferentes softwares de simulación que permitan analizar el comportamiento del robot móvil. La simplificación se llevó a cabo mediante los siguientes pasos:
1.  El CAD completo se encuentra en OnShape [[4]](#4), en el cual se descargaron únicamente las partes significativas del ensamble en formato “STEP”. Esto último es       esencial, pues las piezas se modificaron en SolidWorks para posteriormente realizar el urdf.

      Figura 1. CAD completo de la página OnShape.
![KayaOnShape](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/blob/main/Imagenes_Videos/KayaOnShape.png)                                                        
      
2.  En total se descargaron 4 piezas de subensamble, las cuales se debían modificar para lograr la disminución de polígonos. A la figura 2 se le retiró la plataforma de recogedor, tal y como se muestra en la figura 3.

Figura 2. Marco base original.![MarcoBaseOriginal](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/blob/main/Imagenes_Videos/MarcoBaseOriginal.png) 


![MarcoBase](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/blob/main/Imagenes_Videos/MarcoBase.png)

Figura 3. Marco base modificado.


3. La figura 4 contenía la parte electrónica del robot, esto es: 
- Kit de desarrollo NVIDIA Jetson Nano
- Placa IMU Bosch
- Concentrador de potencia de 6 puertos
- Batería de iones de litio
- Regulador reductor de CC-CC de 5V 
- Interruptor

![NucleoElectronico](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/blob/main/Imagenes_Videos/NucleoElectronicoOriginal.png)

Figura 4. Parte electrónica.

   Por lo que modificar esta pieza fue fundamental a la hora de reducir polígonos.
    Cabe destacar que el regulador reductor de CC-CC de 12 V no se logró quitar del subensamble, debido a una restricción que venía desde la página OnShape, sin         embargo, la pieza no contenía polígonos considerables.

4. Con relación a la figura 5, solo se retiraron las antenas Wi-Fi de doble banda.

![RealSense](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/blob/main/Imagenes_Videos/PuenteRealSense.png)

Figura 5. Cámara RealSense sin antenas WiFi.

5. Finalmente, el subensamble de las ruedas contenía la base del servomotor MX-12W unida a las llantas, por lo cual se tuvieron que separar con la finalidad de elaborar 2 archivos diferentes, los cuales permitieran generar movilidad en el entorno de simulación.

![BaseRuedas](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/blob/main/Imagenes_Videos/RuedasServomotores.png)

Figura 6. Base del servomotor con ruedas.

6. Al finalizar la modificación de las diferentes piezas, se procedió a ensamblar de tal forma que la “carcasa” y las “llantas” resultarán en dos ensambles diferentes listos para los archivos de simulación.

![CarcasaNX](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/blob/main/Imagenes_Videos/CarcasaNX.png)

Figura 7. Carcasa ensamblada.

![LlantasNX](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/blob/main/Imagenes_Videos/RuedaNX.png)

Figura 8. Ruedas ensambladas.

Cuando se obtuvieron las piezas deseadas se empleó el software Blender únicamente para corroborar la disminución de los polígonos trabajados. De esta manera, se realizó una comparativa del ensamble original al ensamble modificado, en el cual se observó una reducción de aproximadamente el 83% respecto al ensamble original, tal como lo muestran la figura 9 y 10.

![PoligonosIniciales](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/blob/main/Imagenes_Videos/PoligonosIniciales.png)

Figura 9. Polígonos iniciales.

![PoligonosFinales](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/blob/main/Imagenes_Videos/PoligonosFinales.png)

Figura 10. Polígonos finales.


Cabe mencionar que a lo largo del proyecto se estuvieron haciendo diversas pruebas para eliminar la mayor cantidad de polígonos presentes, por lo cual el presente repositorio tiene 2 carpetas de CAD. Sin embargo, las piezas finales y las descritas anteriormente se subieron como un Branch titulado “CAD-Simplificado-SOLIDWORKS” en la carpeta de “CAD-Simplificado” con el nombre de [`Kaya_STEP`](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/tree/CAD-Simplificado-SOLIDWORKS/CAD_simplificado/Kaya_STEP).

![ArchivosRepositorio](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/blob/main/Imagenes_Videos/ArchivosRepositorio.png)

Figura 11. Archivos de los ensambles finales del CAD.

Finalmente, se abrirán las piezas en SOLIDWORKS como se ve a continuación:

![CarcasaSolid](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/blob/main/Imagenes_Videos/CarcasaSolid2.png)

Figura 12. Carcasa en SOLIDWORKS.

![RuedasSolid](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/blob/main/Imagenes_Videos/RuedasSolid2.png)

Figura 13. Ruedas en SOLIDWORKS.


El siguiente paso para realizar es generar un archivo URDF, el cual permitirá describirlo mediante su modelo cinemático y dinámico del robot necesario para su simulación dinámica y control. Es fundamental considerar que no permite describir robots que no sigan una estructura tipo árbol y sus elementos no sean rígidos [[5]](#5).
Por lo anterior, se adjunta un video para generar dicho archivo con el CAD generado en la presente documentación.

[![Diseño de herramientas computacionales para la robótica](https://github.com/mrg-mex/Proyecto_4_sem_2023-1/blob/main/Imagenes_Videos/URDF.png)](https://www.youtube.com/watch?v=CKlK5H8EguA&t=2423s)

Figura 14. Enlace para URDF.

