# LAB_2_INSTRUMENTACION

### Integrantes

Lina María Cortes Almonacid

Karen Dayanna Mora Segura

Sofia Alejandra Cardona Cruz

### Introducción

En esta práctica se desarrolló un sistema para la adquisición y monitoreo de la respuesta galvánica cutánea (GSR), con el propósito de analizar las variaciones de la conductancia eléctrica de la piel asociadas a diferentes estímulos y tareas que demandan esfuerzo mental. La actividad electrodérmica o EDA comprende los fenómenos eléctricos que ocurren en la piel y está relacionada con cambios en su capacidad para conducir corriente eléctrica. Dentro de esta respuesta se pueden identificar un nivel basal o componente estacionario y variaciones transitorias denominadas respuestas de conductancia cutánea (SCR) [1]. La guía establece que estos cambios pueden presentarse ante diferentes estímulos, incluyendo modificaciones en la respiración, estímulos térmicos y estímulos mecánicos [1].

El sistema desarrollado permitió adquirir la señal GSR de manera continua mediante electrodos ubicados sobre la piel y procesar los datos obtenidos para observar su comportamiento en tiempo real. La práctica también permitió estudiar la respuesta de la piel ante una inspiración profunda y posteriormente durante actividades que demandan concentración y esfuerzo mental. De acuerdo con la guía, una inspiración profunda puede generar un incremento considerable de la respuesta galvánica cutánea, seguido de un retorno progresivo hacia el nivel inicial [1].

Además de la adquisición de la señal, se planteó el desarrollo de un dispositivo vestible capaz de realizar el monitoreo continuo y transmitir la información a un computador. Posteriormente, el sistema debía adaptarse para realizar una transmisión inalámbrica y mostrar un indicador o mensaje relacionado con el nivel de estrés estimado. De esta manera, la práctica permitió relacionar conceptos de instrumentación biomédica, adquisición de señales fisiológicas, sistemas embebidos y procesamiento de señales con el análisis de una respuesta fisiológica del sistema nervioso autónomo.

### Objetivo General

Desarrollar un sistema de medición continua basado en la respuesta galvánica cutánea (GSR) que permita estimar los cambios asociados al nivel de estrés de una persona durante diferentes condiciones y tareas cognitivas.

### Objetivos específicos

* Identificar las componentes estacionaria y transitoria presentes en la respuesta galvánica cutánea.
* Diseñar e implementar un dispositivo vestible capaz de capturar de forma continua las variaciones de la GSR.
* Seleccionar una ubicación adecuada para los electrodos con el propósito de obtener la señal con la menor cantidad posible de interferencias.
* Adquirir y visualizar la señal GSR en tiempo real durante condiciones de reposo y durante diferentes actividades.
* Analizar la respuesta de la GSR ante una inspiración profunda y durante tareas que requieren concentración y esfuerzo mental.
* Establecer umbrales que permitan diferenciar niveles bajo, moderado y elevado a partir de los valores obtenidos durante las pruebas.
* Adaptar el sistema para realizar la transmisión inalámbrica de la información hacia un computador o dispositivo móvil.
* Plantear posibles explicaciones fisiológicas para los cambios observados en la señal GSR.

### Metodología

La práctica se desarrolló mediante la construcción de un sistema capaz de adquirir y monitorear continuamente la respuesta galvánica cutánea de una persona. El procedimiento se dividió en diferentes etapas que comprendieron la revisión teórica de la actividad electrodérmica, el diseño del circuito de adquisición, la selección de la ubicación de los electrodos, la adquisición y visualización de la señal, el análisis de la respuesta ante diferentes estímulos y la adaptación del sistema para realizar transmisión inalámbrica.

Inicialmente, se realizó una revisión sobre la actividad electrodérmica (EDA) y la respuesta galvánica cutánea (GSR). La conductancia de la piel puede presentar variaciones ante diferentes estímulos fisiológicos y ambientales. En la señal se pueden distinguir una componente estacionaria correspondiente al nivel basal de conductancia y una componente transitoria asociada a cambios rápidos de la respuesta. Estas variaciones constituyen la base para analizar la respuesta fisiológica durante la práctica [1].

Posteriormente, se diseñó el circuito para realizar la medición de la conductancia de la piel. La guía establece que el sistema debía utilizar una alimentación entre +3,3 V y +5 VDC y que se debían realizar los cálculos necesarios para garantizar que, incluso en una condición extrema en la que la resistencia de la piel fuera equivalente a un cortocircuito, la corriente que circulara por el sujeto no superara 1 mA. Este cálculo permitió establecer condiciones de operación seguras para el dispositivo antes de realizar las pruebas sobre una persona.

Para la adquisición de la señal se utilizaron electrodos en contacto con la piel. La guía contempla el uso de electrodos Ag-AgCl o, alternativamente, placas metálicas de acero inoxidable, aluminio u otro material que no reaccione con el sudor corporal. La ubicación de los electrodos se seleccionó buscando obtener una señal con la menor interferencia posible y permitir que el dispositivo pudiera utilizarse de manera cómoda como un sistema vestible.

El sistema de adquisición se conectó a un dispositivo embebido encargado de recibir la señal proveniente del circuito. Para la práctica, la guía contempla el uso de un Arduino UNO o Nano, junto con una protoboard, cables, una resistencia de 68 kΩ y un condensador de 1 µF. La información adquirida debía ser enviada de forma alámbrica a un computador para visualizar la señal en tiempo real.

Antes de realizar las mediciones sobre el sujeto de prueba, se verificó el funcionamiento del circuito y las condiciones de seguridad. Se revisaron los valores de alimentación y se comprobó que la corriente aplicada al sujeto se encontrara dentro del límite establecido por la guía. También se verificó que los electrodos estuvieran correctamente ubicados y sujetos para reducir movimientos y posibles interferencias durante la adquisición.

Una vez puesto en funcionamiento el sistema, se realizó una primera prueba con el sujeto en reposo y cómodamente sentado. Se solicitó realizar una inspiración profunda y posteriormente una exhalación lenta. De acuerdo con la guía, durante esta prueba se esperaba observar un incremento considerable de la GSR seguido de un retorno progresivo hacia el valor inicial. A partir de los valores máximo y mínimo registrados se podían establecer posteriormente los umbrales utilizados para diferenciar los niveles de estrés.

Después se evaluó el comportamiento del dispositivo mientras el sujeto realizaba diferentes actividades. La guía plantea observar el sistema durante movimientos, caminata o tareas como escribir, con el propósito de identificar posibles interferencias producidas por el movimiento. Posteriormente, el sujeto debía realizar tareas cognitivas que demandaran concentración y esfuerzo mental mientras utilizaba el dispositivo vestible. Durante esta etapa se registraron las variaciones de la GSR para analizar su comportamiento frente a la demanda mental.

Finalmente, se realizó la adaptación del sistema para transmitir los datos de manera inalámbrica hacia un computador o, incluso, hacia un teléfono celular. En esta etapa, el objetivo no era únicamente visualizar la señal GSR, sino utilizar la información obtenida para generar un mensaje o alerta que indicara el nivel de estrés estimado del sujeto.

### Materiales, instrumentos y equipos

Para el desarrollo de la práctica se utilizaron los elementos establecidos en la guía de laboratorio:

* Computador con acceso a Internet.
* MATLAB.
* Arduino UNO o Nano.
* Protoboard.
* Cables UTP.
* Resistencia de 68 kΩ.
* Condensador de 1 µF.
* Dos electrodos Ag-AgCl o placas metálicas adecuadas.
* Cintas de velcro.
* Fuente de alimentación.
* Equipos de medición disponibles en el laboratorio.

### Seguridad en el laboratorio

Antes de iniciar la práctica se verificaron las condiciones eléctricas de los elementos utilizados y los valores de alimentación del circuito. Debido a que los electrodos se encuentran en contacto directo con la piel del sujeto, se tuvo especial cuidado con el nivel de corriente aplicado. La guía establece que la corriente que circule por el sujeto debe mantenerse por debajo de 1 mA, incluso considerando una condición extrema de resistencia de piel igual a cero.

También se utilizaron responsablemente los elementos de protección personal y se verificó que los equipos estuvieran correctamente conectados antes de realizar las mediciones. Durante la adquisición se procuró mantener los electrodos correctamente sujetos para evitar movimientos bruscos que pudieran afectar la señal.

### Resultados

Durante la práctica se obtuvo la señal correspondiente a la respuesta galvánica cutánea del sujeto de prueba. Inicialmente se observó el comportamiento de la señal en reposo y posteriormente se registraron sus variaciones durante la realización de diferentes actividades.

En la prueba de inspiración profunda y exhalación lenta se esperaba identificar un aumento de la conductancia cutánea seguido de un descenso progresivo hacia el nivel basal. Este comportamiento permitió reconocer la componente transitoria de la GSR respecto al nivel estacionario de la señal.

Durante las actividades que implicaron movimiento y tareas cognitivas se observaron variaciones adicionales en la señal. Los movimientos del sujeto podían introducir interferencias, por lo que fue necesario considerar la estabilidad de los electrodos y las condiciones de adquisición al interpretar los resultados.

A partir de los valores registrados se establecieron los límites utilizados para clasificar la respuesta en diferentes niveles de estrés. Posteriormente, estos niveles fueron utilizados como referencia para la etapa de transmisión inalámbrica y generación del mensaje o indicador correspondiente.

### Análisis de resultados

El sistema desarrollado permitió observar que la respuesta galvánica cutánea presenta variaciones frente a diferentes estímulos. La identificación de una componente basal y de cambios transitorios permitió diferenciar el nivel general de conductancia de las respuestas producidas ante determinados estímulos.

La prueba de inspiración profunda permitió evidenciar que la GSR puede modificarse incluso ante una respuesta fisiológica que no necesariamente corresponde a una situación de estrés. Esto es importante porque demuestra que la señal no debe interpretarse de manera aislada como una medida directa de estrés. La propia guía señala que la conductancia cutánea puede aumentar ante estímulos como una respiración profunda, estímulos térmicos o estímulos mecánicos.

Por otra parte, durante las tareas cognitivas se analizaron las variaciones de la señal con respecto al comportamiento observado en reposo. El esfuerzo mental puede generar cambios en la respuesta autonómica, pero factores como el movimiento, la posición de los electrodos, el contacto con la piel y las condiciones ambientales también pueden modificar la señal. Por esta razón, la GSR debe considerarse como un indicador fisiológico que requiere contextualización y no como una medición directa y exclusiva del estrés.

Una de las principales limitaciones identificadas corresponde a la sensibilidad de la señal frente a interferencias producidas por movimiento. Por esta razón, la correcta selección y fijación de los electrodos resulta fundamental para obtener registros confiables. Asimismo, la ubicación anatómica de los electrodos debe seleccionarse buscando minimizar las interferencias y mejorar la calidad de la adquisición.

La implementación de la transmisión inalámbrica permitió plantear una aplicación más cercana a un sistema vestible de monitoreo continuo. En lugar de limitarse a observar directamente la señal, el sistema puede utilizar los valores obtenidos para generar una clasificación o alerta relacionada con el nivel de respuesta estimado.

### Conclusiones

La práctica permitió desarrollar y analizar un sistema de adquisición basado en la respuesta galvánica cutánea, identificando las componentes estacionaria y transitoria presentes en la señal. Se comprobó la utilidad de la GSR como indicador de cambios fisiológicos relacionados con diferentes estímulos y actividades.

La prueba de inspiración profunda permitió observar que la conductancia cutánea puede presentar cambios importantes ante estímulos fisiológicos, mientras que las actividades cognitivas permitieron analizar el comportamiento de la señal durante situaciones que demandan concentración y esfuerzo mental.

También se evidenció la importancia de una adecuada selección y fijación de los electrodos, debido a que los movimientos y otras interferencias pueden modificar la señal registrada. Por esta razón, el diseño de un sistema vestible debe considerar tanto la adquisición de la señal como la comodidad y estabilidad del dispositivo.

Finalmente, la adaptación del sistema para transmisión inalámbrica permitió plantear una solución de monitoreo continuo capaz de transformar los datos fisiológicos adquiridos en información más sencilla de interpretar, como un nivel o alerta de estrés. Sin embargo, la respuesta galvánica cutánea debe interpretarse con precaución, debido a que diferentes estímulos fisiológicos y ambientales pueden producir cambios similares en la señal.

### Preguntas para la discusión

**1. ¿A qué se debe que una inspiración profunda incremente la magnitud de la respuesta galvánica cutánea (GSR)?**

Una inspiración profunda puede generar cambios en la actividad del sistema nervioso autónomo, produciendo modificaciones en la actividad de las glándulas sudoríparas y, por lo tanto, en la conductancia eléctrica de la piel. Por esta razón, la GSR puede aumentar durante este tipo de estímulo y posteriormente regresar de manera progresiva hacia su nivel inicial. La guía utiliza precisamente esta respuesta como una de las pruebas de la práctica.

**2. ¿Cuáles serían las ventajas y desventajas de utilizar la GSR como indicador de estrés?**

Una ventaja es que permite realizar una medición continua y relativamente sencilla de una respuesta fisiológica relacionada con la actividad del sistema nervioso autónomo. Además, puede integrarse en dispositivos vestibles para realizar monitoreo durante diferentes actividades.

Como desventaja, la GSR no es exclusiva del estrés, debido a que puede modificarse ante otros estímulos como cambios respiratorios, estímulos térmicos, estímulos mecánicos y movimientos. Por esta razón, sus resultados deben interpretarse teniendo en cuenta las condiciones en las que se realizó la medición.

### Bibliografía

[1] W. Boucsein, *Electrodermal Activity*. Nueva York, NY, Estados Unidos: Springer Science & Business Media, 2012.

[2] M. L. Loggia, M. Juneau y C. M. Bushnell, “Autonomic responses to heat pain: Heart rate, skin conductance, and their relation to verbal ratings and stimulus intensity,” *Pain*, vol. 152, no. 3, pp. 592–598, 2011. https://doi.org/10.1016/j.pain.2010.11.032.

[3] M. Breimhorst, S. Sandrock, M. Fechir, N. Hausenblas, C. Geber y F. Birklein, “Do intensity ratings and skin conductance responses reliably discriminate between different stimulus intensities in experimentally induced pain?” *The Journal of Pain*, vol. 12, no. 1, pp. 61–70, 2011. https://doi.org/10.1016/j.jpain.2010.04.012.

[4] B. Figner y R. O. Murphy, “Using skin conductance in judgment and decision making research,” en *A Handbook of Process Tracing Methods for Decision Research*, M. Schulte-Mecklenbeck, A. Kuehberger y R. Ranyard, Eds. Nueva York, NY, Estados Unidos: Psychology Press, 2011, pp. 163–184.
