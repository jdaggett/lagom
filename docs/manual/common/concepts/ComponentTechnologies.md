# Component technologies

As a complete microservices platform, Lagom assembles a collection of technologies and adds value on top of them. Some of the libraries, tools, and servers that Lagom uses and supports were developed at [Lightbend](https://lightbend.com), others are third-party and open-source. As you develop with Lagom, you can also take advantage of these technologies:

* Akka --- Lagom [[Persistence|PersistentEntity]], [[Publish-Subscribe|PubSub]], and [[Cluster|Cluster]] are implemented on top of [Akka](http://akka.io/), Lightbend's toolkit for building concurrent, distributed, and resilient message-driven applications. (This is an implementation detail that does not directly concern you when developing simple microservices. However, you can call also [[Akka APIs|Akka]] directly.)

    * To scale your microservices out across multiple servers, Lagom provides clustering via [Akka Cluster](http://doc.akka.io/docs/akka/2.4/java/cluster-usage.html).
     
    * As described in [[Implementing services|ServiceImplementation]], A Lagom service may be "simple" or "streamed".  Streaming, asynchronous Lagom services are built on top of [Akka Streams](http://doc.akka.io/docs/akka/2.4/java/stream/index.html).

* Customers of Lightbend's [Reactive Platform](https://www.lightbend.com/products/lightbend-reactive-platform) can additionally use [[Lightbend ConductR|ConductR]] and Akka's [Split Brain Resolver](http://doc.akka.io/docs/akka/akka-commercial-addons-1.0/java/split-brain-resolver.html) for deployment and cluster management and [Lightbend Monitoring](https://www.lightbend.com/products/monitoring) for monitoring production systems. See [[Cluster]] for more details.

* Cassandra --- By default, Lagom microservices that need to persist data use the  [Cassandra](http://cassandra.apache.org) instance that runs as part of the development environment. You can also use an existing [[Cassandra Server|CassandraServer]] database or another type of database. See [[Managing data persistence|ES_CQRS]] for more information.   

* Guice --- Like Play, Lagom uses [Guice](https://github.com/google/guice) for dependency injection.

* Play Framework --- Lagom is implemented on top of [Play Framework](https://www.playframework.com), Lightbend's web framework. This is an implementation detail that does not directly concern you when developing simple microservices.  However, advanced users can call some Play APIs directly. If you have an existing Play Framework application to which you want to add microservices, Lagom provides support for that use case.

* SLF4J & Logback --- Lagom uses [SLF4J](http://www.slf4j.org/) for logging, backed by [Logback](http://logback.qos.ch/) as its default logging engine. See [[Logging]] for more information.

* Typesafe Config Library --- Lagom and many of its component technologies are configured using the [Typesafe Config](https://github.com/typesafehub/config) library.  The configuration file format is [HOCON](https://github.com/typesafehub/config/blob/master/HOCON.md), a powerful and expressive superset of JSON.

* Serialization --- Lagom's recommended serialization format is JSON.  The default engine used for JSON serialization and deserialization used for Java is [Jackson](https://github.com/FasterXML/jackson) and for Scala, [Play JSON](https://www.playframework.com/documentation/2.5.x/ScalaJson). Other serialization formats are also supported.

