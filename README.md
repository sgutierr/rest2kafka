# Use Case 1


This repo contains files used for implemeting the use case 1:

## Camel
    
   There are 2 folders representing the Camel integration, both work in the RH environment with Kafka cluster in openshift and Data Grid running locally (Development/software/datagrid/redhat-datagrid-8.5.0-server/bin$/server.sh) :

    1- http2kafkaprotype: contains the YAML DSL.  
    2- http2kafka: quarkus project.

In order to run on different environment is required to modify the endpoints of the Camel routes


## DataGrid (Infinispan)

   Installation files and configruation for OpenShift

## Kafka

   Install the Streams for Apache Kafka operator
   Installation files used to install Kafka, Kafka Console and Prometheus
