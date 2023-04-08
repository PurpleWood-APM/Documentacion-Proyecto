# Justificación de elección de procesos a automatizar con robotica.

## Consideraciones del proceso

Para hacer una correcta selección de los procesos a automatizar con robótica primero es pertinente recordar ciertos puntos sobre el proceso prodcutivo en el que estamos trabjando.

Recordemos que se opto por una producción basada en lotes donde las materias primas pasan por una serie de procesos y estaciones hasta convertirse en las piezas finales, sin embargo los procesos y estaciones depende de cada pieza y por ende estos procesos son parametrizados y ajustables segun se requiera. Esto le permite al proceso ser flexible, adaptable y escalable; esto dado que se tiene una gran cantidad de parametros ajustables segun los requerimientos que se tengan, lo que permitiria la fabricación de nuevas piezas y productos sin mayores afectaciones a la linea de producción. Se opto por este metodo de manufacura por lotes dada la naturaleza del proyecto y de los productos diseñados.

Una vez mencionado esto se hace un analisís de distintos procesos, a continuación se exponen los procesos escogidos y las razones que llevaron a esta selección.

## Definir criterios de selección
Para la selección de procesos a automatizar se opta por realizar una matriz de selección, es decir se asignan diferentes criterios. Luego se da un puntaje a cada proceso y se ponderan estos puntajes para la selección final, a continuación se mencionan los criterios que consideraremos

- Repetitibilidad: Se refiere a que tan mnotona o repetible es la tarea a realizar
- Exigencia respecto a personal capacitado: La tarea requiere personal especifico para su realización.
- Flexibilidad: Que tantos cambios presenta la tarea, por ejemplo ajustes respecto a cambios de prodcutos o cambios en ritmos de producción variable.
- Volumen: Que volumen de piezas son procesadas.
- Factibilidad: Que tanto costo implicaria la automatización con robótica
- Impacto: Que nivel de impacto implica el proceso automatizado versus el tradicional.

## Procesos considerados
A continuación listamos algunos de los procesos considerados:
- Dimensionamiento y corte
- Fresado y perfilado.
- Lijado.
- Pintura y acabado.
- Inspección de calidad.
- Traslado de piezas entre bandas.

## Matriz de selección
Se lista cada proceso y el puntaje asignado en cada uno de los criterios, para la ponderación se asigna a cada criterio una cantidad diferente de puntos para una suma de 100, los criterios más importantes son el impacto respectoa  la no automatización del proceso, la repetitibilida y la factibilidad de la automatización con robots.

| Proceso                  | Repetitibilidad(20) | Necesidad P.C.(5) | Flexibilidad(10) | Volumen(15) | Factibilidad (25) | Impacto(25) | Total(100) |
|--------------------------|---------------------|-------------------|------------------|-------------|-------------------|-------------|------------|
| Dimensionamiento y corte | 10                  | 5                 | 8                | 8           | 5                 | 10          | 46         |
| Fresado y perfilado.     | 12                  | 5                 | 7                | 5           | 5                 | 10          | 44         |
| Lijado                   | 8                   | 5                 | 5                | 12          | 5                 | 15          | 50         |
| Pintura y acabado        | 8                   | 4                 | 9                | 12          | 15                | 15          | 63         |
| Inspección de calidad    | 17                  | 5                 | 8                | 13          | 22                | 20          | 85         |
| Traslado de piezas       | 18                  | 1                 | 8                | 13          | 25                | 20          | 85         |

- Respecto a la repetitibilidad se le asignan puntajes mas altos a los procesos de inspección de calidad y translado de piezas dado que estos procesos no se ven modificados en mayor medida por el cambio de pieza o producto.
- Respecto a la necesidad de personal capacitado todos los procesos relacionados con el maquinado de las piezas  y la inspección de calidad requieren personal dado que pueden generar afectaciones a la integridad del trabajador o de la pieza. Por otro lado  se considera que el traslado de las piezas no requiere personal altamente capacitado.
- Repecto a la flexibilidad de los procesos a todos se les asigna un puntaje similar dado que al tratarse de una producción basada en lotes todos requieren ajustes de parametros segun la pieza o producto. La diferencia de puntaje se asigna segun la magnitud de los cambios requeridos.
- Respecto al volumen se asigna mayor puntaje a los procesos que actuan como cuelllos de botella: Por ejemplo mientras que la entrada a corte es un tablero de madera y sale un lote completo de piezas, el lijado y la inspección de calidad se hace pieza a pieza o producto a producto.
- Respecto a la factibilidad se asigna mayor puntaje a los procesos de inspección de calidad y traslado de peizas dado que son procesos de pick and place por lo que no requieren equipos altamente especializados ni que requieran mayores intervenciones sobre el espacio, a diferencia de los robots necesarios para los otros procesos.
- El impacto respecto al traslado de piezas y la inspección de calidad se hace en comparación a un operario, por lo que se tienen puntajes mas altos, por otro lado el fresado y corte si bien requieren un operario para el setup, el corte y fresado es realizado por maquinas cnc.

## Comentarios respecto a los procesos
Teniendo esto en cuenta los dos procesos seleccionados son el tralado de productos entre bandas y la inspección de calidad, a continuación exponemos algunas cosideraciones adicionales respecto a esos dos procesos.
### Inspección de Calidad 
Nuestros productos a diferencia otros no tiene grandes requrimientos mecanicos, sin embargo la parte estetica es muy importante dado que es la que mas se relaciona con la calidad en productos de este nicho. Sin embargo la estetica no es algo que se pueda medir facilmente y a su vez estas medidas no serian objetivas si no que dependerian de la persona en cuestion. Una posible opción es tener un personal capacitado para esta tarea, sin mebargo consideramos que otra solución mas adecuada, econoica y escalable es la implementación de un proceso robotizado basado en visión artificial. De esta manera podemos asegurar una metrica objetiva que ademas puede ser reprogramada segun requiera el usuario (cambios de color, textura, pieza, etc)

Por otro lado se tiene un proceso con bastantes factores variables, diferentes piezas, diferentes productos, posibilidad de diferentes colores. Esta información y variabilidad puede ser perfectamente procesada por un sistema robótico sin afectación alguna al proceso de producción. Esto sumado a que con estas implementaciones se eliminara el error humano en esta etapa contribuyendo a una mejor calidad global.

A si mismo es importante considerar el ritmo de producción que se tiene, pudiendo ser este variable consideramos que un sistema robotico podria responder de mejor manera estos cambios en volumen y velocidad de producción.
### Traslado de productos
Esta es una tarea sencilla pero altamente repetitiva y monotona, a su vez como en el caso de la isnpección de calidad esta sujeta a cambios en la velocidad y volumen de producción. Por ende se considera adecuada para automatización con robots, dado que la complejidad de su implementación seria baja y el operario podria ser mejor empleado en otras partes del proceso donde la automatización no sea viable y el trabajo manual sea estrictamente necesario.

