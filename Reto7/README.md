
### Estudiante:
- Mateo Muñoz Cadavid, mmunozc4@eafit.edu.co

### Profesor:  Edwin Nelson Montoya Munera, emontoya@eafit.edu.co  


# Laboratorio 7: Implementación de una Data Warehouse con AWS REDSHIFT y REDSHIFT SPECTRUM

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
- Crear un cluster y ejecutar consultas básicas en la base de datos demo ‘tickit’
- 
- Al ingresar al Amazon Redshift, debes darle click a la opción "Crear Cluster"

- Configura el cluster de la siguiente manera

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/857fee16-d981-4ec1-9ff9-07a551751f6a)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/34a68731-1d3f-4abf-a3dd-f3ddc21a5e68)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/94f2a82d-f1ae-44ef-a2c4-819df56f0d81)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/ff1437f2-bbba-4e40-9629-f66fb0d39776)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/1322e72f-ceed-4936-9bab-508a5e107569)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/7f5545ed-150e-4bdf-a69b-15ca34dc0262)


- Darle a la opción craer Cluster
  
- Esperamos unos minutos, hasta que el cluster este creado.

  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/541447ec-384a-4726-b177-7d783ca8ee8e)

  
- Hacemos clic en el nombre del clúster para acceder a las configuraciones.
  
 ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/97c43f0c-9179-4665-8561-55333810a427)


- Nos dirigimos al apartado donde aparece el nombre de nuestro clúster y hacemos clic en los tres puntos. Luego, seleccionamos la opción "Create connection".

  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/bc8bb54b-a6ed-4afa-a06c-549fa5d69734)

- Seleccionamos la cuarta opción, "Database user name and password," para iniciar la conexión. A continuación, ingresamos el "user name" y la "password" que habíamos creado previamente en el clúster.

 ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/b0da632c-ad8a-491d-8000-6f8040743c75)


- Se cargaran las carpetas y archivos correspondientes para realizar las consultas.

  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/0dd6bc2b-a3fe-4aed-83ca-4c90d76feed1)

  
- Nos dirigimos a la carpeta "sample_data_dev" y damos click en la subcarpeta "tickit" en la opcion "open sample notebooks".

 ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/39d4c21d-76f4-4731-8b5d-d94fe359fcd9)


- Hacemos clic en la opción "Create".

  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/d10ba71b-683a-4219-8ce0-c8064e3c5027)



- Creación de tablas externas y consultas a esos datos como si estuvieran en la base de datos Redshift, permitiendo análisis de datos distribuidos entre Redshift y S3.

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/f3ea1914-b7c8-47f7-ad18-0c9df3f55391)

- Ejmeplos de las consultas:

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/34a9d495-9978-4a7e-94a4-180cf18ead31)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/7793f343-0cdd-4d1a-9bf6-50d76fe10d1b)


### REDSHIFT SPECTRUM 
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
 
  
![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/c33f5d7d-d861-44d7-83a0-5dab51497713)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/149cee83-d8d1-4fc7-873b-b9ac71b4a967)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/cdba7c22-610b-4aa6-98a7-63101fc2f136)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/169e1046-bb9b-4dd1-8ab1-c0ebc01ce3d8)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/eed6b642-c856-4a6d-acc5-c734a200eee7)




 
Nota: En la cuenta de AWS Academy, no se permite crear usuarios, grupos ni roles por lo que al intentarlo le saldra error


![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/ab76a06d-c1c1-46ff-9231-d4c1cf1cfa1e)



- Pero para crear la tabla externa en Redshift Spectrum, puede usar el rol predeterminado 'LabRole', que ya ha sido configurado durante la instalación del clúster 'redshift-cluster-1'.
- Para actualizar el ARN del 'LabRole', siga estos pasos:
  
  - Acceda al servicio IAM en la consola de AWS.
    
  - Busque 'LabRole' en la lista de roles y selecciónelo.
    
  - Ingresamos a 'LabRole'.
    
    ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/196684de-0a0a-4558-a8a4-5cd85d6ff6fb)

  - Copie el nuevo ARN del 'LabRole'.

- Este ARN será utilizado al crear la tabla externa en Redshift Spectrum.
- Nuevo ARN : arn:aws:iam::851725175559:role/LabRole
- Volvemos al editor SQL v2:

- Crear la base de datos externa:

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/272d17c2-e3f2-4666-beb1-e777614f6771)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/39aeb91e-79bd-441e-9309-8711d992b5ee)


  
  ```
  create external schema myspectrum_schema 
  from data catalog 
  database 'myspectrum_db' 
  iam_role 'arn:aws:iam::433075868803:role/LabRole'
  create external database if not exists;
  ```  

- Crear una tabla con datos externos en S3:

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/c1ec3703-7804-4705-8bde-ba58f3a27d2f)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/c96ab26e-faff-4e39-a001-1b21f870441a)


  
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

  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/27587e74-0da0-4fb8-afcc-12f31b3fb51d)


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
