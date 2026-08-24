# LAB_2_INSTRUMENTACION

### Integrantes

Lina María Cortes Almonacid

Karen Dayanna Mora Segura

Sofia Alejandra Cardona Cruz

### Introducción  

En esta práctica se desarrolló un sistema para adquirir y visualizar las variaciones de la respuesta galvánica cutánea o GSR de una persona, con el propósito de observar cambios en la actividad electrodérmica y utilizarlos como una aproximación al nivel de estrés. Para la adquisición se emplearon dos electrodos conectados a la piel mediante cables para electrodos y un adaptador, al cual se soldaron jumpers para facilitar su conexión con el circuito. La señal fue acondicionada mediante un circuito compuesto por una resistencia de 68 kΩ y un condensador de 1 µF y posteriormente adquirida mediante una tarjeta ESP32 [1].  

La actividad electrodérmica está relacionada con variaciones en las propiedades eléctricas de la piel, principalmente su conductancia, las cuales pueden modificarse debido a cambios en la actividad del sistema nervioso autónomo. Estas variaciones pueden aparecer frente a diferentes estímulos, como una inspiración profunda, cambios emocionales o situaciones que requieren concentración. Por esta razón, la GSR puede emplearse como un indicador indirecto de activación fisiológica relacionada con el estrés, aunque su interpretación debe realizarse teniendo en cuenta que diferentes estímulos pueden producir respuestas similares [2][3].  

Posteriormente, la ESP32 fue programada para adquirir la señal mediante una entrada analógica y crear su propia red Wi-Fi. Además, se implementó un servidor web que permitió consultar los valores registrados desde dispositivos conectados a dicha red. Finalmente, utilizando Thunkable se desarrolló una interfaz para recibir y visualizar inalámbricamente los datos tanto desde un computador como desde un teléfono celular. De esta manera, se obtuvo un sistema de monitoreo continuo que permitió integrar la adquisición de la GSR con herramientas de comunicación inalámbrica, siguiendo las etapas propuestas en la guía de laboratorio [1].  


### Objetivo General
Desarrollar un sistema de adquisición y monitoreo continuo de la respuesta galvánica cutánea mediante electrodos y una ESP32, capaz de transmitir inalámbricamente las variaciones registradas para analizar cambios relacionados con el nivel de estrés durante diferentes condiciones y tareas cognitivas.  



### Objetivos específicos
- Reconocer las variaciones estacionarias y transitorias presentes en la respuesta galvánica cutánea y su relación con la actividad electrodérmica.  
- Diseñar e implementar un circuito para adquirir las variaciones eléctricas de la piel mediante electrodos conectados a una ESP32. 
- Verificar que la corriente aplicada al sujeto se mantenga por debajo de 1 mA, de acuerdo con la condición de seguridad establecida para el desarrollo de la práctica. 
- Evaluar el comportamiento de la señal GSR durante condiciones de reposo, movimiento y respiración profunda.   
- Identificar valores de referencia que permitan establecer umbrales para diferenciar aproximadamente niveles de estrés bajo, moderado y elevado.  
- Implementar una comunicación inalámbrica entre la ESP32 y una aplicación desarrollada en Thunkable para visualizar la información desde un computador y un teléfono celular.  
- Analizar las variaciones de la GSR durante actividades que requieren concentración o esfuerzo mental y reconocer las limitaciones de emplear esta señal como indicador de estrés.  


### Metodología  
La práctica se desarrolló mediante la construcción de un sistema vestible para adquirir las variaciones de la respuesta galvánica cutánea de una persona y transmitir posteriormente la información de manera inalámbrica. Para ello se utilizaron dos electrodos, un circuito resistivo-capacitivo, una tarjeta ESP32, una batería para proporcionar alimentación independiente, un guante como soporte del sistema de medición y una interfaz desarrollada mediante Thunkable. El procedimiento se dividió en las etapas de revisión del principio fisiológico de la GSR, diseño del circuito, adaptación de los electrodos, construcción del sistema vestible, verificación de la seguridad eléctrica, adquisición analógica, programación de la ESP32, implementación de la comunicación Wi-Fi y visualización de los datos. Estas etapas se desarrollaron de acuerdo con la guía, en la cual se propone inicialmente adquirir la GSR en tiempo real y posteriormente utilizar sus variaciones para estimar diferentes niveles de estrés [1].

La respuesta galvánica cutánea forma parte de la actividad electrodérmica o EDA, término que comprende diferentes fenómenos eléctricos que se producen en la piel. Una de las principales variables relacionadas con esta actividad es la conductancia cutánea, la cual puede modificarse como consecuencia de cambios en la actividad de las glándulas sudoríparas controladas principalmente por el sistema nervioso simpático [2]. Por esta razón, distintos estímulos pueden producir modificaciones detectables en las propiedades eléctricas de la piel.

Dentro de la actividad electrodérmica pueden distinguirse una componente relativamente estable y una componente transitoria. El nivel de conductancia cutánea o SCL representa el nivel basal de la señal durante un determinado intervalo, mientras que las respuestas de conductancia cutánea o SCR corresponden a cambios que aparecen frente a determinados estímulos. Estas respuestas generalmente presentan un incremento relativamente rápido y posteriormente una recuperación más lenta hacia su condición inicial [2].

Para adquirir estas variaciones se utilizaron dos electrodos conectados a la piel. Debido a que los cables de los electrodos contaban con un conector que no podía introducirse directamente en la protoboard, se consiguió un adaptador compatible y sobre sus terminales se soldaron jumpers. De esta manera fue posible conectar los electrodos con el circuito de adquisición sin modificar directamente sus cables originales.

Con el propósito de convertir el montaje en un sistema vestible, se utilizó un guante como soporte para los electrodos. Sobre la zona correspondiente a la palma de la mano se realizaron dos pequeños orificios, ubicados de manera que cada electrodo pudiera atravesar el material y mantener contacto directo con la piel del sujeto. De esta forma, los electrodos permanecieron ubicados aproximadamente en la misma posición durante las pruebas y no fue necesario que el participante los sostuviera manualmente.

La selección de la palma de la mano permitió establecer un contacto directo entre los electrodos y la superficie cutánea. Sin embargo, durante las pruebas también se tuvo en cuenta que los movimientos de la mano, los cambios en la presión ejercida sobre los electrodos, el desplazamiento de los cables o las variaciones en el contacto electrodo-piel podían modificar las lecturas. Esto resulta especialmente importante debido a que la guía propone evaluar el comportamiento del dispositivo mientras el sujeto se mueve, camina o realiza actividades como escribir, con el propósito de reconocer posibles interferencias asociadas con el movimiento [1].

Para facilitar la movilidad del sistema se agregó una correa ajustable alrededor de la muñeca. Sobre esta correa se ubicó la ESP32, permitiendo mantener la tarjeta sujeta al brazo mientras el participante realizaba las diferentes pruebas. También se planteó ubicar en la misma correa la batería utilizada para alimentar la ESP32, haciendo posible que el sistema funcionara de manera independiente después de haber sido programado y sin requerir una conexión permanente al puerto USB del computador.

De esta manera, el sistema vestible quedó constituido principalmente por el guante con los dos electrodos en contacto con la palma de la mano, los cables de conexión, el adaptador con los jumpers soldados, el circuito de adquisición, la ESP32 ubicada sobre la muñeca y la batería encargada de proporcionar la alimentación. Esta distribución permitió que el participante pudiera utilizar el sistema mientras realizaba diferentes actividades y cumplió con el propósito de construir un dispositivo capaz de capturar continuamente las variaciones de la GSR [1].

Antes de realizar las mediciones sobre el sujeto se verificó la corriente máxima que podía circular a través de la piel. La guía establece que para alimentaciones comprendidas entre 3.3 y 5 VDC debe garantizarse que la corriente a través del sujeto no supere 1 mA, considerando como condición extrema que la resistencia de la piel pueda aproximarse a un cortocircuito, es decir, Rskin = 0 Ω [1].  Para el circuito utilizado se consideró una alimentación máxima de 5 V y una resistencia en serie de 68 kΩ. La corriente que podría circular a través del paciente se determinó mediante la ley de Ohm:   

<p align="center">
  <img src=https://github.com/user-attachments/assets/50e02b82-b4a0-4cb2-b0e0-e56585fcaa47 width="500">
</p>

<img width="276" height="88" alt="image" src="https://github.com/user-attachments/assets/50e02b82-b4a0-4cb2-b0e0-e56585fcaa47" />  


Para analizar la condición más desfavorable se tomó Rskin = 0 Ω   


<img width="310" height="236" alt="image" src="https://github.com/user-attachments/assets/8f0b21e1-414d-4549-8206-573f2b958642" />  


Al convertir este resultado a miliamperios:  


<img width="244" height="158" alt="image" src="https://github.com/user-attachments/assets/fc30ef85-ae56-4e55-8742-492a5ff0717c" />  


Se comprobó que, incluso considerando el caso extremo planteado en la guía, la corriente máxima teórica que podría circular a través del sujeto se encontraba por debajo del límite establecido para la práctica [1]. Además, puede comprobarse cuál sería la resistencia mínima necesaria para limitar la corriente a 1 mA utilizando una alimentación de 5 V:   
<p align="center">
<b>Figura 1.</b> Señal respiratoria obtenida durante la respiración en reposo.
</p>

<img width="265" height="128" alt="image" src="https://github.com/user-attachments/assets/f3b00fab-2d98-423a-9b97-e6c1388c9fc1" />  


La resistencia utilizada experimentalmente fue de 68 kΩ, considerablemente mayor que los 5 kΩ obtenidos para esta condición límite. Por esta razón, la resistencia seleccionada permitió mantener la corriente teórica por debajo del valor máximo planteado en la guía.  

Una vez construido y verificado el circuito, el punto de adquisición se conectó al pin GPIO 34 de la ESP32. Este pin fue utilizado como entrada analógica para registrar las variaciones generadas por el circuito GSR. La tarjeta se programó mediante Arduino IDE y en el código se configuró el convertidor analógico-digital con una resolución de 12 bits mediante la instrucción analogReadResolution(12).  

Por esta razón, las lecturas realizadas por la ESP32 mediante analogRead() se representaron digitalmente dentro del rango correspondiente al convertidor. Es importante tener en cuenta que el número obtenido no representa directamente una medida de conductancia expresada en siemens. Corresponde inicialmente a la conversión digital del voltaje presente en el pin GPIO 34, el cual depende del comportamiento del circuito y de las propiedades eléctricas de la piel. Por esta razón, durante la práctica los valores fueron utilizados principalmente para identificar variaciones relativas en la GSR.  

La comunicación serial fue configurada a una velocidad de 115200 baudios. Inicialmente, esta comunicación se utilizó para verificar el funcionamiento del montaje mediante el monitor serial de Arduino IDE. Durante la ejecución del programa, la ESP32 realizó una lectura periódica del GPIO 34 y mostró información de la forma GSR = valor  

Las lecturas se realizaron aproximadamente cada 500 ms, debido al tiempo de espera definido dentro del ciclo principal del programa. Esto permitió observar continuamente los cambios producidos en la señal y comprobar que los electrodos, el circuito y la entrada analógica estuvieran funcionando antes de implementar la comunicación inalámbrica.  

Posteriormente se evaluó el comportamiento de la señal GSR en diferentes condiciones. Inicialmente se observaron los valores mientras el sujeto se encontraba en reposo y también durante algunos movimientos. Esta prueba permitió identificar variaciones producidas no solamente por respuestas fisiológicas, sino también por modificaciones en el contacto entre los electrodos y la piel, movimiento de los cables y presión ejercida sobre la palma de la mano.  

Después se realizó la prueba de respiración profunda propuesta en la guía. Para ello, el sujeto permaneció cómodamente sentado y en reposo y posteriormente realizó una inspiración profunda seguida de una exhalación lenta. Este tipo de estímulo puede provocar una modificación de la actividad electrodérmica y generar una respuesta observable en la GSR [1][2].  

De acuerdo con el comportamiento descrito para las respuestas de conductancia cutánea, después del estímulo puede presentarse un aumento de la respuesta seguido de una recuperación progresiva hacia su condición inicial [2]. Durante esta prueba se observaron las variaciones obtenidas y se tomaron como referencia los valores mínimos y máximos registrados. Según el procedimiento planteado en la guía, estos valores permiten establecer posteriormente umbrales correspondientes a poco estrés, estrés moderado y estrés elevado [1].  

Los límites correspondientes a estos niveles no deben considerarse valores universales, ya que la actividad electrodérmica puede variar entre individuos e incluso en un mismo sujeto dependiendo de las condiciones de medición. Por esta razón, los rangos utilizados para la clasificación deben establecerse a partir de los valores obtenidos experimentalmente durante las pruebas y no únicamente mediante valores predeterminados [2].  

Una vez comprobada la adquisición de la GSR se realizó la adaptación necesaria para transmitir la información de manera inalámbrica. Para ello se utilizaron las capacidades Wi-Fi integradas en la ESP32 y las librerías WiFi.h y WebServer.h. La tarjeta fue configurada en modo de punto de acceso, permitiendo crear una red inalámbrica propia sin depender de la conexión Wi-Fi disponible en el laboratorio.  

La red creada por la ESP32 se configuró con el nombre ESP32_GSR y se estableció una contraseña dentro del programa. El teléfono celular y el computador utilizados durante las pruebas se conectaron directamente a esta red para establecer comunicación con la ESP32.  

Al iniciar el punto de acceso, la ESP32 utilizó durante las pruebas la dirección IP:  

192.168.4.1 

Posteriormente se inició un servidor web en el puerto 80 mediante la librería WebServer. En el programa se implementaron dos rutas principales. La primera correspondió a la dirección raíz /, desde la cual se podía acceder mediante un navegador a una página denominada Monitor GSR. En esta página se mostraba el valor adquirido por la ESP32 y se configuró una actualización automática periódica para facilitar su visualización.  

La segunda ruta se denominó /datos por lo que podía consultarse mediante la dirección:

http://192.168.4.1/datos

Cada vez que un dispositivo realizaba una solicitud a esta dirección, la ESP32 efectuaba una nueva lectura del GPIO 34 y construía una respuesta en formato JSON. El uso de JSON permitió transmitir únicamente el dato necesario e identificarlo mediante la propiedad gsr, facilitando posteriormente su procesamiento desde la aplicación.  

Para visualizar inalámbricamente la información se utilizó la plataforma Thunkable. Dentro de la aplicación se incorporaron un temporizador, un componente Web API y un elemento de texto destinado a mostrar el valor recibido. El temporizador se utilizó para realizar consultas periódicas al servidor de la ESP32 y actualizar la información presentada al usuario.  
 
Cuando se activaba el temporizador, el componente Web API realizaba una solicitud GET hacia la ruta /datos. Si la solicitud se realizaba correctamente, la aplicación recibía la respuesta JSON generada por la ESP32. Esta respuesta era convertida nuevamente en un objeto, del cual se obtenía la propiedad gsr. Finalmente, el valor extraído era asignado al elemento de texto de la interfaz.  

La cadena completa de adquisición y transmisión implementada durante la práctica puede resumirse de la siguiente manera:  

Palma de la mano → electrodos → adaptador con jumpers → circuito GSR → GPIO 34 de la ESP32 → conversión ADC → servidor web → Wi-Fi → Web API → Thunkable → computador/celular.  

La aplicación fue utilizada tanto desde el computador como desde un teléfono celular conectado a la red creada por la ESP32. Con esto se comprobó que la lectura obtenida mediante los electrodos podía ser adquirida, procesada y consultada inalámbricamente, sin necesidad de mantener una conexión física entre la ESP32 y el dispositivo encargado de mostrar la información.  

La alimentación mediante batería y la disposición de la ESP32 sobre la correa ajustable de la muñeca permitieron complementar esta comunicación inalámbrica y convertir el montaje en un sistema con mayor movilidad. De esta manera, el sujeto podía portar el guante y la electrónica mientras realizaba las actividades establecidas, mientras que los datos podían observarse desde otro dispositivo ubicado a cierta distancia.  

Finalmente, los valores obtenidos mediante la GSR se utilizaron como base para plantear una clasificación del nivel de estrés. Una vez determinados experimentalmente los valores mínimo y máximo y definidos los correspondientes umbrales, las lecturas pueden clasificarse aproximadamente como estrés bajo, estrés moderado o estrés elevado. Esta clasificación permite transformar el valor numérico obtenido por el ADC en información más sencilla de interpretar por el usuario. La guía establece que, en la etapa de transmisión inalámbrica, el sistema debe evolucionar desde la visualización de la señal hacia la presentación de un mensaje o alerta correspondiente al nivel de estrés estimado [1].  

La etapa final de la práctica contempla utilizar el dispositivo mientras el sujeto resuelve un breve examen o diferentes problemas que requieran concentración y esfuerzo mental. Durante esta prueba, el sistema vestible debe continuar adquiriendo la GSR y transmitiendo inalámbricamente la información. Posteriormente, los cambios registrados pueden compararse con el comportamiento observado en reposo para determinar si durante la actividad cognitiva se produjeron variaciones detectables en la respuesta galvánica cutánea [1].  

Sin embargo, la interpretación de estas variaciones debe realizarse con precaución. La GSR refleja modificaciones de la actividad electrodérmica y de la activación autonómica, pero no responde exclusivamente al estrés. Una respiración profunda, estímulos térmicos, dolor, emociones y otras condiciones también pueden producir modificaciones en la conductancia de la piel [2][3][4]. Por esta razón, el sistema desarrollado permite realizar una estimación del nivel de activación fisiológica asociada al estrés, pero una lectura aislada de GSR no permite determinar de manera absoluta el estado emocional de una persona.  







### Resultados


### Análisis de resultados



### Conclusiones


### Preguntas para la discusión



### Bibliografía  

[1] Universidad Militar Nueva Granada. (2025). Guía de preparación práctica de laboratorio: Estimación del nivel de estrés basada en la respuesta galvánica cutánea (GSR). Laboratorio de Instrumentación Biomédica y Biosensores, Programa de Ingeniería Biomédica. 
Guía de laboratorio

[2] Boucsein, W. (2012). Electrodermal activity (2nd ed.). Springer Science & Business Media.
https://doi.org/10.1007/978-1-4614-1126-0

[3] Loggia, M. L., Juneau, M., & Bushnell, M. C. (2011). Autonomic responses to heat pain: Heart rate, skin conductance, and their relation to verbal ratings and stimulus intensity. Pain, 152(3), 592–598.
https://doi.org/10.1016/j.pain.2010.11.032

[4] Breimhorst, M., Sandrock, S., Fechir, M., Hausenblas, N., Geber, C., & Birklein, F. (2011). Do intensity ratings and skin conductance responses reliably discriminate between different stimulus intensities in experimentally induced pain? The Journal of Pain, 12(1), 61–70.
https://doi.org/10.1016/j.jpain.2010.04.012
