# Jenkins con Docker Plugin
<b><i>Univesidad Icesi</i></b><br>
Santiago De Los Ríos<br>
Nelson David Padilla H.</br>
Juan Camilo Amezquita</br>
<h2>Proyecto Final</h2>
<p>En el siguiente proyecto se realiza el aprovicionamiento de un ambiente que permita realizar integración continua, utilizando la herramienta jenkins, junto con la tecnologia de virtualización docker. A contiuación, se presenta la arquitectura utilizada.</p>
![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/arquitectura.jpg)
<h2>Procedimiendo:</h2>
## 1. Clonar repositorio
```
$ git clone https://github.com/phndavid13/docker_app
```
## 2. Crear imagenes
Ingrese al directorio master, para crear la imagen del servidor master con jenkis y ejecute la siguiente instrucción:
```
$ docker build -t jenkins_master .
```
## 3. Ejecutar docker-compose
Ingrese al directorio proyecto_distribuidos para levantar la maquina jenkins_master y ejecute la siguiente instrucción:
```
$ docker-compose up
```
Una vez finalizado este procedimiento, puede ir al navegador y ejecutar la Ip: 127.0.0.1 con el puerto: 8080. A continuación, se muestra lo que usted tiene que visualizar.
![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/jenkins_1.jpg)
