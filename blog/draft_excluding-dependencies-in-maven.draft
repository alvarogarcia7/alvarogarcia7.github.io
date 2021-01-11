---
published: false
categories:
  - sample
  - mvn
  - maven
  - dependency
  - protip
  - coderwall
---

This is a draft sample

TODO: maybe publish to coderwall then link from here


````
SLF4J: Detected both log4j-over-slf4j.jar AND slf4j-log4j12.jar on the class path, preempting StackOverflowError. 
SLF4J: See also http://www.slf4j.org/codes.html#log4jDelegationLoop for more details.

java.lang.ExceptionInInitializerError
	at org.apache.log4j.LogManager.getLogger(LogManager.java:45)
	at org.slf4j.impl.Log4jLoggerFactory.getLogger(Log4jLoggerFactory.java:66)
	at org.slf4j.LoggerFactory.getLogger(LoggerFactory.java:270)
	at org.apache.commons.logging.impl.SLF4JLogFactory.getInstance(SLF4JLogFactory.java:156)
	at org.apache.commons.logging.impl.SLF4JLogFactory.getInstance(SLF4JLogFactory.java:132)
	at org.apache.commons.logging.LogFactory.getLog(LogFactory.java:274)
	at org.springframework.test.context.junit4.SpringJUnit4ClassRunner.<clinit>(SpringJUnit4ClassRunner.java:86)
	at sun.reflect.NativeConstructorAccessorImpl.newInstance0(Native Method)
	at sun.reflect.NativeConstructorAccessorImpl.newInstance(NativeConstructorAccessorImpl.java:62)
	at sun.reflect.DelegatingConstructorAccessorImpl.newInstance(DelegatingConstructorAccessorImpl.java:45)
	at java.lang.reflect.Constructor.newInstance(Constructor.java:422)
	at org.junit.internal.builders.AnnotatedBuilder.buildRunner(AnnotatedBuilder.java:104)
	at org.junit.internal.builders.AnnotatedBuilder.runnerForClass(AnnotatedBuilder.java:86)
	at org.junit.runners.model.RunnerBuilder.safeRunnerForClass(RunnerBuilder.java:59)
	at org.junit.internal.builders.AllDefaultPossibilitiesBuilder.runnerForClass(AllDefaultPossibilitiesBuilder.java:26)
	at org.junit.runners.model.RunnerBuilder.safeRunnerForClass(RunnerBuilder.java:59)
	at org.junit.internal.requests.ClassRequest.getRunner(ClassRequest.java:33)
	at org.junit.internal.requests.FilterRequest.getRunner(FilterRequest.java:36)
	at com.intellij.junit4.JUnit4IdeaTestRunner.startRunnerWithArgs(JUnit4IdeaTestRunner.java:41)
	at com.intellij.rt.execution.junit.JUnitStarter.prepareStreamsAndStart(JUnitStarter.java:212)
	at com.intellij.rt.execution.junit.JUnitStarter.main(JUnitStarter.java:68)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at com.intellij.rt.execution.application.AppMain.main(AppMain.java:140)
Caused by: java.lang.IllegalStateException: Detected both log4j-over-slf4j.jar AND slf4j-log4j12.jar on the class path, preempting StackOverflowError. See also http://www.slf4j.org/codes.html#log4jDelegationLoop for more details.
	at org.apache.log4j.Log4jLoggerFactory.<clinit>(Log4jLoggerFactory.java:50)
	... 26 more
````

```bash
mvn clean dependency:tree |less
```

find this:

````
[INFO] +- org.springframework.boot:spring-boot-starter-jersey:jar:1.2.3.RELEASE:test
[INFO] |  +- org.springframework.boot:spring-boot-starter:jar:1.2.3.RELEASE:test
[INFO] |  |  +- org.springframework.boot:spring-boot:jar:1.2.3.RELEASE:test
[INFO] |  |  +- org.springframework.boot:spring-boot-autoconfigure:jar:1.2.3.RELEASE:test
[INFO] |  |  +- org.springframework.boot:spring-boot-starter-logging:jar:1.2.3.RELEASE:test
[INFO] |  |  |  +- org.slf4j:jul-to-slf4j:jar:1.7.11:test
[INFO] |  |  |  \- org.slf4j:log4j-over-slf4j:jar:1.7.11:test
[INFO] |  |  \- org.yaml:snakeyaml:jar:1.14:test
````

then exclude your dependencies as needed:

````xml
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-jersey</artifactId>
  <exclusions>
    <exclusion>
      <groupId>org.hibernate</groupId>
      <artifactId>hibernate-validator</artifactId>
    </exclusion>
    <exclusion>
      <groupId>org.slf4j</groupId>
      <artifactId>log4j-over-slf4j</artifactId>
    </exclusion>
  </exclusions>
  <scope>test</scope>
  <version>1.2.3.RELEASE</version>
</dependency>
````
