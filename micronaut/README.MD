# Micronaut

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


