This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Running only the Camel context

local : jbang "-Dcamel.jbang.version=4.7.0" camel@apache/camel run *


## Running the application in dev mode (TO RUN in your LAPTOP)


You can run your application in dev mode that enables live coding using:
```shell script
./mvnw compile quarkus:dev
```

> **_NOTE:_**  Quarkus now ships with a Dev UI, which is available in dev mode only at http://localhost:8080/q/dev/.

## Packaging and running the application

The application can be packaged using:
```shell script
./mvnw package
```
It produces the `quarkus-run.jar` file in the `target/quarkus-app/` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `target/quarkus-app/lib/` directory.

The application is now runnable using `java -jar target/quarkus-app/quarkus-run.jar`.

If you want to deploy on OpenShift (oc login is required) check the parameters on application-prod.properties build and execute the following command:
```shell script
mvn clean package -Popenshift -DSkiptest

```
# Testing the application in dev mode (for prod you should change the localhost by the OpenShift Route URL generated)

## TRUE NIPC

    POST http://localhost:8081/resquest
    {
        "name":"mysurnam108",
        "nipc": "123456789",
        "comment": "XXXXXXXX"
    }

will see:

    {
        "correlationId": "DF1B10D3A509B6B-0000000000000000",
        "name": "mysurnam108",
        "result": "true"
    }

## FALSE NIPC

    POST http://localhost:8081/request
    {
        "name":"mysurnam110",
        "nipc": "523456789",
        "comment": "XXXXXXXX"
    }

will see:

    {
        "correlationId": "E27851B127F3261-0000000000000003",
        "name": "mysurnam110",
        "result": "false"
    }



This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .


## Related Guides

- OpenShift ([guide](https://quarkus.io/guides/deploying-to-openshift)): Generate OpenShift resources from annotations
- Camel Core ([guide](https://access.redhat.com/documentation/en-us/red_hat_build_of_apache_camel/4.4/html/red_hat_build_of_apache_camel_for_quarkus_reference/camel-quarkus-extensions-reference#extensions-core)): Camel core functionality and basic Camel languages: Constant, ExchangeProperty, Header, Ref, Simple and Tokenize
- Camel Kafka ([guide](https://access.redhat.com/documentation/en-us/red_hat_build_of_apache_camel/4.4/html/red_hat_build_of_apache_camel_for_quarkus_reference/camel-quarkus-extensions-reference#extensions-kafka)): Sent and receive messages to/from an Apache Kafka broker
- Camel MicroProfile Health ([guide](https://access.redhat.com/documentation/en-us/red_hat_build_of_apache_camel/4.4/html/red_hat_build_of_apache_camel_for_quarkus_reference/camel-quarkus-extensions-reference#extensions-microprofile-health)): Expose Camel health checks via MicroProfile Health
- Camel Infinispan ([guide](https://access.redhat.com/documentation/en-us/red_hat_build_of_apache_camel/4.4/html/red_hat_build_of_apache_camel_for_quarkus_reference/camel-quarkus-extensions-reference#extensions-infinispan)): Read and write from/to Infinispan distributed key/value store and data grid
- Camel Netty-HTTP ([guide](https://docs.redhat.com/en/documentation/red_hat_build_of_apache_camel/4.4/html/red_hat_build_of_apache_camel_for_quarkus_reference/camel-quarkus-extensions-reference#extensions-netty-http)): HTTP transport on top of Netty    