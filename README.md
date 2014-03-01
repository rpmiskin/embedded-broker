Embedded Broker
===============

### Overview
Provides an easy way to set up an embedded [ActiveMQ messaging broker](http://activemq.apache.org)
 for use in an [Apache Camel](https://camel.apache.org) project.

### Adding to your project
Download the source and install it locally using:

    mvn clean install

Add a the dependency to your pom using

    <dependency>
        <groupId>in.misk</groupId>
        <artifactId>camel-embedded-broker</artifactId>
        <version>1.0.1-SNAPSHOT</version>
    </dependency>

And finally add the broker to your the context.xml by using:

    <!-- Import the embedded broker settings. -->
    <import resource="classpath:META-INF/spring/embedded-broker-context.xml" /> 

The default port is `8200` and can be overidden by setting the `embedded-broker.port` 
property. See the [example project](https://github.com/rpmiskin/embedded-broker-example/blob/master/src/main/resources/META-INF/spring/internal-broker.properties)
for other configuration options.


### Using the embedded broker in a Camel Route
A Camel component called `embedded` is initialisd to use the embedded broker. This can
be used from within Camel routes by using the following:

    from("embedded:queue-name")

For more information see the Camel documentation for the [ActiveMQ component](https://camel.apache.org/activemq.html).

See the [embedded-broker-example](https://github.com/rpmiskin/embedded-broker-example) project for a working example.
