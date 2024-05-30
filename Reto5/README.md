

### Estudiante:
- Mateo Muñoz Cadavid, mmunozc4@eafit.edu.co

### Profesor:  Edwin Nelson Montoya Munera, emontoya@eafit.edu.co  

# Laboratorio 5: GESTIÓN DE ARCHIVOS EN HDFS Y S3 PARA BIG DATA

##  Objetivo
- **Crear un Cluster AWS EMR en Amazon para trabajar todos los laboratorios.**
## Descripción de la Actividad 
- Esta guía describe los pasos necesarios para instalar y configurar un clúster EMR (Elastic MapReduce) en AWS (Amazon Web Services). El objetivo es usar herramientas de big data como Hadoop y Spark para análisis de datos.

## Guia paso a paso 

- Prerrequisitos
  - Antes de iniciar, asegúrate de tener lo siguiente:
    - Una cuenta de AWS.
    - Generar Claves SSH: Crea un nuevo par de claves SSH (si no tienes uno). Guarda la clave privada en tu máquina local para acceder al máster del clúster.

- Iniciar la Creación del Clúster EMR
  - Acceder a EMR: Desde la consola de AWS, navega a EMR.
  - Crear Clúster: Haz clic en "Create cluster".
- Configurar el Clúster de la siguiente manera;
  - Configuración del Catálogo de datos de AWS Glue
  - Versión de EMR: Selecciona la versión 6.14.0
  - Instalar las siguientes aplicaciones
    
  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/b99e32ce-5784-4057-bf1b-66660ca9595c)


- Configurar Persistencia de Notebooks en S3
  - Configurar S3: Para persistir los notebooks creados en JupyterHub, configura un bucket S3.
    
  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/7e69ab97-2d9d-4628-9165-8d28c0f5bc64)



    ```
          [
            {
                "Classification": "jupyter-s3-conf",
                "Properties": {
                    "s3.persistence.enabled": "true",
                    "s3.persistence.bucket": "mmunozcnotebooks"
                }
            }
        ]
    ```
    
- Configuración de Hardware
  - Dejar por defecto las opciones
  
- Finalizar Configuración
  - Clave SSH: Selecciona la clave SSH creada previamente.
    
  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/ec035bba-7c69-4210-9fdf-d4962a353cf0)

  - Rol de servicio de Amazon EMR y Perfil de instancia de EC2 para Amazon EMR deben ser las Default
    
  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/413cc7de-6483-40c3-867a-8afbc504aea1)

  - Rol de escalamiento automático debe ser el determinado para academy
    
  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/58d46476-aa4f-458d-b71a-4904a8305aa9)

  - Crear Clúster: Haz clic en "Create cluster".
    
  - La creación del clúster tomará aproximadamente 20-25 minutos.
  ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/f65ddd3a-0b61-49f6-9eff-f65fe4c51857)


### Con el cluster creado 

- Cambio de los puertos de las instancias
  
 - Accedemos a la instancia master
   
   ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/eb451d80-0d20-4f1c-adaf-23632e7b834c)

   
 - Y modificamos los siguientes puertos:
   
   ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/668015f6-6d9a-49d9-9707-90ffbcfb7ca9)

### Acceso a las aplicaciones - HUE

- Ingresamos a las aplicaciones del cluster y copiamos la direccion correspondiente a HUE y la pegamos en el navegador
  
![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/7a170705-9516-4092-b08c-192b8887e161)
- Creamos usuario y contraseña
  
![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/1cf888ca-ee1d-4398-9cbe-39e222e00cb7)
- Veremos lo siguiente
  
![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/7b4ebc9e-166c-48d9-ae66-6c8f66a1c091)
- Ingresamos a "Files" y veremos el siguiente error
  
![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/000a9cac-aaf7-4949-922d-d9a8416df24b)
- Ingresamos a la terminal de aws
  
![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/0d75ecd1-b91b-4566-b497-6486cac5fedc)

- Conexión al Clúster
  - volvemos a nuestro cluster
    
    ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/74a1589b-6091-49b0-be72-9fd024b2f4e5)
    
  - Conectar al nodo master vía SSH.
      - Damos clic en "Conectarse al nodo principal mediante SSH
        
      ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/ac958e91-7d10-45f1-bddd-2372d63beadb)
    
      - Al momento de dar clic nos aparecera lo siguiente
        
      ![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/b5feb558-a8d5-4719-b350-ebf3550925a9)
    
      - Copiamos la instruccion que nos proporciona
        
- En la termnal
  
  - Pegamos y damos enter
    
  - Posterior mente pegamos los siguientes comandos
    
  ``` sudo sed -i 's/.ec2.internal:14000/.ec2.internal:9870/' /etc/hue/conf/hue.ini```

  ``` sudo systemctl restart hue ```
  
![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/72c1f9e1-b972-470d-9413-36e97e5f88f9)


  ```sudo hdfs dfs -ls /user```
  
  ```sudo -u hdfs hdfs dfs -mkdir /user/admin```
  
  ```sudo -u hdfs hdfs dfs -chown admin:hdfsadmingroup /user/admin```
  
  ```sudo -u hdfs hdfs dfs -chmod 755 /user/admin```
  
  ```sudo systemctl restart hue```

  - NOTA: DONDE DICE ADMIN DEBE DE IR EL NOMBRE DE USUARIO QUE SE CREO 

- Si volvemos a Hue ya veremos lo siguiente:
  
![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/2cca31b2-782f-4c7a-9d54-55e546706ddf)

- Creamos dos directorios de forma tal que queden de la siguiente manera; datasets\onu
  
![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/b61aa20a-06c2-48c4-bb1f-0fc5eb8eb2d0)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/c6c2f7e2-c721-4eab-91c2-2e90dcc1b50c)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/73c843cf-a949-4d48-afd1-1fc22151f4d7)


- Dentro de onu subimos los siguientes archivos que se encuentran en la carpeta datasets

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/ad32cf5d-3e9c-42ef-8a3c-472b108a0b18)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/acad3b31-8226-4301-9a3e-79787ded0c40)

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/4bf66874-5766-474f-bd53-43b1cc99067d)

### Acceso a las aplicaciones - ZEPPELIN

- De la misma forma que se abrio HUE se abre ZEPPELIN y veremos lo siguiente

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/1001d201-904f-4c75-9e1e-537b5bde8d4b)

- Le damos en "Create new note"

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/13d4eaed-e978-4f62-97b6-529f70a8e1e4)

- Para verificar el funcionamiente corremos los siguientes comandos 

![image](https://github.com/mmunozc/mmunozc4-st0263/assets/106570098/17d99cdc-1900-48c2-8497-e472633d46a9)


    
## Resultados Esperados
- Gestión de Archivos en HDFS y S3: Los estudiantes deberán demostrar habilidades prácticas en la gestión de archivos utilizando HDFS y S3 en un entorno de clúster EMR. Se espera que copien y gestionen archivos desde y hacia HDFS usando tanto HUE como SSH. Asimismo, deberán realizar las mismas operaciones con AWS S3. La verificación de estas tareas se hará a través de evidencias de las operaciones completadas, mostrando que los archivos han sido correctamente gestionados en ambos sistemas de almacenamiento.

- Configuración de Accesos Públicos en S3: Cada estudiante deberá configurar los buckets de S3 con acceso de lectura pública. Esto se verificará mediante la comprobación de la accesibilidad de los archivos a través de URLs públicas.

- Documentación y Evidencias: Los estudiantes deberán enviar un informe detallado que incluya las evidencias de las actividades realizadas. Este informe deberá incluir capturas de pantalla y comandos utilizados, así como la URL del bucket público de S3 donde están los datasets. También deberán depositar las evidencias en el formato template distribuido en el OneDrive del curso.


## Descripción del Ambiente de Desarrollo y Técnico
- Cluster EMR: El laboratorio se llevará a cabo en un clúster EMR previamente configurado en el Lab 5. Cada estudiante tiene acceso a su propio servidor EC2 del nodo maestro del clúster EMR, al cual se conectarán mediante SSH para realizar las actividades de gestión de archivos en HDFS. El clúster debe tener HUE activado y un usuario 'hadoop' creado.

- Herramientas Utilizadas:
  - HDFS: Sistema de archivos distribuido utilizado para almacenar grandes volúmenes de datos.
  - Hue: Interfaz web utilizada para gestionar archivos en HDFS y S3 de manera gráfica.
  - SSH: Protocolo utilizado para acceder de forma segura al nodo maestro del clúster EMR y ejecutar comandos de gestión de archivos en HDFS.
  - AWS S3: Servicio de almacenamiento de objetos utilizado para almacenar y recuperar cualquier cantidad de datos en cualquier momento y desde cualquier lugar en la web.
- Comandos y Operaciones:
  - HDFS CLI: Se utilizarán comandos como hdfs dfs -put, hdfs dfs -get, hdfs dfs -copyFromLocal, entre otros, para la gestión de archivos en HDFS.
  - AWS CLI: Se utilizará para copiar archivos hacia y desde AWS S3.
  - Hue: Se utilizará para la gestión gráfica de archivos en HDFS y S3, permitiendo operaciones como subir, descargar y explorar archivos.
- Dataset: Se utilizarán archivos de datos disponibles en el repositorio de GitHub del curso y en el bucket de S3 'st0263datasets'. Los estudiantes deberán copiar estos datasets al HDFS y S3 según se indique en las instrucciones del laboratorio.

- Seguridad y Acceso: Es crucial que los estudiantes configuren el acceso público a los buckets de S3 para permitir la lectura pública de los archivos. Esto se logrará siguiendo las instrucciones disponibles en la documentación de AWS S3.
