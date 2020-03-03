# Enterprise Application Development
## General Information

## Annotations
- @Named - It will ask the container to create an object. This allows us to stray away from having to create objects with ```new```
  - This will be referenced in the batchet

## Connecting to database with JPA
- In the pom.xml file, you need JDBC Drivers
```java
<version.h2database>1.4.200</version.h2database>
<version.mssql-jdbc>8.2.1.jre11</version.mssql-jdbc>
<version.ojdbc10>19.3.0.0</version.ojdbc10>
<version.postgresql>42.2.9</version.postgresql>
<version.mysql-connector-java>8.0.18</version.mysql-connector-java>
<version.mariadb-java-client>2.5.3</version.mariadb-java-client>
<version.derby>10.15.1.3</version.derby>
```
- The persistence.xmlfile allows us to connect to a DB
- The persistence-unit allows us to connect to different types of dbs
- We are able to generate Java classes with the db tables, and also vice versa
  - This is done with with the ```<property name="javax.persistence.schema-generation.database.action" value="create"/>```
  - ``` <!-- database.action or scripts.action value: none, create, drop-and-create, drop --> ``` never use drop-and-create IRL


## Batch Proccessing
- Batch proccessing is proccessing large amounts of data
- Batch proccessing allows us to populate data to a database 
  - There can be many ```<steps>```
  - You set a listener in the batchlet check the different steps of the batch job
- The path MUST be src/main/resources -> META-INF -> batch-jobs
- The name of the xml file is important because it will be called later on to import data
- A batchlet will proccess data and will return either if it fails or is completed
- **The curl command is used to execute batch jobs**
### Batch Proccessing APIS
  - An EntityManager instance is associated with a persistence context. A persistence context is a set of entity instances in       which for any persistent entity identity there is a unique entity instance
- The JobOperater  allows us to perform batch jobs, through the JobOperator a program can start, stop, and restart jobs


