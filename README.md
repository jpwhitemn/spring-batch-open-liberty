# spring-batch-open-liberty
Simple spring batch demo app running on Open Liberty via Spring Boot

Spring Batch code from https://spring.io/guides/gs/batch-processing
Running on Open Liberty via Spring Boot.  Needing the following server.xml

```
<?xml version="1.0" encoding="UTF-8"?>
<server description="new server">

    <featureManager>
    <!-- tag::servlet[] -->
        <feature>servlet-6.0</feature>
    <!-- end::servlet[] -->
    <!-- tag::springboot[] -->
        <feature>springBoot-3.0</feature>
    <!-- end::springboot[] -->
    </featureManager>

    <!-- tag::httpport[] -->
    <httpEndpoint id="defaultHttpEndpoint"
                  host="*"
                  httpPort="9080"
                  httpsPort="9443" />
    <!-- end::httpport[] -->

    <!-- tag::springBootApplication[] -->
    <springBootApplication id="prototype-sbatch"
                           location="thin-prototype-sbatch-0.1.0-SNAPSHOT.jar"
                           name="prototype-sbatch" />
    <!-- end::springBootApplication[] -->

</server>
```

To package and run:
```
./mvnw package
./mvnw liberty:run
```
