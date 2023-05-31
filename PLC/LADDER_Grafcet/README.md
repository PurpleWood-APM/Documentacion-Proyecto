# Control secuencial - Rutina Grafcet

Para realizar el grafcet, se identificaron los diferentes procesos automáticos secuenciales que se deben realizar, no es solo uno para toda la planta, ya que, se busca que cada proceso se realice en paralelo o que un proceos no depende 100% de la actuación de procesos posteriores. por ellos de dtermianron los siguientes procesos y etapas

1. Este proceso sería de fresado y cortado, donde un operario indicaría con tres botones que tipo de prodcuto quiere cortar, para pasar entre etapas es necesario que el controlador de la máuina cnc indique cuando termina la etapa de fresao y que pase automáticamente a la de corte. En este caso el operario coloca y quita la materia prima y los productos obtenidos
2. Banda transportadora: este proceos trasnladará los objetos ensamblados si detecta que se coloca uno al incio de la banda transportadora( al lado de la zona de ensamble) hasta que lleguen al final de la banda que se encuentra al lado de la zona de almacenamiento, en este momento se debera desactivar la banda
3. Pintado: en este, un operario, indicará cuando empezar la rutina de pintadoy sensores de paso determinarán por las diferentes alturas de los objetos que tipo de rutina empezar. Cuando el controlador del robot indique que se terinó la rutina se debe apagar la banda trasnportadora aerea y las salidas que indican la activación del robot.
4. Inspección: debe haber una banda transportadora que desplace los objetos o productos terminados hasta que una camra detecte si es un produto de buena calidad, si no lo es, un elemento deberá empujarlo sacarlo de la banda, para esta acción se puede usar un pistón neumático o eléctrico que realice la tarea de empujar los productos, claro este actuador deberá tner una pieza complementaria que aumente la superficie de contacto para realizar correctamente el empuje

Todos los procesos deberán tener su botón de emergencia, que pararán inmediatamente el proceso, en algunos casos también serán usados como forma de apagado, como en caso del proceso 4 que también será la forma de apagar la banda trasnportadora. 

Si entramos a mayor detalle a cada proceso:

## 1.#. Fresado y cortado: Proceso donde se realiza el corte de la materia prima dependiendo el tipo de producto.

  ### 1.#.0 Etapa de inicio: se verifica que las salidas del PLC que indican la activación de alguna secuencia en específico del PLC no estén prendidas
  
  - condición de paso de etapa: que se orpima el boton de inicio de proceso, en este caso sería tres, para cada tipo de producto que se quiere fabricar.
 
  ### 1.#.1. Activación de secuecnia cnc de fresado: al haber detectado el tipo de pieza producto que se quiere producir, se activa la salida del PLC principal que de paso a esta secuencia de Fresado
  
  - condición de paso de etapa: que se haga finalizado la secuencia de fresado

 ### 1.#.2 Activación de secuecnia cnc de corte: se desactivan las salidas de fresado y se activa la secuencia de corte del tipo de producto correspondiente
  
  -condición de paso de etapa: que se haya finalizado la secuenia de corte
  
  ### 1.#.3 Desactivación de secuencias: se desactivan todas las salidas que indqiuen el incio de una secuencia
  
  Se debe retornar a la condicón de paso de etapa entre la 1.#.0 y la 1.#.1
  
  
  
  
## 2.Banda Trasportadora a alamcen:

  ### 2.0 Etapa de inicio: se verifica que la salida del PLC que indican la activación de la banda trasnportadora no esté activada.
  
  - condición de paso de etapa: que se detecte un objeto en un sensor al incio de la banda trasnportadora.
 
  ### 2.1. Activación de la banda trasnportadora: se activa la banda trasnportadora 
  
  - condición de paso de etapa: que se detetcte un objeto en el sensor al final de la banda trasnportadora

 ### 2.2 desactivación banda trasnportadora: se desactivan la salidas que activa la banda trasnportadora 
  
  -condición de paso de etapa: que este desactivada la banda. 
  
  ### 2.3 Desactivación banda trasnportadora: se desactivan la salidas que activa la banda trasnportadora (esta etapa se usa para evitar errores lógicos en LADDER) 
  
  Se debe retornar a la condicón de paso de etapa entre la 2.0 y la 2.1
  
  
  
  ## 3.Pintado:

  ### 3.#.0 Etapa de inicio: se verifica que las salidas del PLC que indican la activación de una secuencia de pintado específica para cada tipo de producto del robot no estén activadas.
  
  - condición de paso de etapa: que se detecta si se oprime el botón de inicio de rutina de pintado y se detecta que tipo de producto es.
 
  ### 3.#.1. Activación del robot: se activa las salidas que indica que proceso de pintado usar y se activa la banda trasnportadora aerea que moverá la objetos
  
  - condición de paso de etapa: que se haya finalizado la rutina de pintado del robot

  ### 3.#.2 Desactivación de salidas : se desactivan la salidas que le idnican al robot que porceso realizar y se desactiva la banda trasnportadora aerea
  
  -condición de paso de etapa: que las salidas de la banda y hacia el robot estén desactivadas 
  
  ### 3.#.3 Desactivación de salidas: se desactivan la salidas que le idnican al robot que porceso realizar y se desactiva la banda trasnportadora aerea  (esta etapa se usa para evitar errores lógicos en LADDER) 
  
  Se debe retornar a la condicón de paso de etapa entre la 3.#.0 y la 3.#.1
  
  
  ## 4.Inspección:

  ### 4.0 Etapa de inicio: se verifica que la salida del PLC que indican la activación de la banda trasnportadora y el pistón neumático no estén activadas .
  
  - condición de paso de etapa: que oprima el botón de encendido de la banda.
 
  ### 4.1. Activación de la banda trasnportadora: se activa la banda trasnportadora 
  
  - condición de paso de etapa: que la camara detecte un producto defectuoso
 
  ### 4.2 Activación de pistón: se activa la salida que hará extender el psitón neumático
  
  -condición de paso de etapa: que hayan pasado .2s. 
  
  ### 4.3 Desactivación de pistón: se desactiva la salida del psitón, que haga retraer el pistón neumático
  
  -condición de paso de etapa: que el pistón esté retarido. 
  
  ### 4.4 Desactivación del pistón: se desactivan la salidas que extienden el psitón (esta etapa se usa para evitar errores lógicos en LADDER) 
  
  Se debe retornar a la condicón de paso de etapa entre la 4.1 y la 2.2
  
Visto con grafcet y con mejor nomenclatura de sensores y actuadroes tendríamos:

### Nomenclatura
![Nomenclatura](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/1789a19c-c1e5-4726-a26c-aacae056af56)

### Procesos
![Procesos](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/5d99e337-2cfe-4fe7-89ba-9663cc165df4)


### Proceso general
![Proceso general](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/3dab0e39-206b-4a6e-b38d-0ad092edb902)

### Lista entradas y salidas
![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/51938754/8f021268-1f00-4215-b0e5-d64a0ced4e90)

Si se desea ver el progama realizado en LADDER dirjase a [Código en ladder](https://github.com/PurpleWood-APM/DisenoDeProduccion) de nuestro repositorio complementario para archivos que puedan ser de gran tamaño. El proyecto en LADDER lo encontra´ra con el nombre ProyectoAPM.ADC
También puede ver las conexiones entre el plc, studio 5000 y demás softwares en el siguiente link: [Video de SCADA](https://www.youtube.com/watch?v=R3Ken7L0liA&t=3s)
