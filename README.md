Embedded Broker
===============

Provides an easy way to set up an embedded ActiveMQ messaging broker for use in an
Apache Camel project.

Include the context.xml by using:

    <!-- Import the embedded broker settings. -->
    <import resource="classpath:META-INF/spring/embedded-broker-context.xml" /> 

The default port is `8200` and can be overidden by setting the `embedded-broker.port` 
property.

A Camel component called `embedded` is initialisd to use the embedded broker. This can
be used from within Camel routes by using the following:

    from("embedded:queue-name")

For more information see the Camel documentation for the JMS endpoint.


