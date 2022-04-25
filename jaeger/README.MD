# Working with Astra DB and `Jaeger`

<img src="img/logo.svg" height="100px" />

[🏠 Back to LIST](../README.MD)

## Overview

- Cassandra provides pluggable tracing starting from version 3.4. 
- By adding a jar file to the Cassandra classpath and one JVM option, Cassandra's tracing can be replaced with Jaeger. It can even identify incoming Jaeger traces and add Cassandra's own internal tracing on to it.

### Instructions for `Cassandra`

Will adapt the instructions from the following Github repo to be able to use Astra DB.

https://github.com/infracloudio/cassandra-jaeger-tracing