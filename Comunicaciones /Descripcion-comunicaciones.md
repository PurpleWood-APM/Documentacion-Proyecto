## Comunicaciones utilizadas en el proyecto de automatización

Para el proyecto de plante el uso de diferentes comunicaciones para interconectar los dispositivos, sensores, actuadores y sistemas involucrados. A continuación, presentamos una breve descripción de estas comunicaciones, incluyendo los protocolos, canales y el nivel de la pirámide de automatización donde se utilizan.

### Comunicación de PLC con  Dispositivos/Sensores/Actuadores (Dispositvos y sensores de proceso)
- **Protocolo:** Se planea el uso de Profibus 
- **Canales:** La conexión física entre el PLC y los dispositivos se realizara con cables Ethernet. Sin embargo cabe mencionar que en algunos casos, se pueden requerir cables específicos o adaptadores según indique el dispositivo.
- **Niveles de la pirámide de automatización:** Esta comunicación ocurre a nivel de campo, donde se encuentran los sensores y actuadores. estableciendo asi una comunicación entre el nivel de control (PLC) y el nivel de campo (dispositivos/sensores/actuadores).

### Comunicación PLC - CNC (Corte y fresado de piezas)
- **Protocolo:** Dado que no se realiza la selección final de la maquina se desconoce el protocolo o esquema de comunicaciones requerido por el fabricante, sin embargo se consideran distintos protocolos como FANUC, Mazatrol o Heidenhain.
- **Canales:** Se plantea que la conexión entre el PLC y el CNC se realize a través de cables Ethernet o cables específicos adaptados al protocolo y la interfaz del CNC.
- **Niveles de la pirámide de automatización:** Esta comunicación ocurre entre el nivel de campo (CNC) y el nivel de control (PLC)

### Comunicación PLC - Celda Robotica (Proceso de Pintado)
- **Protocolo:** El protocolo dependera de lo indicado por el fabricante, sin embargo esta información no fue encontrada en la ficha tecnica, sin embargo se espera que el protocolo empleado pueda ser Profibus.
- **Canales:** Se emplean cables Ethernet o adaptadores específicos para conectar el PLC y el robot y su controlador.
- **Niveles de la pirámide de automatización:** La comunicación se establece entre el nivel de control (PLC) y el nivel de ejecución (manipulador - controlador) en el nivel inferior de la pirámide de automatización.

### Comunicación PLC - Sistema de control de calidad (Bandas, pistones)
- **Protocolo:** Para este caso nuevamente emprearemos profibus para y asi mismo señales digitales para enviar señales a los actuadores y capturar información de los sensores. 
- **Canales:** La conexión se realizara a través de cables Ethernet y asi mismo cables de poder para el envio de las señales digitales.
- **Niveles de la pirámide de automatización:** Esta comunicación se produce entre el nivel de control (PLC) y el nivel de campo.

### Monitoreo y visualización en la nube mediante dashboards
- **Protocolo:** Para la conexión con ignition usamos  el protocolo MQtt
- **Canales:** Se utiliza Internet a través de cables Ethernet para el envio de la información a ignition
- **Niveles de la pirámide de automatización:** La comunicación se realiza desde el nivel de control (PLC) hasta el nivel de supervisión.

### Conexión Gemelo Digital
- **Protocolo:** Para la conexión con entre ignition y Studio 5000 usamos el protocolo OPC
- **Canales:** Repecto a los canales usamos conexi
- **Niveles de la pirámide de automatización:** La comunicación se realiza entre el nivel de supervisión y el de planeación, siendo esta una de las finalides del gemelo digital implementado.

### Respecto a la elección de Profibus
Se opta por usar este protocolo en el nivel de campo teniendo en cuenta las siguientes razones:

- Amplia adopción en la industria: PROFIBUS es uno de los protocolos de comunicación más comunes en entornos industriales. Es compatible con una amplia gama de dispositivos de campo y ha sido ampliamente utilizado en diferentes sectores industriales, lo que facilita la integracions de nuevos dispositivos o la realización de ajustes en el proyecto.

- Velocidad de transmisión: PROFIBUS ofrece diferentes velocidades de transmisión, como PROFIBUS DP (Decentralized Periphery) para la comunicación entre el PLC y los dispositivos de campo y PROFIBUS PA (Process Automation) para aplicaciones de proceso. Esto permite adaptar la velocidad de comunicación según se requiera , lo que puede ser beneficioso para garantizar una transmisión eficiente de datos en tiempo real teniendo en cuenta el trabajo con el gemelo digital.

- Robustez y confiabilidad: PROFIBUS se ha desarrollado para soportar entornos industriales exigentes, lo que garantiza su robustez y confiabilidad. Está diseñado para resistir interferencias electromagnéticas y ruidos, lo que es adecuado para nuestro entorno de producción dada la existencia de distintas fuentes de interferencias, como los motores y maquinaria usada en nuestro proceso productivo.

- Integración de diagnósticos y control de calidad: PROFIBUS proporciona funciones de diagnóstico avanzadas, lo que permite supervisar y realizar un efectivo. Esto nos permite saber el estado de los dispositivos de campo, detectar errores y realizar un mantenimiento predictivo, garantizando la continuidad del proceso y disminuyendo los riesgos.

- Soporte de fabricantes: PROFIBUS cuenta con el respaldo de numerosos fabricantes de dispositivos y sistemas, lo que garantiza una amplia disponibilidad de productos, servicios y documentacion. Esto hace que  la integración de fututos dispositivos y la obtención de soporte técnico sea mas sencilla.
