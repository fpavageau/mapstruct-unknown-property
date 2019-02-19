# Reproducer for a MapStruct bug with 1.3.0.Final

## Prerequisites

- JDK 8

## Build

    ./gradlew build
    
The build should fail with

    > Task :compileJava FAILED
    /some/path/mapstruct-unknown-property/src/main/java/com/ekino/mapstruct/MyMapper.java:26: error: Unknown property "lastModifiedDate" in result type com.ekino.mapstruct.MyEntity. Did you mean "null"?
        MyEntity myDtoToMyEntity(MyDto myDto);
                 ^
    1 error
    
The same code compiles with MapStruct 1.2.0.Final.

It also compiles with MapStruct 1.3.0.Final if the `builder()` method is commented out in `MyEntity.java`.
    
----

Licensed under the Apache License, Version 2.0
