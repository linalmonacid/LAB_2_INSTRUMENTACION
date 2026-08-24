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
Para realizar la adquisición se utilizaron dos electrodos conectados a la piel del sujeto. Los electrodos disponibles contaban con cables y un conector que no podía introducirse directamente en la protoboard, por lo que se utilizó un adaptador. En las terminales de este adaptador se soldaron jumpers para facilitar la conexión de los electrodos con el circuito de adquisición. De esta manera fue posible conservar los cables originales de los electrodos y establecer una conexión más sencilla con los demás componentes del sistema.  

Debido a que uno de los requisitos de la práctica era desarrollar un dispositivo vestible que permitiera adquirir la GSR de manera continua, el montaje se adaptó a un guante. Para ello, se realizaron dos pequeños orificios en el material del guante justo en las posiciones correspondientes a los electrodos. Los electrodos se ubicaron a través de estos orificios de manera que su superficie permaneciera en contacto directo con la piel mientras el sujeto utilizaba el dispositivo. Esta configuración permitió mantenerlos en una posición más estable y disminuir desplazamientos durante las pruebas [1].  

El uso del guante también permitió que los electrodos permanecieran sujetos sin necesidad de que la persona los sostuviera manualmente. Esto fue importante para las pruebas en las que el sujeto debía moverse, escribir o realizar actividades cognitivas, ya que el sistema debía mantenerse funcionando durante estas tareas. Sin embargo, se consideró que los movimientos de la mano, cambios en la presión de los electrodos o alteraciones en el contacto entre estos y la piel podían generar variaciones adicionales en la señal adquirida.  

Para facilitar la movilidad del sistema se instaló además una correa ajustable alrededor de la muñeca. Sobre esta correa se dispuso la ESP32 junto con la batería encargada de alimentar el sistema. De esta manera, tanto la tarjeta de adquisición como su fuente de alimentación podían permanecer sujetas al brazo del participante, evitando la necesidad de mantener la ESP32 conectada físicamente al computador durante las pruebas.  

La alimentación mediante una batería permitió que el dispositivo funcionara de manera independiente después de ser programado. Al combinar el guante, los electrodos, la correa ajustable, la ESP32 y la batería se obtuvo un sistema portátil capaz de realizar la adquisición de la respuesta galvánica cutánea mientras el sujeto desarrollaba diferentes actividades. Posteriormente, la transmisión de la información mediante Wi-Fi permitió visualizar los datos desde otro dispositivo sin necesidad de una conexión alámbrica, completando así la característica vestible e inalámbrica propuesta en la guía [1].  


### Seguridad en el laboratorio
Antes de realizar las mediciones sobre el sujeto se verificó la corriente máxima que podía circular a través de la piel. La guía establece que para alimentaciones comprendidas entre 3.3 y 5 VDC debe garantizarse que la corriente a través del sujeto no supere 1 mA, considerando como condición extrema que la resistencia de la piel pueda aproximarse a un cortocircuito, es decir, Rskin = 0 Ω [1].  Para el circuito utilizado se consideró una alimentación máxima de 5 V y una resistencia en serie de 68 kΩ. La corriente que podría circular a través del paciente se determinó mediante la ley de Ohm:   

<img width="276" height="88" alt="image" src="https://github.com/user-attachments/assets/50e02b82-b4a0-4cb2-b0e0-e56585fcaa47" />  


Para analizar la condición más desfavorable se tomó Rskin = 0 Ω   

<img width="310" height="236" alt="image" src="https://github.com/user-attachments/assets/8f0b21e1-414d-4549-8206-573f2b958642" />  


Al convertir este resultado a miliamperios:  
<img width="244" height="158" alt="image" src="https://github.com/user-attachments/assets/fc30ef85-ae56-4e55-8742-492a5ff0717c" />  


Se comprobó que, incluso considerando el caso extremo planteado en la guía, la corriente máxima teórica que podría circular a través del sujeto se encontraba por debajo del límite establecido para la práctica [1]. Además, puede comprobarse cuál sería la resistencia mínima necesaria para limitar la corriente a 1 mA utilizando una alimentación de 5 V:   

<img width="265" height="128" alt="image" src="https://github.com/user-attachments/assets/f3b00fab-2d98-423a-9b97-e6c1388c9fc1" />  


Por lo tanto, la resistencia utilizada de 68 kΩ es considerablemente mayor que los 5 kΩ mínimos obtenidos bajo esta condición idealizada de cálculo, proporcionando una limitación de corriente adicional dentro del circuito.  


Posteriormente se construyó el circuito encargado de transformar los cambios en las propiedades eléctricas de la piel en variaciones de voltaje que pudieran ser adquiridas por la ESP32. Para el montaje se utilizó la resistencia de 68 kΩ anteriormente verificada y un condensador de 1 µF, componentes establecidos para el desarrollo de la práctica [1].  

La resistencia eléctrica de la piel hizo parte del circuito como un elemento variable. Debido a que esta propiedad cambia con la actividad electrodérmica, las modificaciones en Rskin producen también cambios en el voltaje presente en el nodo de medición. Este punto fue conectado a la entrada analógica de la ESP32 para realizar su conversión a un valor digital. El condensador de 1 µF se incorporó para disminuir variaciones rápidas presentes en la señal y contribuir a obtener una lectura más estable.  

Una vez comprobado el montaje, la salida del circuito se conectó al pin GPIO 34 de la ESP32. Este pin fue utilizado como entrada analógica para registrar las variaciones producidas por el circuito GSR. La tarjeta fue programada desde Arduino IDE y se configuró el convertidor analógico-digital con una resolución de 12 bits, permitiendo representar digitalmente las variaciones de voltaje adquiridas por el sistema.  







### Resultados


### Análisis de resultados



### Conclusiones


### Preguntas para la discusión



### Bibliografía

[1] W. Boucsein, *Electrodermal Activity*. Nueva York, NY, Estados Unidos: Springer Science & Business Media, 2012.

[2] M. L. Loggia, M. Juneau y C. M. Bushnell, “Autonomic responses to heat pain: Heart rate, skin conductance, and their relation to verbal ratings and stimulus intensity,” *Pain*, vol. 152, no. 3, pp. 592–598, 2011. https://doi.org/10.1016/j.pain.2010.11.032.

[3] M. Breimhorst, S. Sandrock, M. Fechir, N. Hausenblas, C. Geber y F. Birklein, “Do intensity ratings and skin conductance responses reliably discriminate between different stimulus intensities in experimentally induced pain?” *The Journal of Pain*, vol. 12, no. 1, pp. 61–70, 2011. https://doi.org/10.1016/j.jpain.2010.04.012.

[4] B. Figner y R. O. Murphy, “Using skin conductance in judgment and decision making research,” en *A Handbook of Process Tracing Methods for Decision Research*, M. Schulte-Mecklenbeck, A. Kuehberger y R. Ranyard, Eds. Nueva York, NY, Estados Unidos: Psychology Press, 2011, pp. 163–184.
