# Proyecto Final del Segundo Parcial
# Representación de Modelo Lider-Seguidor 

_En este proyecto, implementaremos un sistema distribuido, que permitirá hacer una Escritura y lectura de informacion proporcionada por un usuario, en el que el sistema cuenta con nodos que repliquen la data como respaldo. Se utilizó lenguaje de progamación Java y herramienta de base de datos se utilizó un archivo txt donde se guardaria cada dato del CLiente con un formato de log._

## Objetivos 📌
_Este proyecto tiene como objetivo ejercitar la creación de aplicaciones distribuidas que permitan la transferencia y procesamiento de información entre varios nodos con su respectiva replicación, donde se respaldan tambien de un Log para el almacenamiento de la data en .json. Adicionalmente se ponen en práctica otros conceptos como replicacion, escalabilidad de aplicaciones, rendimiento, etc._

## Comenzando 🚀

_Se necesitaran como requisito crear una maquina virtual para que se conserve la idea de implementar los sistemas distribuidos._

## Funcionamiento y Logica ⚙️

_Para comenzar El TCP server se conectara al puerto 9000, el cual La primera vez que se ejecuta el programa, detecta si está bierto el puerto 9000, si no, se ejecuta como líder;si si, se ejecuta como seguidor._
_Con la ejecucion de Main se abre un servidor en el puerto 5000 para manejar una api, es decir, cada nodo tiene su propia api el cual manda instrucciones CRUD (LIMITADO PARA ALGUNOS NODOS)._
_Si ejecutamos un nuevo Main, este detectará que el puerto 5000 ya está ocupado y abrirá en el siguiente. Y así sucesivamente con cada nuevo nodo_

Líder y seguidores están conectados a través de un tcp server/client, cuando se ejecuta una función en la api, este llega a la clase Api la cual lo maneja y responde en base a la función que se haya mandado (CRUD)

_Si se decide hacer un post, se lo pasa como json, el cual lo recibe el líder y lo guarda en un log como "POST {json}". Luego el servidor envía un mensaje en bytes a los clientes, los cuales haran el g en su propio log, a su vez que manejaran su propio diccionario en dónde se van agregando clientes una vez se realiza el post. De esta manera a cada nodo seguidor se le podrá hacer una consulta GET de algún cliente._
```
Nodo lider: POST, PUT, GET, DELETE
Nodo seguidor: GET,PUT
```

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

Tendremos que clonar el repositorio del codigo realizado en nuestra maquina vitual, el cual en ese ejecutaremos el .properties para poder cambiar los parametros de ejecuion del Rabitt. Accedemos al carpeta donde esta ubicado el .properties, y una vez en la directorio, accedemos con un nano para cambiar parametros.
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

