# Security Challenge

 Proof that no sssd, kerberos, tls, etc. are created
 <a href="EVIDENCIA_KERBEROS-SSD.png">KERBEROOS SSSD</a>
<a href="EVIDENCIA_TLS.png">TLS</a>
- Send me FQDNs of hosts I will issue certs

- Kerberize cluster
<a href="kdc.conf">kdc.conf</a>
<a href="kadm5.acl">kadm5.acl</a>
<a href="kdc.conf">kdc.conf</a>
- Enable TLS for CM, CM agents, Hive, HDFS (including DNs), and YARN!
<br><a href="https.png">https</a>
<br><a href="config.ini">Config.ini</a>
<br><a href="tlshost.PNG">Green Agentes</a>
- You have an organization that consists of two lines of business:

    - Finance

    - HR

- The organization has TWO types of roles PER line of business: managers and analysts



- EACH line of business has a SINGLE managed database named after itself

- Managers can create and write tables on their own database and read data from all databases

- Analysts can only read data on their line of business database

- The data for each line of business will be encrypted in HDFS

- Create all the Sentry SQL you need to restrict access (you can name the groups, databases, roles, etc. whatever you want provided it is clear what each represents)

<br>CREATE ROLE managers;
<br>GRANT ROLE managers TO GROUP managers;
<br>CREATE ROLE analysts;
<br>GRANT ROLE analysts; TO GROUP analysts;
<br>GRANT ALL ON DATABASE admins TO ROLE admins;
<br>GRANT ALL ON DATABASE analysts TO ROLE analysts;
<br>GRANT ALL ON DATABASE managers TO ROLE managers;
<br> GRANT SELECT ON DATABSE business TO ROLE analysts;
<br> GRANT SELECT ON DATABSE analysts TO ROLE managers;


- Describe what is required to ensure data is encrypted and ensure managers and analysts can read data from HDFS and Hive
Tener habilitado HDFS Transparent Encryption en el clúster con todas sus dependecias (KMS KTS),cifrar carpeta warehouse
por subcarpeta con nombre de base de datos de cada area ,para asi restringir el acceso a nivel hdfs ,y compartir los acl 
para que quien pueda leer lea

- Describe the capabilities of Navigator Audit, Lineage, and Metadata. What is it useful for?
<br>Navigator Audit->Gobierno de datos y audiotria de cl'uster ,permite ver quienes se han logueado ,quienes han fallado el logging
que se esta ejecutando ,y demas llegando a una granularidad de query 

<br>Navigator Linage -> Saber el linage de los datos ,así como las trasformaciones que surguen de el .Permite ver quien y que tranforma la data ,asi como cual es su output 

<br>Navigator Metadata. -->Permite conocer la metadata a nuestros datoa así como cambiar los nombres de estas para que un usuario de negocio pueda entenderlas ,sin que este cambio se refleje en la data .



- Which technology would you use for encrypting Kafka, Kudu and Flume volumes?
Navigator Encrypt
