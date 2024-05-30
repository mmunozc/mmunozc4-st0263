### Info de la Materia: Topicos Especiales en Telematica-st0263

### Estudiante:
- Miguel Angel Martinez Florez, mamartinef@eafit.edu.co

### Profesor:  Edwin Nelson Montoya Munera, emontoya@eafit.edu.co  

# Laboratorio 3-3: Implementación de una Data Warehouse con AWS REDSHIFT y REDSHIFT SPECTRUM

##  Objetivo
El objetivo de este laboratorio es aprender a implementar un Data Warehouse utilizando AWS Redshift y Redshift Spectrum. Se realizará la carga de datos en Redshift 
desde archivos planos ubicados en Amazon S3, y se ejecutarán consultas SQL en la base de datos de ejemplo 'tickit' para realizar análisis de datos.

## Descripción de la Actividad 
En este laboratorio, se seguirán los siguientes pasos:

- Crear un cluster de Redshift en la consola de AWS.
- Configurar el cluster y realizar la carga inicial de la base de datos de ejemplo 'tickit'.
- Configurar Redshift Spectrum para acceder a datos externos en Amazon S3.
- Ejecutar consultas SQL en Redshift para realizar análisis de datos en la base de datos 'tickit'.

## Guia paso a paso 
- Crear un cluster y ejecutar consultas básicas en la base de datos demo ‘tickit’:
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/d97fb708-14b0-4cf9-9f90-ce687e15837f)

- Al ingresar al Amazon Redshift, debes darle click a la opción "Crear Cluster":
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/de3a24ba-0713-4a52-899f-c12feecec138)

- Configura el cluster de la siguiente manera:
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/60db2d4c-8a09-44cf-b3e0-34697e4b68a6)
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/10d3c28d-2dc7-448d-9e48-5a17309bf030)
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/094c3ffd-7814-4eda-bd2f-021840b9d4ac)
- Ingresas un usuario y contraseña (Recuerdalo ya que se utilizara mas adelante)
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/3d9fb572-1502-4e30-963b-4a4dd2ca3143)
- Asignamos los tres roles respectivos para los permisos:
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/b52eca39-7cfd-4f10-b090-ffa5700886ea)
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/49ae5f5f-1170-423f-9710-a197ad5b4920)
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/5c1a3fe7-8d06-4ed3-8ec6-7c62e2175621)
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/aeb36c9a-de21-4bbf-b9bd-06d251ea10e6)
- Darle a la opción craer Cluster
- Esperamos unos minutos, hasta que el cluster este creado.
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/3862d2d6-2785-4b90-97b0-ce6660f465af)
- Hacemos clic en el nombre del clúster para acceder a las configuraciones.
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/8cb9f428-a248-41b8-b88b-6ef3d7103c87)
- Al acceder, revisamos en la parte superior derecha un botón llamado "Query data". Hacemos clic en ese botón y seleccionamos la opción "Query in query editor v2".
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/a0ce9d66-9495-4f1e-9002-edd1a04f5acf)
- Al ingresar, veremos la siguiente página:
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/8b5ab68e-7925-4c0a-935c-394b90e8fb92)
- Nos dirigimos al apartado donde aparece el nombre de nuestro clúster y hacemos clic en los tres puntos. Luego, seleccionamos la opción "Create connection".
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/4f503c28-5470-4319-b1c2-4af349827394)
- Seleccionamos la cuarta opción, "Database user name and password," para iniciar la conexión. A continuación, ingresamos el "user name" y la "password" que habíamos creado previamente en el clúster.
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/de26d367-5c96-49a8-a58d-eacc9a4452ef)
- Hacemos clic en la opción "Create connection".
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/9282cf0c-7ab0-43a9-971a-a5e394e21181)
- Se cargaran las carpetas y archivos correspondientes para realizar las consultas.
- Nos dirigimos a la carpeta "sample_data_dev" y damos click en la subcarpeta "tickit" en la opcion "open sample notebooks".
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/e8dd63b4-e227-40aa-8f8c-6f68eaea50f4)
- Hacemos clic en la opción "Create".
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/4c08300f-4bef-4493-92f7-b560bf4514dc)
- Creación de tablas externas y consultas a esos datos como si estuvieran en la base de datos Redshift, permitiendo análisis de datos distribuidos entre Redshift y S3.
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/9b9d8fce-6eef-498b-8b94-3384ddad77e6)

- Ejmeplos de las consultas: 
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/5683bdbd-0326-4c19-bb3b-416669a26a9e)

![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/57e7a96a-0417-4d4a-93ba-7b39c4a9c741)

![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/96ff0319-1b8c-4a77-8ac0-fb6bf240a362)

![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/870f2a2e-e36d-4b4d-8a9d-0b4517104510)

- Terminamos el laboratorio
- NOTA: Recuerde que debe pausar o borrar el clúster si no va a trabajar más, ya que seguirá cobrando incluso después de terminar el laboratorio de AWS Academy.

- REDSHIFT SPECTRUM (opcional)
Redshift Spectrum: consultas de datos en S3 a través de Redshift.
Referencia: Documentación de Redshift Spectrum (https://docs.aws.amazon.com/redshift/latest/dg/c-getting-started-using-spectrum.html)

- Crear un rol IAM para Amazon Redshift:
  - Abrir la consola de IAM.
  - En el panel de navegación, seleccionar "Roles".
  - Hacer clic en "Crear rol".
  - Seleccionar "AWS service", luego elegir "Redshift".
  - En "Select your use case", elegir "Redshift - Customizable" y luego hacer clic en "Siguiente: Permisos".
  - En la página "Attach permissions policy", seleccionar "AmazonS3ReadOnlyAccess",   "AWSGlueConsoleFullAccess" y "AmazonAthenaFullAccess". Luego, hacer clic en "Siguiente: Revisar".
 
- Configurar el rol:
  - En "Role name", ingresar "myspectrum_role".
  - Revisar la información y luego hacer clic en "Crear rol".
  - En el panel "Roles", seleccionar el rol recién creado y copiar el Role ARN al portapapeles. Este ARN será utilizado al crear la tabla externa en Amazon S3.
 
Nota: En la cuenta de AWS Academy, no se permite crear usuarios, grupos ni roles, por lo que recibirá un mensaje de error si intenta hacerlo.
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/e960de3c-53ae-44eb-aa1c-aa20b6ed5917)


- Pero para crear la tabla externa en Redshift Spectrum, puede usar el rol predeterminado 'LabRole', que ya ha sido configurado durante la instalación del clúster 'redshift-cluster-1'.
- Para actualizar el ARN del 'LabRole', siga estos pasos:
  - Acceda al servicio IAM en la consola de AWS.
  ![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/54142e1c-209c-4217-942b-982a68d57a6f)

  - Busque 'LabRole' en la lista de roles y selecciónelo.
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/040faf19-3857-4164-9c6a-be687e83b606)

  - Ingresamos a 'LabRole'.
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/e8cb5279-dda1-4eef-8546-408d7363f52a)

  - Copie el nuevo ARN del 'LabRole'.
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/d9c0311e-cbde-4dee-9b5b-cdbb59c56735)

- Este ARN será utilizado al crear la tabla externa en Redshift Spectrum.
- Nuevo ARN : arn:aws:iam::851725175559:role/LabRole
- Volvemos al editor SQL v2:
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/79026d57-82e1-4509-811d-b5c36f8c7baa)

- Crear la base de datos externa:
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/6ffeca35-18f2-4c60-a114-6ccebf29ba86)
  ```
  create external schema myspectrum_schema 
  from data catalog 
  database 'myspectrum_db' 
  iam_role 'arn:aws:iam::433075868803:role/LabRole'
  create external database if not exists;
  ```  

- Crear una tabla con datos externos en S3:
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/830882cf-fd9e-4aac-865e-8f84a4607d9e)
  ```
  create external table myspectrum_schema.sales(
  salesid integer,
  listid integer,
  sellerid integer,
  buyerid integer,
  eventid integer,
  dateid smallint,
  qtysold smallint,
  pricepaid decimal(8,2),
  commission decimal(8,2),
  saletime timestamp)
  row format delimited
  fields terminated by '\t'
  stored as textfile
  location 's3://emontoyadatalake/datasets/tickitdb2/sales/'
  table properties ('numRows'='172000');
  
  ```

- Consultar datos:
```
select count(*) from myspectrum_schema.sales;
```

- Crear una tabla nativa en Redshift para combinarla con la tabla externa en una consulta:
![image](https://github.com/migueflorez10/Laboratorio_3-3/assets/68928440/c9b161aa-f55a-40ce-82a4-be61e338c516)

  ```
  create table event2(
  eventid integer not null distkey,
  venueid smallint not null,
  catid smallint not null,
  dateid smallint not null sortkey,
  eventname varchar(200),
  starttime timestamp);
  ```

- Cargar datos en la tabla 'event2':
```
COPY event2 FROM 's3://emontoyadatalake/datasets/tickitdb2/events/allevents.txt'
iam_role 'arn:aws:iam::433075868803:role/LabRole'
delimiter '|' timeformat 'YYYY-MM-DD HH:MI:SS' region 'us-east-1';
```

- Realizar una consulta con tablas externas y nativas:
```
select top 10 myspectrum_schema.sales.eventid, sum(myspectrum_schema.sales.pricepaid) 
from myspectrum_schema.sales, event2
where myspectrum_schema.sales.eventid = event2.eventid
and myspectrum_schema.sales.pricepaid > 30
group by myspectrum_schema.sales.eventid
order by 2 desc;
```

- **ADVERTENCIA:** Recuerde pausar o borrar el clúster si no va a trabajar más, ya que seguirá cobrando incluso después de terminar el laboratorio de AWS Academy.


## Resultados Esperados
- Configurar un cluster de Redshift y acceder a él utilizando herramientas de consulta en la consola de AWS.
- Cargar datos en el cluster desde Amazon S3 y ejecutar consultas SQL para analizar esos datos.
- Configurar Redshift Spectrum para acceder a datos externos y realizar consultas distribuidas entre Redshift y S3.
- Tener una comprensión práctica de cómo implementar y utilizar un data warehouse en AWS, lo cual es esencial para el análisis y la gestión eficiente de grandes volúmenes de datos en la nube.


## Descripción del Ambiente de Desarrollo y Técnico
Para este laboratorio, se utilizarán los siguientes recursos:

- AWS Account: Se requiere una cuenta de AWS para acceder a los servicios.
- AWS Redshift: Se utilizará Redshift como el Data Warehouse principal.
- Amazon S3: Se utilizará S3 para almacenar archivos planos y acceder a ellos a través de Redshift Spectrum.
- Dataset 'tickit': Se utilizará el dataset 'tickit' como ejemplo de base de datos para realizar consultas SQL. (https://docs.aws.amazon.com/redshift/latest/gsg/samples/tickitdb.zip)
