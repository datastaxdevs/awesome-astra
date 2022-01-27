# Working with Astra DB and `Pentaho Data Integration`

*This article was originally written by **Erick ramirez** on [community.datastax.com](https://community.datastax.com/articles/12289/how-to-connect-to-astra-db-from-pentaho-data-integ.html)*

<img src="img/logo-pentaho.png" height="100px" />

[🏠 Back to LIST](../README.MD)

## Overview

<img src="img/pdi.png" height="100px" />

Pentaho Data Integration (PDI) provides the Extract, Transform, and Load (ETL) capabilities that facilitate the process of capturing, cleansing, and storing data using a uniform and consistent format that is accessible and relevant to end users and IoT technologies.

- ℹ️ [Introduction to PDI](https://blog.knoldus.com/introduction-to-pdi/)
- 📥 [PDI Download Link](https://sourceforge.net/projects/pentaho/)
- 📘 [Installation Guide on Linux](https://www.hitachivantara.com/en-us/pdf/white-paper/pentaho-ce-installation-guide-on-linux-operating-system-whitepaper.pdf)
- 📘 [Installation Guide on Windows](https://www.hitachivantara.com/en-us/pdf/white-paper/pentaho-community-edition-installation-guide-for-windows-whitepaper.pdf)
  
## Prerequisites

- [Create an Astra Database]()

- [Create an Astra Token]()

- [Download and install PDI](https://sourceforge.net/projects/pentaho/)

This article was written for version `9.1` on `MacOS` but it should also work for the Windows version.

## Installation and Setup

- Micronaut Cassandra configuration using 3x
- Micronaut Cassandra using 4x, the latest

- [Working Sample](https://github.com/clun/astra-native-java/tree/main/astra-todo-micronaut)

- [Micronaut Cassandra documentation](https://micronaut-projects.github.io/micronaut-cassandra/latest/guide/)


## Sample `pom.xml`

```xml
<dependency>
      <groupId>io.micronaut.cassandra</groupId>
      <artifactId>micronaut-cassandra</artifactId>
      <scope>compile</scope>
</dependency>
```

## Sample Configuration File

```yaml
# Astra
cassandra:
  default:
    basic:
      request:
        timeout: 5 seconds
        consistency: LOCAL_QUORUM
        page-size: 5000
      session-keyspace: native_java
      cloud:
        secure-connect-bundle: /Users/cedricklunven/Downloads/secure-connect-workshops.zip
    advanced:
      auth-provider:
        class: PlainTextAuthProvider
        username: token
        password: YOUR_TOKEN
      connection:
        init-query-timeout: 10 seconds          
        set-keyspace-timeout: 10 seconds
      control-connection.timeout: 10 seconds
```

## Sample Code intialize

```java
@Singleton
public class TodoApplicationStartup  implements ApplicationEventListener<ServiceReadyEvent> {

    /** Logger for the class. */
    private static final Logger LOGGER = LoggerFactory.getLogger(TodoApplicationStartup.class);
    
    @Property(name = "todo.cassandra.create_schema", defaultValue="false")
    private boolean createTable;
    
    @Inject 
    private CqlSession cqlSession;
    
    /** {@inheritDoc} */
    @Override
    public void onApplicationEvent(final ServiceReadyEvent event) {
        LOGGER.info("Startup Initialization");
        if (createTable) {
            TodoServiceCassandraCql.createTableTodo(cqlSession);
            LOGGER.info("+ Table TodoItems created if needed.");
        }
        LOGGER.info("[OK]");
```        


