# Diagrama VSM

### Cálculos generales: Demanda, Takt Time
Se realizan los cálculos del tiempo disponible en la planta de producción, teniendo en cuenta la cantidad de turnos al día, días de trabajo, tiempos de descanso,
entre otros.

También se calcula el takt time para cada uno de los productos: Organizador, repisa y casa para gatos. Así, se obtiene la cantidad de productos que se debe producir
por segundo o por minuto para cubrir la demanda estimada en el mercado colombiano de estos productos. 

![Calculos](https://user-images.githubusercontent.com/51938754/230691697-0f82631b-dcce-405e-82ae-85dad9f12245.png)

Se puede ver que el tiempo disponible por día son 24000 segundos o 6.67 horas.

Se calcula la cantidad de tableros exactos para cada lote de producción al mes, según la demanda de cada producto:

![NumeroTableros](https://user-images.githubusercontent.com/51938754/230692590-c8916630-6b21-40fe-86b9-e20f1e7cb020.png)

## Pre-automatización

### Productos-Procesos

Se genera la tabla de procesos necesarios para la producción de cada artículo. Con esto se tiene una clasificación adecuada de los productos, los cuáles comparten más del 70% de los procesos.

![produccto_vs_proceso](https://user-images.githubusercontent.com/51938754/226518361-1c0c5f2e-a1e2-4b46-80cf-7d6cd1823fff.PNG)


### Disponibilidad

Se investiga sobre la disponibilidad de cada máquina a usar durante la producción; para esto se investiga sobre la industria de madera en artículos o páginas de proveedores, con esto se puede definir una disponibilad teórica. Se usan las siguentes fórmulas:

![Calculo_disp](https://user-images.githubusercontent.com/51938754/230692239-24cb158a-c74a-4fbd-8fa8-2ab3f51efd6d.png)
![Calculo_disp2](https://user-images.githubusercontent.com/51938754/230692397-2d760233-81d1-40d6-99c9-458487e1455c.png)

Se clacula la disponibilidad de las máquinas de los procesos:

![Disponibilidad](https://user-images.githubusercontent.com/51938754/230693694-890f05e5-9872-4e21-ac8a-74e5c22a5f77.png)

Los datos para los cálculos son obtenidos de las siguientes referencias:

* Sierra: https://8pfs.short.gy/DDXFfT
* Fresadora CNC: http://tangara.uis.edu.co/biblioweb/tesis/2015/157836.pdf
* Router para madera: https://www.woodworkhubby.com/how-long-do-router-bits-last/
* Limas para madera: https://labois.com/madera/limas-escofinas-carpinteria-madera/
* Barnizado: https://www.youtube.com/watch?v=sDyuOxmJu3c y https://powdertronic.com/principales-partes-y-mantenimiento-de-una-pistola-para-pintar/
* Robot KUKA: https://www.dempro.co/post/cada-cuanto-se-deben-hacer-los-mantenimientos-en-los-robots-kuka

### Diagrama VSM pre-automatización

Con estos datos se procede a realizar el digrama VSM o Value Stream Mapping, contando con la información de la demanda, tiempos de los procesos previamente mostrados 
([Documento tiempos estimados por proceso](https://github.com/PurpleWood-APM/Documentacion-Proyecto/blob/main/gestion-produccion/TiemposEstimadosProduccion.md)), disponibilidad de las máquinas para cada proceso y los diagramas de flujo detallados para cada producto ([Diagramas de flujo](https://github.com/PurpleWood-APM/Documentacion-Proyecto/tree/main/gestion-produccion/esquemas-SeleccionDeProductos)).

![VSM_pre](https://user-images.githubusercontent.com/51938754/230695004-af738ec9-b37b-4e4b-9a45-6a32f478716d.png)
https://lucid.app/lucidchart/22ce5c2b-ee08-4e71-a5f5-4fa62de4c11d/edit?viewport_loc=-34%2C27%2C3483%2C1503%2C0_0&invitationId=inv_8d96285d-1d1e-4bef-90a1-d884c3b4282a

Se identifican momentos clave para el inventario de productos intermedios necesarios para otros procesos posteriores e inventario de los productos terminados. Además,
se encuentran el tiempo o plazo total de producción LT = 21 minutos y el tiempo de valor añadido VA = 33 horas.

## Pos-automatización

De acuerdo al diagrama pre-automatización y los requerimiento generales del takt time y la demanda, se procede a realizar el proceso de mejorar las estrategias pre-automatización:

1.  Primero se hizo una reevaluación de los procesos involucrados en la producción, se eliminaron procesos que no eran necesarios o se podían hacer en una misma estación:
    * Se eliminaron los procesos de biselado, resanado y pintura. Esto es debido al material usado (Triplex fenólico), el cual ya tiene acabados apropiados  y no es necesario una pintura adicional al barnizado. Por lo tanto, acortamos tiempos en la producción, tanto tiempos de espera por el almacenamiento adicional de la pintura como de alistamiento de las herramientas para el biselado y resanado.
    * Se juntaron los procesos de corte y fresado en una misma estación, gracias a que se cotizó una máquina con la capacidad de hacer los dos procesos, acortando así tiempos de alistamiento y transporte de la materia prima a otra estación.

2.  Se disminuye el tiempo de mantenimiento de algunas máquinas, buscano otras opciones de equipos y máquinas, aumentando su disponibiliad.
3.  Implementación de una celda robótica para el barnizado, junto con banda trasnportadoras aéreas (Head Conveyor) para su transporte continuo y almacenamiento ágil.
4.  Un proceso de inspección de fallas, basado en una cámara para detección de fallas en las piezas y un actuador neumático que empuja la pieza, en caso
de presentar fallas, fuera de la línea principal de producción para no ser empaquetado. Con esto se mejora la calidad de los productos finales.
### Procesos y disponibilidad

Por ende, se tienen los siguiente procesos con su rescpectiva disponibilidad:

![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/715f3b52-0f4b-49b8-908a-d0c55d9e93e5)

La disponibiliad es calculada de acuerdo a tiempos de mantenimiento y reparación de fallas, que se encontraron buscando en artículos sobre la vida útil de estas máquinas y con las fórmulas antes mencionadas, se presenta un resúmen a continuación:

![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/8ff4880c-1124-4b87-b729-b23d3d013ec1)

Los datos para los cálculos son obtenidos de las siguientes referencias:

* CNC: https://www.upkeep.com/learning/preventive-maintenance-on-cnc-machines/
* Lijadora: https://www.educarex.es/pub/cont/com/0055/documentos/10_Información/07_Herramientas/La_lijadora.pdf
* Robot: https://www.dempro.co/post/cada-cuanto-se-deben-hacer-los-mantenimientos-en-los-robots-kuka
* Actuador neumático: https://www.distritec.com.ar/cuando-debo-realizar-el-mantenimiento-de-los-cilindros-neumaticos/#:~:text=Entre%20500%20y%203000%20km%20recorridos%20semanales%20es%20considerable%20realizar%20el%20mantenimiento.

### Características para construcción dle diagrama

Se presenta una tabla con los procesos e información necesaria de cada uno para construir el VSM:

![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/51de03e5-3050-4fb6-94a6-33d66c647f15)


### Diagrama VSM pos-automatización

Con estos datos se procede a realizar el digrama VSM o Value Stream Mapping, contando con la información de la demanda, tiempos de los procesos previamente mostrados 
([Documento tiempos estimados por proceso](https://github.com/PurpleWood-APM/Documentacion-Proyecto/blob/main/gestion-produccion/TiemposEstimadosProduccion.md)), disponibilidad de las máquinas para cada proceso y los diagramas de flujo detallados para cada producto ([Diagramas de flujo](https://github.com/PurpleWood-APM/Documentacion-Proyecto/tree/main/gestion-produccion/esquemas-SeleccionDeProductos)).

![VSM-pos](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/1aec4a5a-15d1-4f6a-a35e-9cd6bb351e64)
https://lucid.app/lucidchart/128ed46a-2627-4925-9767-d102effc57cf/edit?viewport_loc=145%2C-150%2C3536%2C1826%2C0_0&invitationId=inv_a2124c5f-1b73-47c4-9161-48341412ba24

Se observan el tiempo de producción y tiempo de valor añadido, presentando una mejora en este último. El tiempo de corte y fresado es alto debido a que por cada tabla de madera salen 30 o 12 piezas y el tiempo de corte de todas estas piezas es de 2 horas y 30 minutos; hasta que no se corten todas las piezas no es posible continuar la producción.

Se destaca el uso de tarjetas Kanban, lo que permite disminuir la cantidad de procesos que requieren comunicación directa con control de producción, ya que se pueden comunicar los procesos a nivel bajo, con solo una interfaz a control del producción.


