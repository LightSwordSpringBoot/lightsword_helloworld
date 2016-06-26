# 第三章 从HellWorld开始


### 创建Maven工程

Maven工程groupId,artifactId配置如下:

```
 <groupId>com.lightsword.sb</groupId>
 <artifactId>helloword</artifactId>
 <version>1.0-SNAPSHOT</version>
```



配置pom.xml如下:

```

<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.lightsword.sb</groupId>
    <artifactId>helloword</artifactId>
    <version>1.0-SNAPSHOT</version>

    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>1.3.5.RELEASE</version>
    </parent>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
    </dependencies>

    <!-- (you don't need this if you are using a .RELEASE version) -->
    <repositories>
        <repository>
            <id>spring-snapshots</id>
            <url>http://repo.spring.io/snapshot</url>
            <snapshots><enabled>true</enabled></snapshots>
        </repository>
        <repository>
            <id>spring-milestones</id>
            <url>http://repo.spring.io/milestone</url>
        </repository>
    </repositories>
    <pluginRepositories>
        <pluginRepository>
            <id>spring-snapshots</id>
            <url>http://repo.spring.io/snapshot</url>
        </pluginRepository>
        <pluginRepository>
            <id>spring-milestones</id>
            <url>http://repo.spring.io/milestone</url>
        </pluginRepository>
    </pluginRepositories>

</project>


```




### 创建入口类

HelloWorld.java

```

package com.lightsword.sb;

import org.springframework.boot.*;
import org.springframework.boot.autoconfigure.*;
import org.springframework.stereotype.*;
import org.springframework.web.bind.annotation.*;


/**
 * Created by jack on 2016/6/24.
 */

@Controller
@EnableAutoConfiguration
public class HelloWorld {

    @RequestMapping("/")
    @ResponseBody
    String home() {
        return "Hello World!";
    }

    public static void main(String[] args) throws Exception {
        SpringApplication.run(HelloWorld.class, args);
    }

}



```


## 運行

直接运行Java类(Run Hellworld,在eclipse上Run As Java Application),可以看到控制台输出如下日志:

```

/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/bin/java -Dspring.output.ansi.enabled=always -Didea.launcher.port=7532 "-Didea.launcher.bin.path=/Volumes/IntelliJ IDEA/IntelliJ IDEA.app/Contents/bin" -Dfile.encoding=UTF-8 -classpath "/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/charsets.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/deploy.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/ext/cldrdata.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/ext/dnsns.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/ext/jfxrt.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/ext/localedata.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/ext/nashorn.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/ext/sunec.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/ext/sunjce_provider.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/ext/sunpkcs11.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/ext/zipfs.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/javaws.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/jce.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/jfr.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/jfxswt.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/jsse.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/management-agent.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/plugin.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/resources.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/jre/lib/rt.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/lib/ant-javafx.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/lib/dt.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/lib/javafx-mx.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/lib/jconsole.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/lib/packager.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/lib/sa-jdi.jar:/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home/lib/tools.jar:/Users/jack/githubcode/lightsword-helloworld/target/classes:/Users/jack/.m2/repository/org/springframework/boot/spring-boot-starter-web/1.3.5.RELEASE/spring-boot-starter-web-1.3.5.RELEASE.jar:/Users/jack/.m2/repository/org/springframework/boot/spring-boot-starter/1.3.5.RELEASE/spring-boot-starter-1.3.5.RELEASE.jar:/Users/jack/.m2/repository/org/springframework/boot/spring-boot/1.3.5.RELEASE/spring-boot-1.3.5.RELEASE.jar:/Users/jack/.m2/repository/org/springframework/boot/spring-boot-autoconfigure/1.3.5.RELEASE/spring-boot-autoconfigure-1.3.5.RELEASE.jar:/Users/jack/.m2/repository/org/springframework/boot/spring-boot-starter-logging/1.3.5.RELEASE/spring-boot-starter-logging-1.3.5.RELEASE.jar:/Users/jack/.m2/repository/ch/qos/logback/logback-classic/1.1.7/logback-classic-1.1.7.jar:/Users/jack/.m2/repository/ch/qos/logback/logback-core/1.1.7/logback-core-1.1.7.jar:/Users/jack/.m2/repository/org/slf4j/slf4j-api/1.7.21/slf4j-api-1.7.21.jar:/Users/jack/.m2/repository/org/slf4j/jcl-over-slf4j/1.7.21/jcl-over-slf4j-1.7.21.jar:/Users/jack/.m2/repository/org/slf4j/jul-to-slf4j/1.7.21/jul-to-slf4j-1.7.21.jar:/Users/jack/.m2/repository/org/slf4j/log4j-over-slf4j/1.7.21/log4j-over-slf4j-1.7.21.jar:/Users/jack/.m2/repository/org/springframework/spring-core/4.2.6.RELEASE/spring-core-4.2.6.RELEASE.jar:/Users/jack/.m2/repository/org/yaml/snakeyaml/1.16/snakeyaml-1.16.jar:/Users/jack/.m2/repository/org/springframework/boot/spring-boot-starter-tomcat/1.3.5.RELEASE/spring-boot-starter-tomcat-1.3.5.RELEASE.jar:/Users/jack/.m2/repository/org/apache/tomcat/embed/tomcat-embed-core/8.0.33/tomcat-embed-core-8.0.33.jar:/Users/jack/.m2/repository/org/apache/tomcat/embed/tomcat-embed-el/8.0.33/tomcat-embed-el-8.0.33.jar:/Users/jack/.m2/repository/org/apache/tomcat/embed/tomcat-embed-logging-juli/8.0.33/tomcat-embed-logging-juli-8.0.33.jar:/Users/jack/.m2/repository/org/apache/tomcat/embed/tomcat-embed-websocket/8.0.33/tomcat-embed-websocket-8.0.33.jar:/Users/jack/.m2/repository/org/springframework/boot/spring-boot-starter-validation/1.3.5.RELEASE/spring-boot-starter-validation-1.3.5.RELEASE.jar:/Users/jack/.m2/repository/org/hibernate/hibernate-validator/5.2.4.Final/hibernate-validator-5.2.4.Final.jar:/Users/jack/.m2/repository/javax/validation/validation-api/1.1.0.Final/validation-api-1.1.0.Final.jar:/Users/jack/.m2/repository/org/jboss/logging/jboss-logging/3.3.0.Final/jboss-logging-3.3.0.Final.jar:/Users/jack/.m2/repository/com/fasterxml/classmate/1.1.0/classmate-1.1.0.jar:/Users/jack/.m2/repository/com/fasterxml/jackson/core/jackson-databind/2.6.6/jackson-databind-2.6.6.jar:/Users/jack/.m2/repository/com/fasterxml/jackson/core/jackson-annotations/2.6.6/jackson-annotations-2.6.6.jar:/Users/jack/.m2/repository/com/fasterxml/jackson/core/jackson-core/2.6.6/jackson-core-2.6.6.jar:/Users/jack/.m2/repository/org/springframework/spring-web/4.2.6.RELEASE/spring-web-4.2.6.RELEASE.jar:/Users/jack/.m2/repository/org/springframework/spring-aop/4.2.6.RELEASE/spring-aop-4.2.6.RELEASE.jar:/Users/jack/.m2/repository/aopalliance/aopalliance/1.0/aopalliance-1.0.jar:/Users/jack/.m2/repository/org/springframework/spring-beans/4.2.6.RELEASE/spring-beans-4.2.6.RELEASE.jar:/Users/jack/.m2/repository/org/springframework/spring-context/4.2.6.RELEASE/spring-context-4.2.6.RELEASE.jar:/Users/jack/.m2/repository/org/springframework/spring-webmvc/4.2.6.RELEASE/spring-webmvc-4.2.6.RELEASE.jar:/Users/jack/.m2/repository/org/springframework/spring-expression/4.2.6.RELEASE/spring-expression-4.2.6.RELEASE.jar:/Volumes/IntelliJ IDEA/IntelliJ IDEA.app/Contents/lib/idea_rt.jar" com.intellij.rt.execution.application.AppMain com.lightsword.sb.HelloWorld

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v1.3.5.RELEASE)

2016-06-26 12:13:31.021  INFO 38506 --- [           main] com.lightsword.sb.HelloWorld             : Starting HelloWorld on jacks-MacBook-Air.local with PID 38506 (/Users/jack/githubcode/lightsword-helloworld/target/classes started by jack in /Users/jack/githubcode/lightsword-helloworld)
2016-06-26 12:13:31.028  INFO 38506 --- [           main] com.lightsword.sb.HelloWorld             : No active profile set, falling back to default profiles: default
2016-06-26 12:13:31.220  INFO 38506 --- [           main] ationConfigEmbeddedWebApplicationContext : Refreshing org.springframework.boot.context.embedded.AnnotationConfigEmbeddedWebApplicationContext@1d7acb34: startup date [Sun Jun 26 12:13:31 CST 2016]; root of context hierarchy
2016-06-26 12:13:34.765  INFO 38506 --- [           main] s.b.c.e.t.TomcatEmbeddedServletContainer : Tomcat initialized with port(s): 8080 (http)
2016-06-26 12:13:34.817  INFO 38506 --- [           main] o.apache.catalina.core.StandardService   : Starting service Tomcat
2016-06-26 12:13:34.821  INFO 38506 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet Engine: Apache Tomcat/8.0.33
2016-06-26 12:13:35.093  INFO 38506 --- [ost-startStop-1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2016-06-26 12:13:35.093  INFO 38506 --- [ost-startStop-1] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 3893 ms
2016-06-26 12:13:35.608  INFO 38506 --- [ost-startStop-1] o.s.b.c.e.ServletRegistrationBean        : Mapping servlet: 'dispatcherServlet' to [/]
2016-06-26 12:13:35.623  INFO 38506 --- [ost-startStop-1] o.s.b.c.embedded.FilterRegistrationBean  : Mapping filter: 'characterEncodingFilter' to: [/*]
2016-06-26 12:13:35.624  INFO 38506 --- [ost-startStop-1] o.s.b.c.embedded.FilterRegistrationBean  : Mapping filter: 'hiddenHttpMethodFilter' to: [/*]
2016-06-26 12:13:35.625  INFO 38506 --- [ost-startStop-1] o.s.b.c.embedded.FilterRegistrationBean  : Mapping filter: 'httpPutFormContentFilter' to: [/*]
2016-06-26 12:13:35.625  INFO 38506 --- [ost-startStop-1] o.s.b.c.embedded.FilterRegistrationBean  : Mapping filter: 'requestContextFilter' to: [/*]
2016-06-26 12:13:36.389  INFO 38506 --- [           main] s.w.s.m.m.a.RequestMappingHandlerAdapter : Looking for @ControllerAdvice: org.springframework.boot.context.embedded.AnnotationConfigEmbeddedWebApplicationContext@1d7acb34: startup date [Sun Jun 26 12:13:31 CST 2016]; root of context hierarchy
2016-06-26 12:13:36.588  INFO 38506 --- [           main] s.w.s.m.m.a.RequestMappingHandlerMapping : Mapped "{[/]}" onto java.lang.String com.lightsword.sb.HelloWorld.home()
2016-06-26 12:13:36.593  INFO 38506 --- [           main] s.w.s.m.m.a.RequestMappingHandlerMapping : Mapped "{[/error]}" onto public org.springframework.http.ResponseEntity<java.util.Map<java.lang.String, java.lang.Object>> org.springframework.boot.autoconfigure.web.BasicErrorController.error(javax.servlet.http.HttpServletRequest)
2016-06-26 12:13:36.594  INFO 38506 --- [           main] s.w.s.m.m.a.RequestMappingHandlerMapping : Mapped "{[/error],produces=[text/html]}" onto public org.springframework.web.servlet.ModelAndView org.springframework.boot.autoconfigure.web.BasicErrorController.errorHtml(javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse)
2016-06-26 12:13:36.670  INFO 38506 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/webjars/**] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2016-06-26 12:13:36.670  INFO 38506 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/**] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2016-06-26 12:13:36.752  INFO 38506 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/**/favicon.ico] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2016-06-26 12:13:36.990  INFO 38506 --- [           main] o.s.j.e.a.AnnotationMBeanExporter        : Registering beans for JMX exposure on startup
2016-06-26 12:13:37.134  INFO 38506 --- [           main] s.b.c.e.t.TomcatEmbeddedServletContainer : Tomcat started on port(s): 8080 (http)
2016-06-26 12:13:37.140  INFO 38506 --- [           main] com.lightsword.sb.HelloWorld             : Started HelloWorld in 7.609 seconds (JVM running for 9.363)


```


## 测试

访问浏览器

>http://localhost:8080/

可以看到输出:

```
Hello World!
```

## 换一个端口

默认端口是8080,如果我们想指定端口号,怎么配置呢?

SB的web-starter默认内嵌应用容器是tomcat,8080端口(从启动日志,我们可以看出).配置端口,我们只需要在应用的全局配置文件application.properties(放到resource根目录下),添加如下一行配置:

```

server.port=8888

```

即可使用我们自己配置的端口号.


##使用jetty容器启动


