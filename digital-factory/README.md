# Explicación de la planta de NX
## Divisiones 
Visión generla de la planta 
La planta se divide en las siguientes zonas o procesos. 

![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/52113892/d23ec114-dd2e-46fd-9414-818275c2d7bb)

1. la zona de fresado y corte de materia prima.

![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/52113892/ba6cda8e-6aa3-438d-93f2-8a1d980d7046)

 Este proceso al ser automático, contará con 3 botones para indicar la rutina cnc que debe ejecutar la fresadora dependendiendo del tipo de producto que se quiera manufacturar. Además de tener entradas lógicas al plc principal que indique la finalización de la rutina de fresado y la de corte. También hay 6 salidas lógicas para indicar al controlador que proceso empezar, si el fresado de la pieza 1 o el corte del producto 3.
 
2. la zona de lijado y barnizado

![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/52113892/94145986-c817-433a-aa19-b228f1809b19)
 Esta zona no es automática y las bandas transportadoras que se encuentran en fresado y corte y lijado y banrnizado, no son automáticas, solo se uso su modelo pero están planaeadas como rodillos para deslizar el material\\
 
 3. la zona de ensamble

![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/52113892/d05ce2a1-2c4e-47fc-83ec-021e4b991895)

Esta zona no es automática, en este proceso se espera que un operario pegue o ensamble las piezas para armar un prodcuto.

4. Zona de transporte a almacen de secado

![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/52113892/f7283daf-4e72-474f-9f5c-42e423ffb9ae)

Esta zona cuenta con un actuador, que sería el motor que haga mover la banda, se esperararía que apesar del modelo mostrado sean varias bandas, que fuese una banda continua, la cual cuenta con dos sensores de paso, uno al incio de la banda ( al lado de la zona de ensamble) el cual indicaría la activación de la banda y trasnportará los productos ensamblados hasta el final de la banda, donde hay sensor de paso, el cual indicaría la desactivación o parada de la banda. 

5. Zona de almacenado de piezas ensambladas.

![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/52113892/8a3f49be-5c91-4063-90f2-eec632220bf6)

 Esta zona no es automática Por lo que no se identifican sensores o actuadores. 
 
 6. Zona de pintura
 
![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/52113892/980c5f4c-427a-4fbc-919e-4b3b492d4855)

Está zona automatizada cuenta con un robot y una banda transportadora aerea(no se cargó para mejorar el rendimiento de la planta, además las animaciones o sensores o el proceso a detalle se puede visualizar en el módulo de robótica)

7. Zona alamacen de elementos pintados

![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/52113892/b71cae6b-9092-4def-ba2f-0c1d36d69764)

Zona no automática, pero se espera que un usauario, recojas las piezas de la banda transportadora aerea y las traslade a este almacen, donde debe dejar las ´piezas colgando para su secado 

8. Zona de Inspección 

![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/52113892/4c667fee-95c0-4929-a06b-474d0abf9c2e)

Esta zona automática se esepera que un actuador lineal empuje los productos afuera de la banda si detetcta que el producto es defectuoso. Por lo que los actuadores que se identificaron fueron, el motor de la banda trasnportadora y el actuador lineal o pistón neumatico, además de contar con un botón que encenderá la banda indeifinidamente, hasta se oprima el botón de parada y una camara conectada a un modelo de inteligencía artificial para detectar productos defectuoso y accionar el pistón. 

9. Zona de empaquetado 

![image](https://github.com/PurpleWood-APM/Documentacion-Proyecto/assets/52113892/f1dddeac-613e-45ad-9c85-b3aa938a5cf2)

Esta zona no es automática y solo se realizará el empaquetado de los produtcos de buena calidad.

Si se desea ver las animaciones  o las conexiones con ignition y su relación con el PLC real, puede dirigirse a los siguientes dos videos:

[video planta NX](https://www.youtube.com/watch?v=FqLP5wtsmLo)

[video SCADA y Conexiones](https://www.youtube.com/watch?v=R3Ken7L0liA)
 
