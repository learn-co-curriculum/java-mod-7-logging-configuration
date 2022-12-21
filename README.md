# Logging Configuration

## Learning Goals

- Manage logging level.

## Logging Level Control

Let's look at how to configure the logging level of our logging framework, which
controls whether a call to the corresponding method will actually result in an
output.

Consider the log levels again from the previous lesson:

1. TRACE
2. DEBUG
3. INFO
4. WARN
5. ERROR

Remember, the higher the logging level, the less information it should output.
Therefore, ERROR will _only_ show error messages whereas TRACE will show the
most detailed output.

We can configure the logging level that we want shown in the
`application.properties` file. Let's add the following line in our
spring-rest-demo project:

```properties
logging.level.root=WARN
```

Restart the application and observe that the output will look something like
this:

```java
/Users/dbash/Library/Java/JavaVirtualMachines/corretto-17.0.3/Contents/Home/bin/java -XX:TieredStopAtLevel=1 -noverify -Dspring.output.ansi.enabled=always -Dcom.sun.management.jmxremote -Dspring.jmx.enabled=true -Dspring.liveBeansView.mbeanDomain -Dspring.application.admin.enabled=true -javaagent:/Applications/IntelliJ IDEA.app/Contents/lib/idea_rt.jar=62255:/Applications/IntelliJ IDEA.app/Contents/bin -Dfile.encoding=UTF-8 -classpath /Users/dbash/sandbox/flatiron/flatiron-spring/build/classes/java/main:/Users/dbash/sandbox/flatiron/flatiron-spring/build/resources/main:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.boot/spring-boot-starter-web/2.7.1/29f47f503f9955b1a9746870aeaebdba448416d/spring-boot-starter-web-2.7.1.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.boot/spring-boot-starter-security/2.7.1/43175965577a1ecc9569fc93f009479cb933fc1e/spring-boot-starter-security-2.7.1.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.security/spring-security-oauth2-resource-server/5.7.2/4ec6f79605ff69d8b01b1df678239f4eb985c549/spring-security-oauth2-resource-server-5.7.2.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.security/spring-security-oauth2-jose/5.7.2/a252fbe76622ce0d1435ef2fb043149346923b4/spring-security-oauth2-jose-5.7.2.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.security/spring-security-oauth2-client/5.7.2/d41f66630e320055ea1fb287bf0ca941bf6058e5/spring-security-oauth2-client-5.7.2.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.webjars/webjars-locator-core/0.50/d1ae68f5fea4f8e36e1d9adfd1ac02463c43894a/webjars-locator-core-0.50.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.webjars/jquery/3.6.0/633447ad320c04c69fb621d08ba2268f50822eee/jquery-3.6.0.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.webjars/bootstrap/5.1.3/b35baad17ca0e57a9dcdb1245a290cc35ff6e7c8/bootstrap-5.1.3.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.boot/spring-boot-starter-json/2.7.1/711889df8474d7f0271b1e25cd75a9249e0a4621/spring-boot-starter-json-2.7.1.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.boot/spring-boot-starter/2.7.1/48f7e04459ccc16d3532bfc486c1b6d629e6e0fc/spring-boot-starter-2.7.1.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.boot/spring-boot-starter-tomcat/2.7.1/c99fe94b685f1707907afb84ecb998ac13271ead/spring-boot-starter-tomcat-2.7.1.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework/spring-webmvc/5.3.21/a62db425cc29c48e138846e706ca37acb138ca13/spring-webmvc-5.3.21.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework/spring-web/5.3.21/317aadd37f70ba34ff93d068343e3110b5dcf2f/spring-web-5.3.21.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.security/spring-security-web/5.7.2/3933d4de5c80b8f6b4711207f2fcfac9020f8aed/spring-security-web-5.7.2.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.security/spring-security-config/5.7.2/aa69c37286d37ffe9a5534210692f986777d6f60/spring-security-config-5.7.2.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework/spring-aop/5.3.21/58ec4ff7a0ce30a1e2612f04ad0fb13ea806705/spring-aop-5.3.21.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.security/spring-security-oauth2-core/5.7.2/1596443a3268e749f4c3db4f6ba02b6e8261e677/spring-security-oauth2-core-5.7.2.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.security/spring-security-core/5.7.2/48cc4cec862ca88ea199f1c98a1b9a8ea5701467/spring-security-core-5.7.2.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework/spring-core/5.3.21/1b0c9be6b972e4c615f175c70fc32e80557e68e8/spring-core-5.3.21.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/com.nimbusds/nimbus-jose-jwt/9.22/bed63628cd31d8641c5a1b29609a965179ef91ec/nimbus-jose-jwt-9.22.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/com.nimbusds/oauth2-oidc-sdk/9.35/7bfdf91bc4ae265f6c49a367bc0ed0e47d0e3a97/oauth2-oidc-sdk-9.35.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.slf4j/slf4j-api/1.7.36/6c62681a2f655b49963a5983b8b0950a6120ae14/slf4j-api-1.7.36.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/io.github.classgraph/classgraph/4.8.139/6932809e00eb69b2321bd3c35e7b61e964714996/classgraph-4.8.139.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/com.fasterxml.jackson.core/jackson-core/2.13.3/a27014716e4421684416e5fa83d896ddb87002da/jackson-core-2.13.3.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.webjars/popper.js/2.9.3/5a29186da48dfce0c2455f383efd517ab15ec146/popper.js-2.9.3.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/com.fasterxml.jackson.datatype/jackson-datatype-jsr310/2.13.3/ad2f4c61aeb9e2a8bb5e4a3ed782cfddec52d972/jackson-datatype-jsr310-2.13.3.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/com.fasterxml.jackson.module/jackson-module-parameter-names/2.13.3/f71c4ecc1a403787c963f68bc619b78ce1d2687b/jackson-module-parameter-names-2.13.3.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/com.fasterxml.jackson.datatype/jackson-datatype-jdk8/2.13.3/d4884595d5aab5babdb00ddbd693b8fd36b5ec3c/jackson-datatype-jdk8-2.13.3.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/com.fasterxml.jackson.core/jackson-databind/2.13.3/56deb9ea2c93a7a556b3afbedd616d342963464e/jackson-databind-2.13.3.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.boot/spring-boot-autoconfigure/2.7.1/923ad789b004e8cc17d67853b1e4d3db11946f0/spring-boot-autoconfigure-2.7.1.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.boot/spring-boot/2.7.1/8e49b8e7e9ea470a7772f489532264732ab206a2/spring-boot-2.7.1.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.boot/spring-boot-starter-logging/2.7.1/461cf82dc10505f47d3ce2146bd01721177cde4a/spring-boot-starter-logging-2.7.1.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/jakarta.annotation/jakarta.annotation-api/1.3.5/59eb84ee0d616332ff44aba065f3888cf002cd2d/jakarta.annotation-api-1.3.5.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.yaml/snakeyaml/1.30/8fde7fe2586328ac3c68db92045e1c8759125000/snakeyaml-1.30.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.apache.tomcat.embed/tomcat-embed-websocket/9.0.64/2a5e4f1f04830f2bfd01108ddc59a451c4baef34/tomcat-embed-websocket-9.0.64.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.apache.tomcat.embed/tomcat-embed-core/9.0.64/2d91a06d1b93ba13a2cca9e9ea7c143a64037351/tomcat-embed-core-9.0.64.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.apache.tomcat.embed/tomcat-embed-el/9.0.64/227363669235feab54519102af723a54d1a7850e/tomcat-embed-el-9.0.64.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework/spring-context/5.3.21/fe371c85f02b8c6690fc3b3d0950ef4f965db0cd/spring-context-5.3.21.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework/spring-beans/5.3.21/e3eae7e6d211381642a0b7507a5215e3ac1b32e1/spring-beans-5.3.21.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework/spring-expression/5.3.21/ca8c5822fc528066ec717f1e74160a1575c43192/spring-expression-5.3.21.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework.security/spring-security-crypto/5.7.2/323a1844204fc8e05cead2bd75a9077121eba87e/spring-security-crypto-5.7.2.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.springframework/spring-jcl/5.3.21/b41a2888c0e708f9fd12cf9cc0c29cebbcab2e5e/spring-jcl-5.3.21.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/com.github.stephenc.jcip/jcip-annotations/1.0-1/ef31541dd28ae2cefdd17c7ebf352d93e9058c63/jcip-annotations-1.0-1.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/com.nimbusds/content-type/2.2/9a894bce7646dd4086652d85b88013229f23724b/content-type-2.2.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/net.minidev/json-smart/2.4.8/7c62f5f72ab05eb54d40e2abf0360a2fe9ea477f/json-smart-2.4.8.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/com.nimbusds/lang-tag/1.6/ba96ae591bf885f130a772794f07209e2bdb9fb5/lang-tag-1.6.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/com.fasterxml.jackson.core/jackson-annotations/2.13.3/7198b3aac15285a49e218e08441c5f70af00fc51/jackson-annotations-2.13.3.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/ch.qos.logback/logback-classic/1.2.11/4741689214e9d1e8408b206506cbe76d1c6a7d60/logback-classic-1.2.11.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.apache.logging.log4j/log4j-to-slf4j/2.17.2/17dd0fae2747d9a28c67bc9534108823d2376b46/log4j-to-slf4j-2.17.2.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.slf4j/jul-to-slf4j/1.7.36/ed46d81cef9c412a88caef405b58f93a678ff2ca/jul-to-slf4j-1.7.36.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/net.minidev/accessors-smart/2.4.8/6e1bee5a530caba91893604d6ab41d0edcecca9a/accessors-smart-2.4.8.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/ch.qos.logback/logback-core/1.2.11/a01230df5ca5c34540cdaa3ad5efb012f1f1f792/logback-core-1.2.11.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.apache.logging.log4j/log4j-api/2.17.2/f42d6afa111b4dec5d2aea0fe2197240749a4ea6/log4j-api-2.17.2.jar:/Users/dbash/.gradle/caches/modules-2/files-2.1/org.ow2.asm/asm/9.1/a99500cf6eea30535eeac6be73899d048f8d12a8/asm-9.1.jar com.flatiron.spring.FlatironSpring.FlatironSpringApplication
OpenJDK 64-Bit Server VM warning: Options -Xverify:none and -noverify were deprecated in JDK 13 and will likely be removed in a future release.

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.7.1)
```

Where has all the rest of the output gone?

Since we set the logging level to WARN, we will only see output for the WARN or
ERROR leveled log statements. If we go back to the output before we changed the
log levels, we will see that most of the output associated with the Spring
Framework itself has the level `INFO`; therefore, it will not be visible when
the log level is higher.

Let's now go from a very terse output to a very verbose output - let's change
the log level to `TRACE`:

```properties
logging.level.root=TRACE
```

Restart the application and look at everything the Spring Framework now tells
us about everything single process it's doing. The output on the workstation
went from the 10 lines to over 4,000 lines of output!

This can be useful when we are trying to trace a particular call or debug a
specific issue, but this is usually too much information under normal
circumstances.

So far in this lesson, we've been configuring the logging level at `root`,
which impacts every single class that runs under our application, including the
Spring Framework itself. This is why when we changed the `root` level to TRACE,
it produced a massive log.

Let's set the `root` logging level back to `INFO` and set the logging level for
our application to `TRACE`:

```properties
logging.level.root=INFO
logging.level.com.example.springrestdemo=TRACE
```

As we can see, we can specify a package name after `logging.level` and the
logging level will be set as indicated for any `Logger` instances associated
with a class that is anywhere in that package (even sub-packages).

Let's add a few logging statements to our service in order to see the impact
of this change:

```java
package com.example.springrestdemo.service;

import com.example.springrestdemo.dto.JokeDTO;
import lombok.extern.slf4j.Slf4j;
import org.springframework.stereotype.Service;
import org.springframework.web.client.RestTemplate;

@Service
@Slf4j
public class JokeService {

    private static final String JOKE_URI = "https://icanhazdadjoke.com/";
    private final RestTemplate restTemplate;

    @Autowired
    public JokeService(RestTemplate restTemplate) {
        this.restTemplate = restTemplate;
    }

    public JokeDTO getJoke() {
        log.trace("Entering in the getJoke() method");
        JokeDTO joke = restTemplate.getForObject(JOKE_URI, JokeDTO.class);
        log.trace("Retrieved joke from external source. Returning the DTO");
        return joke;
    }
}
```

Here are a few lines from the corresponding output:

```text
2022-12-15 14:18:45.327  INFO 7230 --- [nio-8080-exec-1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring DispatcherServlet 'dispatcherServlet'
2022-12-15 14:18:45.328  INFO 7230 --- [nio-8080-exec-1] o.s.web.servlet.DispatcherServlet        : Initializing Servlet 'dispatcherServlet'
2022-12-15 14:18:45.328  INFO 7230 --- [nio-8080-exec-1] o.s.web.servlet.DispatcherServlet        : Completed initialization in 0 ms
2022-12-15 14:18:45.403 TRACE 7230 --- [nio-8080-exec-1] c.e.springrestdemo.service.JokeService    : Entering in the getJoke() method
2022-12-15 14:18:45.890 TRACE 7230 --- [nio-8080-exec-1] c.e.springrestdemo.service.JokeService    : Retrieved joke from external source. Returning the DTO
```

As you can see, we no longer have all the `trace()` output from the Spring
Framework itself, but we do have them from our service class.

## Summary

We can configure the log levels of what is printed out to the log through the
`application.properties` file. We can change the log level at the root level,
which includes logs regarding the Spring Framework itself, or we can change the
log level at the application level.

## References

- [Spring Logging Documentation](https://docs.spring.io/spring-boot/docs/2.1.18.RELEASE/reference/html/boot-features-logging.html)
