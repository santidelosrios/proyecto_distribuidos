# Jenkins con Docker Plugin
<b><i>Univesidad Icesi</i></b><br>
Santiago De Los Ríos - 12207009<br>
Nelson David Padilla H. - 12207013</br>
Juan Camilo Amezquita</br>
<h2>Proyecto Final</h2>
<p>En el siguiente proyecto se realiza el aprovicionamiento de un ambiente que permita realizar integración continua, utilizando la herramienta jenkins, junto con la tecnologia de virtualización docker. A contiuación, se presenta la arquitectura utilizada.</p>
![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/arquitectura.jpg)
<h2>Procedimiendo:</h2>
## 1. Clonar repositorio
```
$ git clone https://github.com/santidelosrios/proyecto_distribuidos
```
## 2. Crear imagenes
Ingrese al directorio master y construya la imagen del contenedor que tiene el nodo maestro de Jenkins.

```
$ cd master
$ docker build -t jenkins_master .
```
## 3. Ejecutar Contenedor Maestro
Ingrese al directorio proyecto_distribuidos para levantar el contenedor con la imagen jenkins_master:

```
$ docker run -p 8080:8080 -d jenkins_master
```
Una vez finalizado este procedimiento, puede ir al navegador y ejecutar la Ip: 172.17.0.1 con el puerto: 8080. A continuación, se muestra lo que usted tiene que visualizar.
![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/jenkins_1.jpg)

Para comprobar que la instalación de los plugings fue exitosa puede ir a :
![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/jenkins_2.jpg)

## 4. Configuración del servidor de Docker en Jenkins

Para permitir que Jenkins cree los nodos esclavos para ejecutar pruebas, se debe utilizar el Docker plugin y configurar el servidor que tendrá las imagenes de los contenedores.

Para esto, en la pantalla inicial de Jenkins, vaya a la opción Manage Jenkins > System Configuration > Add Cloud > Docker y registre la información como lo muestra la siguiente imagen.


## 5. Configuración Job
![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/jenkins_3.jpg)
