## Diagrama VSM

Se realizan los cálculos del tiempo disponible en la planta de producción, teniendo en cuenta la cantidad de turnos al día, días de trabajo, tiempos de descanso,
entre otros.

También se calcula el takt time para cada uno de los productos: Organizador, repisa y casa para gatos. Así, se obtiene la cantidad de productos que se debe producir
por segundo o por minuto para cubrir la demanda estimada en el mercado colombiano de estos productos. 

![Calculos](https://user-images.githubusercontent.com/51938754/226517014-43e61aac-c231-4584-98c5-664550321fe0.PNG)

Se puede ver que el tiempo disponible por día son 24000 segundos o 6.67 horas.

Además, se genera la tabla de procesos necesarios para la producción de cada artículo. Con esto se tiene una clasificación adecuada de los productos, los cuáles comparten más del
70% de los procesos.

![produccto_vs_proceso](https://user-images.githubusercontent.com/51938754/226518361-1c0c5f2e-a1e2-4b46-80cf-7d6cd1823fff.PNG)

Con estos datos se procede a realizar el digrama VSM o Value Stream Mapping, contando con la información de la demanda, tiempos de los procesos previamente mostrados 
([Documento tiempos estimados por proceso](https://github.com/PurpleWood-APM/Documentacion-Proyecto/blob/main/gestion-produccion/TiemposEstimadosProduccion.md)), disponibilidad
de las máquinas para cada proceso y los diagramas de flujo detallados para cada producto ([Diagramas de flujo](https://github.com/PurpleWood-APM/Documentacion-Proyecto/tree/main/gestion-produccion/esquemas-SeleccionDeProductos)).


![VSM_pre](https://user-images.githubusercontent.com/51938754/226519959-791bd16e-3e82-4f1a-8bc8-44d3b5c19624.PNG)

Se identifican momentos clave para el inventario de productos intermedios necesarios para otros procesos posteriores e inventario de los productos terminados. Además,
se encuentran el tiempo o plazo total de producción LT = 21 minutos y el tiempo de valor añadido VA = 33 horas.
