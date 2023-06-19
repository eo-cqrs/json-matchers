<img alt="logo" src="https://eo-cqrs.github.io/.github/eo-cqrs.svg" height="100px" />

[![Managed By Self XDSD](https://self-xdsd.com/b/mbself.svg)](https://self-xdsd.com/p/eo-cqrs/json-matchers?provider=github)

[![EO principles respected here](https://www.elegantobjects.org/badge.svg)](https://www.elegantobjects.org)
[![DevOps By Rultor.com](https://www.rultor.com/b/eo-cars/json-matchers)](https://www.rultor.com/p/eo-cqrs/json-matchers)
[![We recommend IntelliJ IDEA](https://www.elegantobjects.org/intellij-idea.svg)](https://www.jetbrains.com/idea/)
<br>

[![mvn](https://github.com/eo-cqrs/json-matchers/actions/workflows/mvn.yaml/badge.svg)](https://github.com/eo-cqrs/json-matchers/actions/workflows/mvn.yaml)
[![maven central](http://maven-badges.herokuapp.com/maven-central/io.github.eo-cqrs/json-matchers/badge.svg)](https://search.maven.org/artifact/io.github.eo-cqrs/json-matchers)
[![javadoc](https://javadoc.io/badge2/io.github.eo-cqrs/json-matchers/javadoc.svg)](https://javadoc.io/doc/io.github.eo-cqrs/json-matchers)
[![codecov](https://codecov.io/gh/eo-cqrs/json-matchers/branch/master/graph/badge.svg?token=biuAgXDIEX)](https://codecov.io/gh/eo-cqrs/json-matchers)

[![Hits-of-Code](https://hitsofcode.com/github/eo-cqrs/json-matchers)](https://hitsofcode.com/view/github/eo-cqrs/json-matchers)
[![Lines-of-Code](https://tokei.rs/b1/github/eo-cqrs/json-matchers)](https://github.com/eo-cqrs/json-matchers)
[![PDD status](http://www.0pdd.com/svg?name=eo-cqrs/json-matchers)](http://www.0pdd.com/p?name=eo-cqrs/json-matchers)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/eo-cqrs/json-matchers/blob/master/LICENSE.txt)

Project architect: [@h1alexbel](https://github.com/h1alexbel)

Hamcrest JSON Matchers.

**Motivation**. We are not happy dealing with JSON matching and assertions in procedural way.
<br>
We offer everything through simple, declarative Hamcrest Matchers.

**Principles**. These are the [design principles](https://www.elegantobjects.org/#principles) behind EOkson.

**How to use**. All you need is this (get the latest
version [here](https://search.maven.org/artifact/io.github.eo-cqrs/json-matchers)):

Maven:
```xml
<dependency>
  <groupId>io.github.eo-cqrs</groupId>
  <artifactId>json-matchers</artifactId>
  <scope>test</scope>
</dependency>
```

Gradle:
```groovy
dependencies {
    testCompile 'io.github.eo-cqrs:json-matchers:<version>'
}
```

### `JsonEqualTo`
Simple, Equality Matcher:

```java
new JsonEqualTo(json)
  .matches("{\"test\": \"123\"}")
);
```
```java
final String compare = new SmartJson(
new MutableJson()
    .with("test", "123")
    .with("test-node", "true")
).pretty();
new JsonEqualTo(json)
  .matches(compare);
```

Each submitted JSON to `JsonEqualTo` transformed into **pretty string**.

## How to Contribute

Fork repository, make changes, send us a [pull request](https://www.yegor256.com/2014/04/15/github-guidelines.html).
We will review your changes and apply them to the `master` branch shortly,
provided they don't violate our quality standards. To avoid frustration,
before sending us your pull request please run full Maven build:

```bash
$ mvn clean install
```

You will need Maven 3.8.7+ and Java 17+.

Our [rultor image](https://github.com/eo-cqrs/eo-kafka-rultor-image) for CI/CD.
