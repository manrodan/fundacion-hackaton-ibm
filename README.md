# Hackaton IBM - Chatbot Escuela de Energía - Fundación Naturgy
## Introducción
El presente proyecto implementa un chatbot para su uso futuro por parte de los formadores, alumnos y visitantes de la Escuela de Energía de la Fundación Naturgy. El chatbot permitirá responder de forma ágil a las preguntas que puedan surgir sobre las actividades de la Escuela de Energía, noticias, plan de vulnerabilidad, pobreza energética, etc.
El proyecto se ha desarrollado enteramente empleando las herramientas o servicios de IBM Cloud.
Las herramientas utilizadas han sido:
  1. Watson Assisant
  2. Text To Speech
  3. Speech To Text
  4. Watson Discovery
  5. Node Red
## Descripción del Proyecto
### Chatbot Watson Assistant
Se han desarrollado dos chatbot, el primero de ellos denominado **Fundación** con funcionalidad completa de imágenes, textos, links, etc. para su integración en una web; mientras que el segundo chatbot **Fundación_breve** es un asistente con respuesta de sólo texto para facilitar su integración con las herramientas Speech_To_Text, Text_To_Speech y Telegram.
El chatbot Fundación consta de dos skills: Uno de diálogo y otro de búsqueda. Este último busca información en la página WEB de la Fundación Naturgy. El skill de Diáologo consta de 19 intents, 7 entities y 45 cuadros de diálogo
En la lista de archivos se encuentra el JSON correspondiente a ambos diálogos y en la imagen se puede observar una captura de uno de ellos.

<img src="https://github.com/manrodan/fundacion-hackaton-ibm/blob/master/Dialogo.png"
     alt="Dialogo"
     style="float: left; margin-right: 50px;"
     width="900"/>

### Integración con otras aplicaciones
#### Watson Discovery
Se ha incluido en el chatbot la posibilidad de búsqueda de información a través del servicio Discovery. La búsqueda se efectúa a traves de la web de la Fundación Naturgy.
#### Integración con Node Red del servicio de Telegram
En el gráfico siguiente se muestra la arquitectura desarrollada en Node Red para implementar su integración con Telegram. 

<img src="https://github.com/manrodan/fundacion-hackaton-ibm/blob/master/Diapositiva2.PNG"
     alt="Dialogo"
     style="float: left; margin-right: 50px;"
     width="900"/>
