# Proyecto Final del Segundo Parcial
# Representación de Modelo Lider-Seguidor 

_En este proyecto, implementaremos un sistema distribuido, que permitirá hacer una Escritura y lectura de informacion proporcionada por un usuario, en el que el sistema cuenta con nodos que repliquen la data como respaldo. Se utilizó lenguaje de progamación Java y herramienta de base de datos se utilizó un archivo txt donde se guardaria cada dato del CLiente con un formato de log._

## Obejetivos 📌
_Este proyecto tiene como objetivo ejercitar la creación de aplicaciones distribuidas que permitan la transferencia y procesamiento de información entre varios nodos con su respectiva replicación, donde se respaldan tambien de un Log para el almacenamiento de la data en .json. Adicionalmente se ponen en práctica otros conceptos como replicacion, escalabilidad de aplicaciones, rendimiento, etc._

## Comenzando 🚀

_Se necesitaran como requisito crear una maquina virtual para que se conserve la idea de implementar los sistemas distribuidos._

### Pre-requisitos para Productor 📋

```
Maquinas virtuales deben contar con Ubuntu server o con interfaz.
La maquina virtual debe de contar con una configuración de red de 'Adaptador Puente'.
```

### Instalación 🔧

_Dependecias que se debe instalar desde un principio para la ejecucion del proyecto_

```
sudo apt-get update
sudo apt install net-tools
sudo apt install default-jdk
sudo apt install git
sudo apt install erlang
sudo apt intall ipconfig
```

_Una vez instalado las dependencias procederemos con las ejecuciones_

## Ejecutando las pruebas ⚙️

_Tendremos que clonar el repositorio del codigo realizado en nuestra maquina vitual, el cual en ese ejecutaremos el .properties para poder cambiar los parametros de ejecuion del Rabitt. Accedemos al carpeta donde esta ubicado el .properties, y una vez en la directorio, accedemos con un nano para cambiar parametros.
```
git clone https://github.com/miguelperezmvp/uees-sd-proyectofinal.git      // git clone "link repositorio".git
```
```
nano archive.propeties
```
_Se accede a la carpeta donde se ecuentran los .java y las librerias del repositorio y una vez dentro se ejecuntan estos comandos. Para poder incializar con la ejecucion del programa._
```
Terminal de MAIN
javac -cp json-2014017.jar *.java
java main
```
_Con la ejecucion de Main el Api se conecta al puerto 9000 el cual manda instucciones de CRUD hacia el lider._
_El TCP server se conectara al puerto 5000, el cual siendo el primero este de proclama como lider, apto para escrituras y lecturas********._


### Acceder a RabbitMQ 🔩

_Se puede acceder al RabbitMQ en la propia maquina virtual con interfaz desde el navegador_

```
localhost:15672       //Puerto de RabbitMQ
```
_Tambien se puede acceder desde el navegador de tu propia computadora por medio del ip que tiene y el puerto en el corre RabbitMQ el cual es 15672. En caso personal es http://192.168.100.131:15672/ _

_Una vez dentro de este, te vas al apartado de Queues en el que puedes observar las tareas enviadas, en un cola,esperando que sean consumidas por el Consumidor._



## Ejecutando las pruebas de CONSUMIDOR⚙️
_Apenas es ejecutado el Producer, la informacion llegaria al Consumer por medio de que ambos estan conectados al Rabbit_
_La funcion del Consumer espera el mensaje .json, a lo que lee las firmas(id) de los archivos leidos en producer_
_El consumidor los guarda en .txt con las firmas para indicar en caso de que quieran mandar la misma informacion, decir que ya fue procesada. De esta manera se realizo' la persistencia del programa._
_Se leen los .json y junta las palabras en un archivo de texto junto a sus frecuencias para luego mostrarlas en forma descendente y las primeras 10.

```
HOLA 4
archivo 3
bisco 3
casa 2
palma 2
daniel 1
computadora 1
palabra 1
rabbit 1
guarda 1

```
_A su vez, cuando el consumidor capta los mensajes del producer, se eliminan de la cola de mesnajes del Rabbit._
## Despliegue 📦

_Tener en cuenta las configuraciones de la maquina virtual y las dependencias descargadas._

## Construido con 🛠️

_Herramientas utilizadas para el proyector_

* [Virtualbox](https://www.virtualbox.org/) - El cual se instalarón las maquinas virtuales.
* [Java](https://www.java.com/es/download/help/develop.html) - Descarga de dependencia de JDK y Java a utlizar.

## Versionado 📌

Para todas las versiones disponibles, mira los [tags en este repositorio](https://github.com/tu/proyecto/tags).

## Autores ✒️

_Menciona a todos aquellos que ayudaron a levantar el proyecto desde sus inicios_

* **Steven Rodriguez** - [estiven94ops](https://github.com/estiven94ops)
* **Miguel Perez** - [miguelperezmvp](https://github.com/miguelperezmvp)

