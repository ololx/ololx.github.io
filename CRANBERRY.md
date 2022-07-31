# Cranberry Project

```
             ___/\\ /\  
            / _//| \ /  
           / / / |/ \__ 000   000
           |/ /  / /  000       000
      00 00 _/   |/ 000       ^   000
   00 ^     00   | 000     <  *  > 000  
  00< * >    00 0 0 000       v   000
   00 v     00 0 * 0  000       000
      00 00     0 0     000   000
________________________________________
The Cranberry Project                   
```

The Cranberry is a java library that allows to write less code - it's  automatically plugs into your project build and sweets up your java.

The gif demonstraits how `cranberry` helps to write less code on the checking parameters implementation example for non-emptiness via usage of the `@ NotEmpty` annotation from the `cranberry-statement` module. This is one of opportunities which cranberry provides.

![The demo of cranberry statement usage](https://github.com/ololx/cranberry/blob/assets/demo/cranberry-statements-not-blank-demo-1.gif?raw=true)

[More info](https://ololx.github.io/cranberry/)

## Features

- The api for the statements validation about not null values of the `Object` type;
- The api for the statements validation about not empty values of the `Map` type, the `Collection` type, the `Array` and the `String` type;
- The api for the statements validation about not blank values of the `String` type; 
- The api for the loggint method params;
- The annotations for the injecting methods of this api into code during compilation.

## Maven Installing

1 - Add this dependency to classpath in pom:

```xml
<dependency>
    <groupId>io.github.ololx.cranberry</groupId>
    <artifactId>${module-name}</artifactId>
    <version>${version}</version>
</dependency>
```

_Example of dependency for installing `cranberry-muffin` module with version `0.13.0` is presented bellow_

```xml
<dependency>
    <groupId>io.github.ololx.cranberry</groupId>
    <artifactId>cranberry-muffin</artifactId>
    <version>0.13.0</version>
    <scope>provided</scope>
</dependency>
```

2 - Execute this with goal

```bash
clean install
```

## Usage examples

The simple example below presents the the checking of a parameters on `not null` value without the specific exception message returns and  `not blank` value with the specific exception message returns.

```java
 ...
//Add the checking statements for method params
public List<SomeDetail> findSomeDetailbyUidAndTypeCode(@NotNull Long uid, 
    @NotEmpty("The Type Code must be not empty") String typeCode) {
    return Collections.EMPTY_LIST;
}
...
```

The simple example below presents the the logging of a parameters of method with the specific message.

```java
...
/**
 * The example of {@code @LogParam} annotation usage on {@code List<String> param}.
 * <p>
 * When this method is called, the parameters will be displayed in the log;
 * Messages in the log will label the format {@char "message param"} for each parameter.
 */
@LogParam(message = "Start execution with param =")
public static void runWithCustomMessage(List<String> param) {
    param.stream()
            .forEach(eachParam -> {
                System.out.println(eachParam);
            });
}
...
```
[More examples](https://github.com/ololx/cranberry-examples)
