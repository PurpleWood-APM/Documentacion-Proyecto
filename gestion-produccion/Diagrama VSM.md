## Diagrama VSM

### Cálculos generales: Demanda, Takt Time
Se realizan los cálculos del tiempo disponible en la planta de producción, teniendo en cuenta la cantidad de turnos al día, días de trabajo, tiempos de descanso,
entre otros.

También se calcula el takt time para cada uno de los productos: Organizador, repisa y casa para gatos. Así, se obtiene la cantidad de productos que se debe producir
por segundo o por minuto para cubrir la demanda estimada en el mercado colombiano de estos productos. 

![Calculos](https://user-images.githubusercontent.com/51938754/230691697-0f82631b-dcce-405e-82ae-85dad9f12245.png)

Se puede ver que el tiempo disponible por día son 24000 segundos o 6.67 horas.

Se calcula la cantidad de tableros exactos para cada lote de producción al mes, según la demanda de cada producto:

![NumeroTableros](https://user-images.githubusercontent.com/51938754/230692590-c8916630-6b21-40fe-86b9-e20f1e7cb020.png)

### Productos-Procesos

Además, se genera la tabla de procesos necesarios para la producción de cada artículo. Con esto se tiene una clasificación adecuada de los productos, los cuáles comparten más del 70% de los procesos.

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

### Diagrama VSM

Con estos datos se procede a realizar el digrama VSM o Value Stream Mapping, contando con la información de la demanda, tiempos de los procesos previamente mostrados 
([Documento tiempos estimados por proceso](https://github.com/PurpleWood-APM/Documentacion-Proyecto/blob/main/gestion-produccion/TiemposEstimadosProduccion.md)), disponibilidad de las máquinas para cada proceso y los diagramas de flujo detallados para cada producto ([Diagramas de flujo](https://github.com/PurpleWood-APM/Documentacion-Proyecto/tree/main/gestion-produccion/esquemas-SeleccionDeProductos)).

![VSM_pre](https://user-images.githubusercontent.com/51938754/230695004-af738ec9-b37b-4e4b-9a45-6a32f478716d.png)
https://lucid.app/lucidchart/22ce5c2b-ee08-4e71-a5f5-4fa62de4c11d/edit?viewport_loc=-34%2C27%2C3483%2C1503%2C0_0&invitationId=inv_8d96285d-1d1e-4bef-90a1-d884c3b4282a

Se identifican momentos clave para el inventario de productos intermedios necesarios para otros procesos posteriores e inventario de los productos terminados. Además,
se encuentran el tiempo o plazo total de producción LT = 21 minutos y el tiempo de valor añadido VA = 33 horas.
