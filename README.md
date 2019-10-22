# Hackaton IBM - Chatbot Escuela de Energía de la Fundación Naturgy
## Introducción
El presente proyecto implementa un chatbot para su uso por parte de los formadores, alumnos y visitantes de la Escuela de Energía de la Fundación Naturgy. El chatbot permite responder de forma ágil a las preguntas que puedan surgir sobre las actividades de la Escuela de Energía, noticias, plan de vulnerabilidad, pobreza energética, etc.
El proyecto **se ha desarrollado integramente empleando las herramientas o servicios de IBM Cloud.**
Las herramientas utilizadas han sido:
  1. Watson Assistant
  2. Text To Speech
  3. Speech To Text
  4. Watson Discovery
  5. Node Red
  
Para la implementación del proyecto es necesario tener una cuenta IBM CLOUD con los servicios LITE
## Descripción del Proyecto
### Chatbot Watson Assistant
Se han desarrollado dos chatbot, el primero de ellos denominado **Fundación** con funcionalidad completa de imágenes, textos, links, etc. para su integración en una web; mientras que el segundo chatbot **Fundación_breve** es un asistente con respuesta de sólo texto para facilitar su integración con las herramientas Speech_To_Text, Text_To_Speech y Telegram.
El chatbot Fundación consta de dos skills: Uno de diálogo y otro de búsqueda. Este último busca información en la página WEB de la Fundación Naturgy. El skill de Diáologo consta de 19 intents, 7 entities y 45 cuadros de diálogo.
En el diálogo se puede interaccionar con el bot sobre cuestiones relacionadas con vulnerabilidad energética,clientes vulnerables, escuela de nergía, fundación Naturgy, etc.
En la lista de archivos del proyecto se encuentra el JSON correspondiente a ambos diálogos y en la imagen se puede observar una captura de uno de ellos.

<img src="https://github.com/manrodan/fundacion-hackaton-ibm/blob/master/Dialogo.png"
     alt="Dialogo"
     style="float: left; margin-right: 50px;"
     width="900"/>

Para incorporar el los Dialogos es necesario hacerlo siguiendo los siguientes pasos.
    1. Dar de alta y lanzar el servicio Watson-Assistant
    2. Crear un asistente.
    3. Añadir un diálogo exportando el JSON adjunto
*Nota:Para añdir el skill de Búsqueda es necesario utilizar los servicios PLUS* 
### Integración con otras aplicaciones
#### Watson Discovery
Se ha incluido en el chatbot la posibilidad de búsqueda de información a través del servicio Discovery. 
La búsqueda se ha configurado para realizarse en  información almacenada en la web de la Fundación Naturgy y permite ampliar la respuesta en el caso de cuestiones relacionadas con la Escuela de Energía, y en otros puntos del ChatBot sobre cuestiones no registradas en el Diálogo.
Para ello se ha utilizado el servicio de WEB_CRAWL y se ha configurado el mismo en cuadro de diálogo SEARCH del asistente de Watson.
#### Integración con Node Red del servicio de Telegram
En el siguiente enlace aparecen los pasos para darse de alta en Node-Red y como crear una aplicación:
[Guía Node Red]:(https://cloud.ibm.com/docs/cloud-foundry?topic=cloud-foundry-gettingstarted-nodered)
En el gráfico siguiente se muestra la arquitectura desarrollada en Node Red para implementar su integración con Telegram. 
Es necesario descargarse de la librerías de Node Red, los nodos de Telegram: [Librería Node Red](https://flows.nodered.org/)
<img src="https://github.com/manrodan/fundacion-hackaton-ibm/blob/master/Diapositiva2.PNG"
     alt="Node Red"
     style="float: left; margin-right: 50px;"
     width="900"/>
Para lanzar la integración es necesario, previamente, haberse dado de alta en la aplicación Telegram y la cuenta Bot Father. A partir de ahí es necesario crearse un chat y capturar su token para introducirlo en la configuración de Node Red
La respuesta al mensaje entrante será la que esté configurada en el chatbot reducido de **Fundación_breve**
El nodo correspondiente a Watson deberá ir configurado con la API y la URL correspondiente asignada por el servicio Assistant como se puede ver en el gráfico de abajo
<img src="https://github.com/manrodan/fundacion-hackaton-ibm/blob/master/Assistant.png"
     alt="Assistant"
     style="float: left; margin-right: 50px;"
     width="900"/>
#### Integración con Node Red del servicio de Text to Speech y Speech To Text
En el gráfico siguiente se muestra la arquitectura creada en Node Red para implementar esta integración.
Es necesario descargarse de la librerías de Node Red, los nodos de microphone y play audio: [Librería Node Red](https://flows.nodered.org/)
<img src="https://github.com/manrodan/fundacion-hackaton-ibm/blob/master/Diapositiva3.PNG"
     alt="Node Red"
     style="float: left; margin-right: 50px;"
     width="900"/>
Para su funcionamiento es recomendable utilizar el navegador **Chrome**. Para emplearlo es necesario disponer de un micrófono activándolo al clicar sobre la caja de node red que aparece y clicando otra vez una vez terminemos nuestra pregunta.
