# Jenkins con Docker Plugin
<b><i>Univesidad Icesi</i></b><br>
Santiago De Los Ríos - 12207009<br>
Nelson David Padilla H. - 12207013</br>
Juan Camilo Amezquita - 122030022
# Proyecto Final
En el siguiente proyecto se realiza el aprovicionamiento de un ambiente que permita realizar integración continua, utilizando la herramienta jenkins, junto con la tecnologia de virtualización docker. A contiuación, se presenta la arquitectura utilizada.

![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/arquitectura.jpg)

# Procedimiento:
## 1. Clonar repositorio
```
$ git clone https://github.com/santidelosrios/proyecto_distribuidos
```
## 2. Crear imagen master
Ingrese al directorio master y construya la imagen del contenedor que tiene el nodo maestro de Jenkins.
```
$ cd master
$ docker build -t jenkins_master .
```
Esto inicia el proceso de construir la imagen del maestro de Jenkins que permitirá aprovisionar un contenedor con dicha herramienta. La siguiente imagen muestra el proceso de construcción de la imagen.

![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/cli-master.png)

## 3. Crear imagen slave

Ingrese al directorio slave y construya la imagen del contenedor que tiene el nodo esclavo de Jenkins.
```
$ cd slave
$ docker build -t jenkins_slave .
```
Esto inicia el proceso de construir la imagen del esclavo de Jenkins que permitirá aprovisionar un contenedor con dicha herramienta. La siguiente imagen muestra el proceso de construcción de la imagen.

![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/cli-slave.png)

## 4. Ejecutar Contenedor Maestro
Ingrese al directorio proyecto_distribuidos para levantar el contenedor con la imagen jenkins_master:
```
$ docker run -p 8080:8080 -d jenkins_master
```
Una vez finalizado este procedimiento, puede ir al navegador y ejecutar la Ip: 172.17.0.1 ó 127.0.0.1 con el puerto: 8080. A continuación, se muestra lo que usted tiene que visualizar.

![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/jenkins_1.jpg)

Para comprobar que la instalación de los plugings fue exitosa puede ir al gestor de plugins, tal como se muestra en la imagen a continuación:

![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/jenkins_2.jpg)

## 5. Configuración del servidor de Docker en Jenkins
Para permitir que Jenkins cree los nodos esclavos para ejecutar pruebas, se debe utilizar el Docker plugin y configurar el servidor que tendrá las imagenes de los contenedores.

Para esto, en la pantalla inicial de Jenkins, vaya a la opción Manage Jenkins > System Configuration > Add Cloud > Docker y registre la información como lo muestra la siguiente imagen.

![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/docker-cloud.png)

## 6. Configuración de las imagenes para los esclavos
Más abajo de la configuración de servidor de Docker, haga click en la opción add template e ingrese la información que se muestra en la imagen.

![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/docker-image-1.png)

## 7. Configuración de un Job

![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/jenkins_3.jpg)

En la página principal de Jenkins, en la parte central, haga click en new item. Posteriormente, escriba un nombre para el trabajo y seleccione la opción freestyle project y luego en ok. Eso lo llevará a la página de configuración del trabajo, ingrese la información que se ve en las siguientes imagenes.

![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/job-setup-1.png)
![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/job-setup-2.png)
![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/job-setup-3.png)

Inicialmente, se configura que el trabajo se corra dentro de un contenedor esclavo usando Docker. Posteriormente, se especifica que solo se puede correr usando un nodo específico. Además, se configura la fuente del código, la cual es un repositorio en GitHub. Por último, se configura que se ejecute un comando de shell en el momento de la construcción del trabajo. Este comando ejecuta la aplicación que se tiene en el repositorio de GitHub.

# Test
## 1. Funcionamiento de las pruebas del Job
Después de terminar la configuración, haga click en <i>save</i> y se le redireccionará a la página principal del job. Haga click en <i>Build Now</i>. Esto comenzará el proceso de construcción de la prueba. Posteriormente, haga click en el número de build que hizo y verificar que hubo éxito en la prueba.

![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/console-output-1.png)
![alt tag] (https://github.com/santidelosrios/proyecto_distribuidos/blob/master/img/console-output-1.png)

# Referencias
<ul>
<li>http://devopscube.com/docker-containers-as-build-slaves-jenkins/</li>
<li>https://engineering.riotgames.com/news/jenkins-ephemeral-docker-tutorial</li>
<li>https://github.com/d4n13lbc/testproject</li>
</ul>
