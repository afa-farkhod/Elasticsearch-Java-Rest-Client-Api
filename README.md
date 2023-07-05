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

## [Java Rest API Connection (Low Level Client & High Level Client)](https://www.elastic.co/guide/en/elasticsearch/client/java-rest/7.17/java-rest-overview.html)

- `HighLevelRestClientRemoteServer` sample inside the folder: `ElasticHighLevelRemote` - First we check Elasticsearch remote server connection with High Level Rest Client. Api allows to enter the index name, field name and value(key word), then runs the `vector search` to bring the related result(ignore the error message, it is just saying that Log4j2 should be updated, api itself works fine):  

<p align="center">
  <img src="https://user-images.githubusercontent.com/24220136/236648733-45a06d69-2a83-4b37-960c-83374e9a4cbe.png" alt="Image">
</p>

- `HighLevelRestClientLocalServer` sample inside the folder: `ElasticHighLevelLocal` - Now we check High Level Rest Client Api Elasticsearch local server. In the case of flowers_dataset data.

<p align="center">
  <img src="https://user-images.githubusercontent.com/24220136/236648733-45a06d69-2a83-4b37-960c-83374e9a4cbe.png" alt="Image">
</p>

- `LowLevelRestCLientRemoteServer` sample inside the folder: `ElasticLowLevelRemote` - is the Low Level Rest Client Api with Elasticsearch remote server: 

<p align="center">
  <img src="https://user-images.githubusercontent.com/24220136/236648990-f6332097-a176-48fb-94d9-0796cf326de0.png" alt="Image">
</p>

- `LowLevelRestClientLocalServer` sample inside the folder: `ElasticLowLevelLocal` - is the Low Level Rest Client Api with Elasticsearch local server:

<p align="center">
  <img src="https://user-images.githubusercontent.com/24220136/236649253-39df4828-341f-49e5-9102-a8b47d74ae95.png" alt="Image">
</p>
