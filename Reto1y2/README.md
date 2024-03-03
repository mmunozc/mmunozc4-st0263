# info de la materia: ST0263 <Top. Telematica>
#
# Estudiante(s): Mateo Muñoz Cadavid, mmunozc4@eafit.edu.co
#
# Profesor: Edwin Nelson Montoya Múnera , emontoya@eafit.edu.co
#

# Reto 1 y 2
#
## 1. breve descripción de la actividad

### 1.1. El desarrollo del reto ha resultado en la creación de un sistema P2P, aprovechando microservicios que se comunican a través de gRPC. Esta implementación ha permitido establecer una comunicación efectiva entre los pear de la red, sin depender de un servidor centralizado. Cada par se conecta exitosamente a un servidor de arranque (Pear #1), facilitando así el inicio y la organización de la red. Además, se ha logrado cumplir con todos los requisitos de despliegue y configuración en el entorno de AWS para las instancias de cada pear, garantizando un funcionamiento óptimo en dicho entorno.

### 1.2. Se han identificado varios aspectos que no se cumplieron completamente en la implementación del proyecto. En primer lugar, la funcionalidad de transferencia de archivos y la confirmación de dicha acción no fueron correctamente implementadas, lo que limita la capacidad del sistema para intercambiar datos entre los pears de la red de manera efectiva. Además, se observa una inconsistencia en la conexión entre los pears, con algunas instancias en las que la conexión no se establece correctamente.

## 2. 
### Se ha implementado una arquitectura basada en microservicios dentro de una red P2P, donde se hace uso del protocolo gRPC para facilitar la comunicación entre estos servicios. Esta elección de diseño pone un fuerte énfasis en la modularidad, permitiendo que cada microservicio funcione de manera independiente, lo que facilita su mantenimiento y escalabilidad. Además, gRPC ofrece una solución eficiente para la gestión de conexiones concurrentes, lo que mejora la capacidad del sistema para manejar múltiples solicitudes simultáneas de manera rápida y efectiva. Este enfoque técnico garantiza una arquitectura robusta y adaptable, adecuada para entornos distribuidos como una red P2P.

## 3. 
### Lenguaje de Programación y Librerías Utilizadas: El proyecto se desarrolla principalmente en Python, versión 3.x. Se emplean varias librerías y paquetes, incluyendo grpcio (v1.62.0) y grpcio-tools (v1.62.0) para la implementación de la comunicación gRPC, así como requests (v2.31.0) para otras operaciones de red. Además, se definen otras dependencias en el archivo requirements.txt.

### Compilación y Ejecución: La aplicación se ejecuta directamente utilizando Python. Para la compilación de archivos .proto y la generación de código gRPC, se emplea la herramienta grpcio-tools.

### Configuración del Proyecto: Los parámetros de configuración, como la dirección IP, el puerto y otros detalles específicos, se gestionan mediante archivos de configuración. Esta estructura permite una configuración flexible y adaptable a diferentes entornos de ejecución, facilitando así la gestión y la portabilidad del proyecto.

### Detalles tecnicos: 

### Organizacion del sistema:

### como se compila y ejecuta.
### detalles del desarrollo.
### detalles técnicos
### descripción y como se configura los parámetros del proyecto (ej: ip, puertos, conexión a bases de datos, variables de ambiente, parámetros, etc)
### opcional - detalles de la organización del código por carpetas o descripción de algún archivo. (ESTRUCTURA DE DIRECTORIOS Y ARCHIVOS IMPORTANTE DEL PROYECTO, comando 'tree' de linux)
### 
### opcionalmente - si quiere mostrar resultados o pantallazos 

# 4. Descripción del ambiente de EJECUCIÓN (en producción) lenguaje de programación, librerias, paquetes, etc, con sus numeros de versiones.

# IP o nombres de dominio en nube o en la máquina servidor.

## descripción y como se configura los parámetros del proyecto (ej: ip, puertos, conexión a bases de datos, variables de ambiente, parámetros, etc)

## como se lanza el servidor.

## una mini guia de como un usuario utilizaría el software o la aplicación

## opcionalmente - si quiere mostrar resultados o pantallazos 

## 5. otra información que considere relevante para esta actividad.

### referencias:

### https://github.com/st0263eafit/st0263-241/blob/main/README.md
### https://grpc.io/docs/languages/python/basics/
