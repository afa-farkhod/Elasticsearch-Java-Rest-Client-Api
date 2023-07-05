# [Elasticsearch-Java-Rest-High-Level-Client-Api](https://www.elastic.co/guide/en/elasticsearch/client/java-api-client/current/installation.html)
Elasticsearch Java Rest High Level Client Api

- [Elasticsearch Java API Client](https://www.elastic.co/guide/en/elasticsearch/client/java-api-client/current/index.html) - Documentation which provides the Java API client
- [Java Low Level REST Client](https://www.elastic.co/guide/en/elasticsearch/client/java-api-client/current/java-rest-low.html) - The low-level client’s features include:
  - minimal dependencies
  - load balancing across all available nodes
  - failover in case of node failures and upon specific response codes
  - failed connection penalization (whether a failed node is retried depends on how many consecutive times it failed; the more failed attempts the longer the client will wait before trying that same node again)
  - persistent connections
  - trace logging of requests and responses
  - optional automatic discovery of cluster nodes
  - `Maven` dependency (`pom.xml`):
    
    ```
       <dependency>
            <groupId>org.elasticsearch.client</groupId>
            <artifactId>rest</artifactId>
            <version>5.5.3</version>
        </dependency>
    ```
- [Java High Level REST Client](https://www.elastic.co/guide/en/elasticsearch/client/java-rest/current/java-rest-high.html) - The High Level REST Client is deprecated in favour of the Java API Client(`Decrecated in v.7.15.0`).
  - The Java High Level REST Client works on top of the Java Low Level REST client. Its main goal is to expose API specific methods, that accept request objects as an argument and return response objects, so that request marshalling and response un-marshalling is handled by the client itself.
  - Each API can be called synchronously or asynchronously. The synchronous methods return a response object, while the asynchronous methods, whose names end with the async suffix, require a listener argument that is notified (on the thread pool managed by the low level client) once a response or an error is received.
  - The Java High Level REST Client depends on the Elasticsearch core project. It accepts the same request arguments as the TransportClient and returns the same response objects.
  - `Maven` dependency (`pom.xml`):
    
    ```
       <dependency>
            <groupId>org.elasticsearch.client</groupId>
            <artifactId>elasticsearch-rest-high-level-client</artifactId>
            <version>7.9.2</version>
        </dependency>
    ```
- [Installation in a Maven project by using Jackson](https://www.elastic.co/guide/en/elasticsearch/client/java-api-client/current/installation.html#maven) - Elasticsearch uses Jackson as its default JSON library for serializing and deserializing JSON data. Jackson is a popular Java library for working with JSON, providing functionalities to convert Java objects to JSON and vice versa.
  
```
      <dependency>
            <groupId>com.fasterxml.jackson.core</groupId>
            <artifactId>jackson-databind</artifactId>
            <version>2.13.0</version>
        </dependency>
```
