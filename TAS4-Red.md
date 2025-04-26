
# TAS4-Red de Contenedores
## 1. Titulo
Despliegue y Configuración de Servidores de Base de Datos MySQL y phpMyAdmin en Contenedores Docker
## 2. Tiempo de duración
El tiempo fue de 120 minutos. 
## 3. Fundamentos:

## Redes Docker 

Las redes Docker configuran las comunicaciones entre contenedores vecinos y servicios externos. Los contenedores deben estar conectados a una red Docker para recibir conectividad de red. Las rutas de comunicación disponibles para el contenedor dependen de sus conexiones de red (Docker Networking - Basics, Network Types & Examples, n.d.).

La red de contenedores se refiere a la capacidad de los contenedores de conectarse y comunicarse entre sí o con cargas de trabajo que no sean Docker. Los contenedores tienen la red habilitada por defecto y pueden realizar conexiones salientes. Un contenedor no tiene información sobre el tipo de red al que está conectado ni si sus pares también son cargas de trabajo de Docker. Un contenedor solo ve una interfaz de red con una dirección IP, una puerta de enlace, una tabla de enrutamiento, servicios DNS y otros detalles de red. Esto es así, a menos que el contenedor utilice el nonecontrolador de red (Redes | Documentación de Docker, n.d.).

<img src="./docker-img/contenedor.png" alt="drawing0" width="500"/>

## MySQL 

La forma tradicional de ejecutar una base de datos MySQL es instalar los paquetes MySQL y las aplicaciones simplemente tendrían que conectarse al puerto de escucha. La mayoría de las tareas de administración, como el ajuste de la configuración, las copias de seguridad, la restauración, la actualización de la base de datos, el ajuste del rendimiento y la resolución de problemas, deben ejecutarse en el propio host de la base de datos. Se espera que haya varios puertos accesibles para la conexión, por ejemplo, el puerto TCP 22 para SSH, el TCP 3306 para MySQL o el UDP 514 para syslog (Contenedores Docker de MySQL: Conceptos Básicos | Variousnines, n.d.).

En un contenedor, piense en MySQL como una sola unidad que solo sirve contenido relacionado con MySQL en el puerto 3306. La mayor parte de las operaciones se realizan en este único canal. Docker funciona de maravilla empaquetando su aplicación/software en una sola unidad, que luego puede implementar en cualquier lugar siempre que el motor Docker esté instalado. Espera que el paquete o la imagen se ejecute como un único proceso por contenedor. Con Docker, el flujo sería que usted (o alguien más) cree una imagen de MySQL con una versión y un proveedor específicos, la empaquete y la distribuya a cualquiera que desee ejecutar una instancia de MySQL rápidamente (Contenedores Docker de MySQL: Conceptos Básicos | Variousnines, n.d.).


<img src="./docker-img/imagen.png" alt="drawing0" width="500"/>

## PhpMyAdmin

La forma tradicional de ejecutar una base de datos MySQL es instalar los paquetes MySQL y las aplicaciones simplemente tendrían que conectarse al puerto de escucha. La mayoría de las tareas de administración, como el ajuste de la configuración, las copias de seguridad, la restauración, la actualización de la base de datos, el ajuste del rendimiento y la resolución de problemas, deben ejecutarse en el propio host de la base de datos. Se espera que haya varios puertos accesibles para la conexión, por ejemplo, el puerto TCP 22 para SSH, el TCP 3306 para MySQL o el UDP 514 para syslog (Contenedores Docker de MySQL: Conceptos Básicos | Variousnines, n.d.).

En un contenedor, piense en MySQL como una sola unidad que solo sirve contenido relacionado con MySQL en el puerto 3306. La mayor parte de las operaciones se realizan en este único canal. Docker funciona de maravilla empaquetando su aplicación/software en una sola unidad, que luego puede implementar en cualquier lugar siempre que el motor Docker esté instalado. Espera que el paquete o la imagen se ejecute como un único proceso por contenedor. Con Docker, el flujo sería que usted (o alguien más) cree una imagen de MySQL con una versión y un proveedor específicos, la empaquete y la distribuya a cualquiera que desee ejecutar una instancia de MySQL rápidamente (Contenedores Docker de MySQL: Conceptos Básicos | Variousnines, n.d.).


<img src="./docker-img/imagen.png" alt="drawing0" width="500"/>

## 4. Conocimientos previos.
   
Para realizar esta practica el estudiante necesita tener claro los siguientes temas:
- Comandos básicos de Docker.
- Conceptos básicos de bases de datos
- Conocimientos de acceso web y puertos.

## 5. Objetivos a alcanzar

- Crear un contenedor de MySQL configurando usuario y contraseña.
- Crear un contenedor de phpMyAdmin conectado a MySQL.
- Crear una red personalizada en Docker.
- Interconectar los contenedores por nombre de servicio.
- Crear una base de datos de prueba desde la interfaz de phpMyAdmin.

## 6. Equipo necesario:
  
- Computador.
- Docker funcionando.
- Navegador web.

## 7. Material de apoyo.
   
- Documentación de Docker
- Guía de asignatura.
- Cheat Sheet de comandos Docker.
- Documentación oficial de MySQL y phpMyAdmin.
- Videos tutoriales de redes Docker.
## 8. Procedimiento

### Pasos 

1. Crear un contenedor para MySQL, definiendo las credenciales necesarias.

Figura 8-1 Creación de contenedor MySQL.

<img src="./docker-img/1.PNG" alt="drawing0" width="500"/>

2. Crear un contenedor para phpMyAdmin, configurando las credenciales.

Figura 8-2 Creación de contenedor phpMyAdmin.

<img src="./docker-img/3.PNG" alt="drawing0" width="500"/>

3. Crear una red personalizada en Docker que permita la comunicación entre ambos contenedores.

Figura 8-3 Creacion de la red personalizada.

<img src="./docker-img/instituto.PNG" alt="drawing0" width="500"/>


4. Conectar ambos contenedores a la red creada.

Figura 8-4 Conexion de los contenedores a la red.

<img src="./docker-img/4.PNG" alt="drawing0" width="500"/>

5. Configurar la conexión entre phpMyAdmin y MySQL, y crear una base de datos de prueba desde la interfaz de phpMyAdmin.

Figura 8-5 Configuracion y creacion de la base de datos en la interfaz de phpMyAdmin.


<img src="./docker-img/p1.PNG" alt="drawing0" width="500"/>


## 9. Resultados esperados:
    
Al finalizar la práctica, se logró cumplir exitosamente los objetivos planteados. Se desplegó correctamente un contenedor de base de datos MySQL, configurando las credenciales de acceso (root/admin) y exponiendo el puerto 3307. Mediante la creación de una red personalizada, se facilitó la comunicación entre los contenedores de MySQL y phpMyAdmin, evitando conflictos de puertos y garantizando la resolución de nombres de servicio.

Desde phpMyAdmin, accedido a través del navegador en el puerto 8081, se pudo gestionar el servidor MySQL y crear de forma gráfica una base de datos de prueba, verificando así la conectividad y funcionamiento del sistema. Durante el proceso se aplicaron comandos esenciales de Docker como ``docker network create``, ``docker network connect``, y se comprendió la importancia de las variables de entorno para la configuración de servicios. Todo el desarrollo de la práctica fue documentado con capturas de pantalla que evidencian la creación de la red, el despliegue de los contenedores, la configuración de acceso y la creación exitosa de una base de datos de prueba desde phpMyAdmin.

<img src="./docker-img/inst.PNG" alt="drawing0" width="500"/>


## 10. Bibliografía
    
- Imagen de Docker y contenedor: diferencia entre tecnologías de implementación de aplicaciones - AWS. (n.d.). Retrieved April 10, 2025, from https://aws.amazon.com/es/compare/the-difference-between-docker-images-and-containers/
- ¿Qué es un contenedor? | Docker. (n.d.). Retrieved April 10, 2025, from https://www.docker.com/resources/what-container/

