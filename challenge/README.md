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

- You have an organization that consists of two lines of business:

    - Finance

    - HR

- The organization has TWO types of roles PER line of business: managers and analysts

- EACH line of business has a SINGLE managed database named after itself

- Managers can create and write tables on their own database and read data from all databases

- Analysts can only read data on their line of business database

- The data for each line of business will be encrypted in HDFS

- Create all the Sentry SQL you need to restrict access (you can name the groups, databases, roles, etc. whatever you want provided it is clear what each represents)


- Describe what is required to ensure data is encrypted and ensure managers and analysts can read data from HDFS and Hive

- Describe the capabilities of Navigator Audit, Lineage, and Metadata. What is it useful for?

- Which technology would you use for encrypting Kafka, Kudu and Flume volumes?
