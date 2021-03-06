# Benchmark tool

## Build the benchmarking tool

```bash
git clone https://github.com/Azure/azure-cosmosdb-java.git
cd azure-cosmosdb-java

mvn clean package -DskipTests
```

and then the package will be generated. 

## Run the Write workload

```bash
java -jar benchmark/target/azure-cosmosdb-benchmark-1.0.1-SNAPSHOT-jar-with-dependencies.jar -serviceEndpoint ENDPOINT -masterKey MASTERKEY -databaseId DATABASE_ID -collectionId COLLECTION_ID -numberOfOperations 100000 -operation Write -maxConnectionPoolSize 3000 -consistencyLevel "Eventual"
```

You can provide ``--help`` to the tool to see the list of other work loads (read, etc) and other options. 

## Further Improvements

For a higher throughput, please look at https://github.com/Azure/azure-cosmosdb-java#use-native-ssl-implementation-for-netty.
Under optimal conditions, we see 43k inserts per second for documents of size 1 KB.
