
### Estudiante:
- Mateo Muñoz Cadavid, mmunozc4@eafit.edu.co

### Profesor:  Edwin Nelson Montoya Munera, emontoya@eafit.edu.co  

# Laboratorio 6: IMPLEMENTACIÓN DE UN DATA WAREHOUSE SENCILLO CON AWS S3, GLUE y ATHENA.

##  Objetivo
El objetivo del laboratorio 5 es familiarizarse con los servicios de AWS S3, Glue y Athena para la implementación de un Data Warehouse sencillo. Se busca entender el proceso de ingestión de datos manual a S3, la catalogación de datos con Glue y la realización de consultas SQL con Athena.

## Descripción de la Actividad 
En la actividad se realiza la ingestión manual de datos a AWS S3 desde un conjunto de datos proporcionados en GitHub. Luego, se procede a catalogar los datos con AWS Glue, creando dos bases de datos (onudb y tickitdb) y las respectivas tablas. Por último, se realizan consultas SQL con AWS Athena a las tablas catalogadas para analizar los datos almacenados.

## Guia paso a paso 
- En AWS necesitamos buscar y acceder al servicio llamado "S3":
  
- Creamos un "Bucket"
  
- Realizamos las iguientes configuraciones para el "Bucket":
  - Elegimos un nombre para el Bucket
    
  - En propiedades de objetos, habilitamos los ACL:

  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/b6ab12b3-c9f9-42a4-ba73-a1248f7e1598)

  - En "Configuración de bloqueo de acceso público para este bucket", desbloquemos el acceso publico:

  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/cc96d4ca-d1b1-42dd-b42a-8470e2b7868c)

  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/968a8c9b-b1b2-4695-991c-39a8f5cb2825)
   
  - Propiedades de objetos (por defecto)
  - Control de versiones (por defecto)
  - Etiquetas (por defecto)
  - Cifrado predeterminado (por defecto)
  - Hacemos clic en "crear bucket"


### Ingresamos al Bucket

  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/1dfb166c-5848-4cec-9db3-37c3025b5264)

- Vamos a subir los datos de catalogacion que se encuentran en la carpeta datasets
  - Subir los archivos de los datasets onu y tickit al bucket.

   ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/32eec34d-03bb-45b4-bd19-9203c6eb0a86)



### Ingresamos a "AWS Glue"

- "AWS Glue" lo vamos a utilizar para poder crear y catalogar las tablas
  
- Cuando accedemos al servicio, dirigimos nuestra atención al panel izquierdo y seleccionamos la opción "Crawlers" que se encuentra en la sección "Data Catalog", con el fin de catalogar las tablas.
  
![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/c466460d-43f7-4db3-8f8d-1f4afcd5b4ca)

- Creamos un "crawler"
  
![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/454f4e5c-f849-4e52-b733-03cb56210a91)

 - Realizamos las siguientes configuraciones

 ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/ef3af1e0-cb81-40d0-955f-58739da40f00)

 - Seleccionamos el bucket que creamos

 ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/a5c8244e-9979-4277-af6a-1611f829cafb)

 ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/1caeff7c-e168-4a0f-9f6c-2ffc41912c40)

 - Seleccionamos el rol de aws academy

 ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/42a2d372-76d0-44c9-b017-e64053afaa3a)

 - En este apartado sera necesario crear una base de datos

 ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/04593f18-3aaa-4125-96ec-2f5df3b8997e)

  - Seleccionamos Add Database
    ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/4063e592-eb79-4475-b8c2-d817a615bf71)

 - Luego creamos el crawler

   ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/24d8e9b0-6cb5-48f1-8118-ceb551170442)

   ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/099033c2-fd96-4985-8459-4f8d13af2566)

- Se debe de crear una carpeta con el nombre de athena, esta se debera de crear en el Bucket
  
 ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/6e25971e-c1a2-42ec-9e9f-eeefb21df94c)

 ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/346cf5f3-5068-4fc3-a5e1-bfa89bbabd37)


### Acceso a la base de datos 

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/9dc89029-2abb-4b3f-83c3-d2d461e26b67)

- Accedemos a la base de datos que habiamos creado

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/ee217d9d-2189-4d2f-aeb9-346633889e3c)

- Ingresamos a hdi y veremos la tabla

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/8b07017c-e3bf-4049-9a16-64cab4b16e56)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/3e6b6395-2056-498d-bd5f-dadc32e42071)



### Acceso ATHENA

- Buscamos el servicio de athena y le damos a iniciar el editor de consultas

 ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/e35f839a-e72c-42ba-90e2-b35e72f7d956)

 ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/c78dc64d-7c61-40ec-a6c0-e0b9c27c454d)

 
- Le damos administrar la configuracion y seleccionamos nuestro bucket

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/8efee9c9-4cee-48ab-8907-1b7c3d6fedfe)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/e1086694-1e19-4a3b-bfa0-38996df902f0)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/2786e014-da67-46a7-87fa-0a8affc2c091)

- Creamos la siguiente consulta y la ejecutamos 

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/6a1fd6c2-0a88-435b-b220-4d0e1abb9d15)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/2cef6c98-ac6e-4bc8-b759-84864eca6840)


## Guía Completa para el Lab 4: Gestión de Datos vía SQL con HIVE y SparkSQL en un Clúster Hadoop en Amazon EMR
- Infraestructura para el Lab 4
- Conexión al Clúster Hadoop vía HUE en Amazon EMR
- Acceder a HUE:
  - Abre tu navegador web y ve a la URL proporcionada para tu clúster EMR. La URL tendrá el formato: http://ec2.compute-1.amazonaws.com:8888.
  - Ingresa con el usuario y la contraseña provistos:
    - username: hadoop
    - password: ********
- Crear tu propio usuario en HUE:
  - Después de iniciar sesión con hadoop, crea tu propio usuario para gestionar tus archivos y consultas de manera independiente.
- Preparar los Archivos de Trabajo en HDFS
- Archivos necesarios:
  - hdi-data.csv
  - export-data.csv
- Copiar los archivos al clúster EMR:
  - Asegúrate de que los archivos hdi-data.csv y export-data.csv estén disponibles en tu máquina local.
  - Utiliza el siguiente comando para copiar los archivos a HDFS:
  ```
  $ hdfs dfs -mkdir -p /user/hadoop/datasets/onu/hdi
  $ hdfs dfs -put /ruta/local/hdi-data.csv /user/hadoop/datasets/onu/hdi/
  $ hdfs dfs -put /ruta/local/export-data.csv /user/hadoop/datasets/onu/hdi/
  ```
- Gestión de Datos (DDL) y Consultas (DQL) en HIVE
- Crear la Tabla HDI en HDFS usando Beeline
- Iniciar Beeline:
  - Abre una terminal y ejecuta el comando para iniciar Beeline:
  ```
  $ beeline
  ```
- Conectarse a la base de datos:
  - Usar tu base de datos:
  ```
  use usernamedb;
  ```
- Crear la tabla HDI:
  - Ejecuta el siguiente comando para crear la tabla HDI:
  ```
      CREATE TABLE HDI (
      id INT, 
      country STRING, 
      hdi FLOAT, 
      lifeex INT, 
      mysch INT, 
      eysch INT, 
      gni INT
    ) 
    ROW FORMAT DELIMITED 
    FIELDS TERMINATED BY ',' 
    STORED AS TEXTFILE;
  ```
- Cargar Datos en la Tabla HDI
- Opción 1: Copiar datos directamente a HDFS:
```
$ hdfs dfs -put /user/hadoop/datasets/onu/hdi-data.csv /user/hive/warehouse/usernamedb.db/hdi/
```

- Opción 2: Cargar datos desde HIVE:
  - Asegúrate de dar permisos completos al directorio:
  ```
  $ hdfs dfs -chmod -R 777 /user/hadoop/datasets/onu/
  ```
  - Cargar los datos usando Beeline:
  ```
  $ beeline
  0: jdbc:hive2://sandbox-hdp.hortonworks.com:2> LOAD DATA INPATH '/user/hadoop/datasets/onu/hdi-data.csv' INTO TABLE HDI;
  ```
- Crear la Tabla HDI en EMR/S3 usando HIVE/Hue
- Tabla externa en S3:
  - Conéctate a tu base de datos:
  ```
  use usernamedb;
  ```
  - Crear la tabla externa en S3:
  ```
        CREATE EXTERNAL TABLE HDI (
        id INT, 
        country STRING, 
        hdi FLOAT, 
        lifeex INT, 
        mysch INT, 
        eysch INT, 
        gni INT
      ) 
      ROW FORMAT DELIMITED 
      FIELDS TERMINATED BY ',' 
      STORED AS TEXTFILE 
      LOCATION 's3://st0263datasets/onu/hdi/';
  ```
- Realizar Consultas y Cálculos en la Tabla HDI
- Mostrar tablas:
```
use usernamedb;
show tables;
```
- Describir la tabla HDI:
```
describe hdi;
```
- Seleccionar todos los registros de la tabla HDI:
```
select * from hdi;
```
- Consultar países con GNI mayor a 2000:
```
select country, gni from hdi where gni > 2000;
```
- Ejecutar un JOIN en HIVE
- Obtener los datos base: export-data.csv
  - Asegúrate de tener los datos en datasets del repositorio y cargarlos en HDFS/S3 según sea necesario.
- Crear la tabla EXPO:
  - Usar HIVE/Hue para crear la tabla EXPO:
  ```
        use usernamedb;
      CREATE EXTERNAL TABLE EXPO (
        country STRING, 
        expct FLOAT
      ) 
      ROW FORMAT DELIMITED 
      FIELDS TERMINATED BY ',' 
      STORED AS TEXTFILE 
      LOCATION 's3://st0263datasets/onu/export/';
  ```
- Ejecutar el JOIN de las dos tablas:
```
SELECT h.country, gni, expct 
FROM HDI h 
JOIN EXPO e ON (h.country = e.country) 
WHERE gni > 2000;
```

- Wordcount en HIVE
- Crear la tabla docs (alternativa 1 en HDFS):
```
use usernamedb;
CREATE EXTERNAL TABLE docs (
  line STRING
) 
STORED AS TEXTFILE 
LOCATION 'hdfs://localhost/user/hadoop/datasets/gutenberg-small/';
```
- Crear la tabla docs (alternativa 2 en S3):
```
CREATE EXTERNAL TABLE docs (
  line STRING
) 
STORED AS TEXTFILE 
LOCATION 's3://st0263datasets/gutenberg-small/';
```
- Realizar el conteo de palabras ordenado por palabra:
```
SELECT word, count(1) AS count 
FROM (SELECT explode(split(line,' ')) AS word FROM docs) w 
GROUP BY word 
ORDER BY word DESC 
LIMIT 10;
```
- Realizar el conteo de palabras ordenado por frecuencia (de mayor a menor):
```
SELECT word, count(1) AS count 
FROM (SELECT explode(split(line,' ')) AS word FROM docs) w 
GROUP BY word 
ORDER BY count DESC 
LIMIT 10;
```
- Reto: Almacenar Resultados de un Query en una Tabla
- Para almacenar el diccionario de frecuencia de palabras en una nueva tabla, puedes hacer lo siguiente:
- Crear una nueva tabla para los resultados:
```
use usernamedb;
CREATE TABLE wordcount_results (
  word STRING, 
  count INT
) 
STORED AS TEXTFILE;
```
- Insertar los resultados del query en la nueva tabla:
```
INSERT INTO TABLE wordcount_results 
SELECT word, count(1) AS count 
FROM (SELECT explode(split(line,' ')) AS word FROM docs) w 
GROUP BY word;
```
- NOTA: Siguiendo esta guía paso a paso, deberías poder conectar y gestionar datos en tu clúster Hadoop usando HIVE y SparkSQL. Desde la configuración inicial y la carga de datos, hasta la ejecución de consultas complejas y la gestión de resultados, esta guía te proporciona una base sólida para trabajar con datos en un entorno de Big Data.

## Resultados Esperados
Se espera obtener un Data Warehouse funcional donde se puedan realizar consultas SQL a los datos almacenados en AWS S3. Se deben haber creado las bases de datos y tablas correspondientes en AWS Glue, y se deben haber realizado consultas exitosas con Athena que permitan extraer información relevante de los datos catalogados.

## Descripción del Ambiente de Desarrollo y Técnico
El ambiente de desarrollo utilizado es AWS, específicamente los servicios de S3, Glue y Athena. Se utilizan los datos proporcionados en GitHub, los cuales se ingieren manualmente a S3. Luego, se utilizan las funcionalidades de Glue para catalogar los datos y crear las tablas correspondientes en las bases de datos onudb y tickitdb. Finalmente, se utilizan las capacidades de consultas SQL de Athena para realizar análisis de los datos almacenados en el Data Warehouse.
