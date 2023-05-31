# Simulaciones y OEE

## Process Analysis
Se realiza la simulación del flujo de materias primas y ciclo de trabajo para la producción de los tres productos (Mesa organizadora, repisa y casa de gato). Para esto se realiza el flujo de los procesos de producción en el software Process Analysis, en el cuál se registran los procesos con características ya documentadas en [Documento tiempos estimados por proceso](https://github.com/PurpleWood-APM/Documentacion-Proyecto/blob/main/gestion-produccion/TiemposEstimadosProduccion.md) y [Cálculos para el digrama VSM](https://github.com/PurpleWood-APM/Documentacion-Proyecto/blob/main/gestion-produccion/DiagramaVSM.md).

![Captura1](https://user-images.githubusercontent.com/51938754/230700019-7dbe7cc9-88b7-4b7d-b629-8985d9f35200.PNG)
![Captura2](https://user-images.githubusercontent.com/51938754/230700023-de7e1d3b-ade0-4234-b6eb-107d088eb734.PNG)

Este fue un primer flujo realizado antes de aplicar estrategias de pre-automatizacón, pero fue punto de partida para la distribución. Por otro lad, por problemas técnicos con el software, se procede a desarrollar la simulación en Tecnomatix.

## Tecnomatix

Se realizó un diseño preliminar de la planta en Tecnomatix, para así observar la distribución de planta (Layout), identificar tiempos de inactividad, tiempos de ciclo, volumen de producción en un tiempo determinado, calidad, desempeño, disponibilidad, entre otros. 

![Planta](https://user-images.githubusercontent.com/51938754/230695854-bd9f3cf9-0aaf-4d64-9ce0-301e9d5b5d0a.png).
[Archivo preliminar de Tecnomatix](https://github.com/PurpleWood-APM/Documentacion-Proyecto/blob/main/gestion-produccion/Planta.spp)

Esta simulación se realizó antes de aplicar las estrategías de pre-automzatización; con base a esta distribución y el VSM pos-automatización se llegó a la siguente distribución de planta:

![distribucion_final_planta](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/febaf970-8e95-4cda-9230-db8d0eda1545)

[Distribución final](https://github.com/PurpleWood-APM/Documentacion-Proyecto/blob/main/gestion-produccion/distribucion_final_planta.jpg)

A la vez, tomando como punto de partida esta distribución, el VSM pos-automatización y las correspondientes caractéristicas de cada proceso se llega a la siguiente distribución de planta y simulación final en Tecnomatix:

![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/7e4b6ec5-8ab7-4c03-84f5-ca593857d2fd)
Archivo de la simulación:
[Simulación final Tecnomatix](https://github.com/PurpleWood-APM/Documentacion-Proyecto/blob/main/gestion-produccion/PurpleWood-tecnomatix.spp)

En el programa se configuran las características de cada proceso: Tiempo de ciclo, tiempo de set-up, disponibilidad intrínseca, promedio de tiempo de inactividad. También se configuran varios tipos de piezas para identificar los 3 tipos de productos generados y sus respectivas piezas, según la siguiente nomenclatura:

<img src="https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/0a48d4d9-d634-4882-905b-9e13dbb1fa60" width= "500" height = "180">


Se configura el flujo de piezas a través de los procesos de fabricación, teniendo en cuenta el horario disponible, un solo turno, días laborales en cada semana y descansos durante la jornada laboral. También, se configuran los trabajadores (en total 6 trabajadores para la planta) asignados a cada estación y sus tareas a realizar, ya sea de procesamiento o transporte. 

Se muestran algunos resultados del reporte de la simulación, para tres días, tiempo donde ya se despacharon lotes de cada producto:

<img src="https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/e79884fb-d4f9-43ba-a3af-ae099dbd30fd" width= "700" height = "300">

<img src="https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/4a01f1a4-c44f-4a28-b18e-4f5f857fbc56" widtg = "300" height ="100">

El reporte completo es el siguiente:
[Reporte Tecnomatix](https://github.com/PurpleWood-APM/Documentacion-Proyecto/blob/main/gestion-produccion/informe_tecnomatix_procesos.jpg)

Se debe tener en cuenta que no se pudo realizar el traspaso automático de materiales de almacenamiento a una siguiente estación, por esto aparece el porcentaje de Storage en 0%; por ende, se simularon estos tiempos por separado, siendo el tiempo promedio en almacenamiento de una pieza 2 días. De acuerdo a estos resultados se realizan los cálculos de tiempos de espera y de trabajo, y poder obtener el tiempo de ciclo total y tiempos de espera no planeados.

<img src="https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/e5bbca7f-2488-4d7e-944c-bfcbfb5b4e69" width= "400" height = "250">

Se observa que el tiempo de espera durante 1 día de trabajo es de 1,43 horas y el tiempo de ciclo o trabajo es de 5,79 horas.

Se verifica que se cumple con la demanda de productos y se alcanzan a producir unidades extras de casas de gato, mesas organizadoras y repisas:

<img src="https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/02741637-2a7b-4ba1-8e9c-e346da1f9df8" width ="300" height = "120">





