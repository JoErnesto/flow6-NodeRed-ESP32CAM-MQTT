# Flow 6 NodeRed-ESP32CAM-MQTT
Este repositorio contiene los archivos para el ejercicio el cual intercambiará información entre NodeRed y ESP32CAM con MQTT.

## Introducción

En el Flow se muestra como realizar el intercambio de información entre el micro controlador ESP32CAM y NodeRed a través de MQTT. El objetivo es demostrar como mandar instrucciones desde NodeRed al ESP32CAM por medio de un Broker local.

## Material Necesario

### Software
Para poder hacer funcionar este proyecto, es necesario contar con los siguientes softwares:
- [Ubuntu 20.04](https://releases.ubuntu.com/20.04/)
- [Arduino IDE](https://www.arduino.cc/en/software)
    - [Gestor de tarjetas ESP32](https://github.com/iotechbugs/esp32-arduino/blob/master/docs/arduino-ide/boards_manager.md)
    - [Configuración de la IDE de Arduino para trabajar con el ESP32CAM](https://github.com/iotechbugs/esp32-arduino)
    - [Biblioteca PubSubClient](https://github.com/knolleary/pubsubclient)
- [Mosquitto MQTT Broker](https://mosquitto.org/download/)
    - [Listener en puerto 1883 para 0.0.0.0 y conexiones no autentificadas activadas](https://mosquitto.org/man/mosquitto-conf-5.html)
- [NodeJS](https://nodejs.org/es/)
    - [NPM](https://www.npmjs.com/)
    - [NodeRed](https://nodered.org/docs/getting-started/local)
    - [Nodos Dashboard](https://flows.nodered.org/node/node-red-dashboard)
### Hardware

Para implementar el ejercicio se requiere de los siguientes componentes eletrónicos:
- Micro controlador ESP32CAM.
- Adaptador de niveles TTL FTDI32.
- Cable USB-A a USB Mini.
- Jumpers.
- Protoboard.
## Material de referencia

En los siguientes enlaces puedes encontrar cursos en la plataforma de edu.codigoiot.com que te permitirán realizar las configuraciones necesarias:

- [Instalación de Virutal Box y Ubuntu 20.04](https://edu.codigoiot.com/course/view.php?id=812)
- [Configuración de Arduino IDE para ESP32CAM](https://edu.codigoiot.com/course/view.php?id=850)
- [Instalación de NodeRed](https://edu.codigoiot.com/course/view.php?id=817)
- [Introducción a NodeRed](https://edu.codigoiot.com/course/view.php?id=278)
- [Instalación de Mosquitto MQTT](https://edu.codigoiot.com/course/view.php?id=818)

## Instrucciones

### Requisitos previos

Para que el Flow funcione, se debe cumplir con los siguientes requisitos previos:
1. Instalación de NodeJS. Se recomienda tener instalado NodeJS en alguna versión LTS. Al momento de creación de este documento, se usó la versión 16.17.0LTS. Esta instalación debe incluir las Build-Tools para hacer uso de NPM.
2. Instalación de NodeRed. La instalación se realiza por NPM. Al momento de la creación de este contenido, se usó la versión 3.0.2 .
3. Instalar los nodos node-red-dashboard. Para ello, dirigete a la opcion "Manage Palette" de NodeRed y en la pestaña Install busca node-red-dashboard. Finalmente haz clic en instalar.
4. Instalación de Broker local Mosquitto MQTT.
5. Configurar el archivo mosquitto.conf para que el Broker Local acepte conexiones externas.

### Instrucciones de preparación del entorno

Para poder configurar tu entorno y realizar este ejercicio, encesitas lo siguiente:

1. Realiza el circuito. Las instrucciones se encuentran en el encabezado del código para el ESP32CAM. Deberás cambiar lo siguiente:
    - El tema de publicación y suscripción.
    - Nombre de red y contraseña al que deseas conectarte.
    - IP de tu broker local.
    - Tiempo de espera entre envío de datos en milisegundos.

2. Arrancar NodeRed con el comando `node-red`
    - Importar el flow del repositorio.
    - Modifica los temas MQTT segun tus necesidades.


### Instrucciones de operación

- Para observar el resultado de este Flow, abre un navegador y dirígete a [localhost:1880/ui](http://localhost:1880/ui) desde la computadora que ejecuta NodeRed.
-  Energizar el ESP32CAM y asegurarse de que esta en rango de una conexión WiFi.

### Notas

- Este Flow se suscribe al tema codigoIoT/flow6/mqtt
- El mensaje mqtt usado para probar este flow es `mosquitto_pub -h localhost -t codigoIoT/Mor/mqtt/flow4 -m '{"ID":"Ernesto","temp":22,"hum":47}'`
- Este flow publica en el tema codigoIoT/flow6/mqttin

## Resultados

A continuación puedes ver los nodos del Flow:
![](https://github.com/JoErnesto/flow6-NodeRed-ESP32CAM-MQTT/blob/main/Imagenes/Nodos%20del%20Flow.png?raw=true)

A continuación se muestra el tablero con el switch para controlar el LED Flash y el mensaje recibido del ESP32CAM.

![](https://github.com/JoErnesto/flow6-NodeRed-ESP32CAM-MQTT/blob/main/Imagenes/Dashboard.png?raw=true)

El funcionamiento del Flow consiste en enciender y apagar el LED Flash del ESP32CAM cuando se activa el switch, en la sección de evidencias se adjuntó un video demostrativo del funcionamiento del ejercicio.

## Evidencias

- [YouTube](https://youtu.be/sUcCGvNIRyc)

# Créditos

Desarrollado por José Ernesto Calvillo Lizárraga
- [GitHub](https://github.com/JoErnesto)
- [LinkedIn](https://www.linkedin.com/in/jos%C3%A9-ernesto-calvillo-liz%C3%A1rraga-4188a4231/)