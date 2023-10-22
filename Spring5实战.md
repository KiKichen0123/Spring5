# Spring5实战

## 不懂的名词

### 反应式编程

反应式编程（Reactive Programming）是一种编程范式，用于处理异步数据流和事件流。它的主要目标是简化异步编程的复杂性，使开发人员能够更容易地处理事件和数据流的变化。

反应式编程的核心思想是将数据流视为一个连续的事件序列，开发人员可以定义对这些事件的响应逻辑。在这个编程范式中，数据流的变化会触发一系列的操作，这些操作可以是数据转换、过滤、合并、映射等，以及对数据流的订阅和取消订阅。

反应式编程通常使用观察者模式和可观察对象（Observable）来实现。观察者订阅可观察对象，当可观察对象发生变化时，观察者会收到通知并执行相应的操作。这种方式使开发人员能够以声明性的方式描述数据流的处理逻辑，而不需要显式地管理异步任务、回调函数或事件处理。

反应式编程在处理复杂的异步场景，例如用户界面的交互、网络通信、传感器数据等方面非常有用。它有助于提高代码的可维护性和可读性，同时降低了出现竞态条件和错误的概率。

一些常见的反应式编程库和框架包括RxJava（Java）、RxJS（JavaScript）、Reactor（Java）、Project Reactor（Java）、RxSwift（Swift）等。这些库提供了丰富的工具和操作符，用于处理数据流和事件流，使开发人员能够更轻松地应对异步编程的挑战。

### RSocket通信协议

RSocket是一种用于网络通信的协议，它旨在提供可靠、高性能和灵活的双向通信。RSocket协议最初由Netflix开发，后来成为Reactive Foundation的一部分。它具有许多吸引人的特性，特别适用于微服务架构和分布式系统。

以下是RSocket通信协议的一些关键特点：

1. 异步双向通信：RSocket支持双向通信，允许客户端和服务器之间进行异步消息传递。这使得实时应用程序、流式处理和实时监控等场景更容易实现。

2. 四种通信模型：RSocket定义了四种通信模型，包括请求-响应、请求-流、流-请求和流-流。这些模型可以根据应用程序的需求来选择，从而实现更高的灵活性。

3. 多语言支持：RSocket具有多语言支持，可以在各种编程语言中使用。这意味着您可以在不同的技术堆栈中使用RSocket进行通信，而不必担心语言限制。

4. 多种传输协议：RSocket可以在多种传输协议上运行，包括TCP、WebSocket、Aeron等。这使得它适用于各种网络环境和场景。

5. 可自定义的负载协商：RSocket允许客户端和服务器在建立连接时协商和选择使用的负载类型。这允许您选择最适合您应用程序需求的负载类型，例如JSON、Protocol Buffers等。

6. 断线重连：RSocket内置了断线重连机制，可以在网络断开连接后自动重新连接，确保通信的可靠性和持久性。

7. 可扩展性：RSocket协议的设计允许添加自定义扩展，以满足特定应用程序的需求。

总之，RSocket是一种灵活、高性能的通信协议，适用于各种应用程序，特别是那些需要实时通信和流式处理的场景。它的多语言支持和多种通信模型使其成为构建现代分布式系统的有力工具之一。

### REST API

REST API（Representational State Transfer Application Programming Interface）是一种基于REST架构原则的应用程序编程接口（API）。REST是一种设计风格，通常用于构建分布式系统中的网络服务和应用程序。REST API基于以下核心原则：

1. **资源（Resources）**：在REST中，所有的数据和功能都被视为资源，每个资源都由一个唯一的标识符（通常是URL）表示。资源可以是实际的物理对象（例如，订单、用户）或抽象的概念（例如，时间表、库存）。

2. **HTTP方法**：REST API使用HTTP方法来执行对资源的操作。常用的HTTP方法包括GET（获取资源）、POST（创建资源）、PUT（更新资源）和DELETE（删除资源）等。每个HTTP方法都对应了一种特定的操作。

3. **状态无关性（Stateless）**：REST API是无状态的，这意味着每个请求都包含了足够的信息，使服务器能够理解和处理它，而不需要依赖于之前的请求。这有助于提高系统的可伸缩性和可维护性。

4. **表示（Representation）**：资源的状态以及与资源相关的操作的信息在请求和响应中通过表示传输。这些表示可以采用不同的格式，如JSON、XML、HTML等，客户端和服务器之间通过这些表示进行数据交换。

5. **统一接口（Uniform Interface）**：REST API的接口应该是统一和一致的，这意味着使用相同的约定和原则来设计所有资源和操作。这有助于降低学习曲线，使API更易于使用。

6. **无状态通信（Stateless Communication）**：每个请求都应该包含足够的信息，以便服务器理解请求，而不依赖于之前的请求。这有助于提高可伸缩性，因为服务器不需要维护客户端的状态。

REST API通常用于构建分布式系统中的网络服务，例如Web服务、移动应用程序后端、IoT设备通信等。由于其简单性和可伸缩性，REST API在现代应用程序开发中得到广泛使用。它们通常使用HTTP作为通信协议，因此可以轻松地与各种编程语言和平台集成。

## 目的

编写本书的目的是让你学会使用Spring框架、Spring Boot及Spring生态系统中的其他组成部分构建令人赞叹的应用程序。本书首先介绍如何使用Spring和Spring Boot开发基于Web、以数据库作为后端的Java应用，随后进行必要的扩展，展现了如何与其他应用进行集成和使用反应式类型进行编程，最后讨论如何准备应用的部署。



# 第1部分涵盖了构建Spring应用的基础知识

### 第一章

●第1章介绍Spring、Spring Boot，以及如何初始化Spring项目。我们在这章中迈出构建Spring应用的第一步，在本书后续章节中，我们会对这个应用进行扩展。

```xml
<?xml version = "1.0" encoding = "UTF-8"?><project
xmlns = "http://maven.apache.org/POM/4.0.0"
xmlns:xsi = "http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation = "http://maven.apache.org/POM/4.0.0
        https://maven.apache.org/xsd/maven-4.0.0.xsd">
<modelVersion>4.0.0</modelVersion>
<parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>2.5.3</version>　　⇽---Spring Boot的版本
    <relativePath />
</parent>
<groupId>sia</groupId>
<artifactId>taco-cloud</artifactId>
<version>0.0.1-SNAPSHOT</version>
<name>taco-cloud</name>
<description>Taco Cloud Example</description>

<properties>
    <java.version>11</java.version>
</properties>

<dependencies>
    <dependency>　　⇽---Starter依赖
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-thymeleaf</artifactId>
    </dependency>

    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>

    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-devtools</artifactId>
        <scope>runtime</scope>
        <optional>true</optional>
    </dependency>

    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
        <exclusions>
            <exclusion>
                <groupId>org.junit.vintage</groupId>
                <artifactId>junit-vintage-engine</artifactId>
            </exclusion>
        </exclusions>
    </dependency>

</dependencies>

<build>
    <plugins>
        <plugin>　　⇽---Spring Boot插件
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-maven-plugin</artifactId>
        </plugin>
    </plugins>
</build>

<repositories>
    <repository>
        <id>spring-milestones</id>
        <name>Spring Milestones</name>
        <url>https://repo.spring.io/milestone</url>
    </repository>
</repositories>
<pluginRepositories>
    <pluginRepository>
        <id>spring-milestones</id>
        <name>Spring Milestones</name>
        <url>https://repo.spring.io/milestone</url>
    </pluginRepository>
</pluginRepositories>

</project>
```

首先要注意的是<parent>元素，更具体来说是它的<version>子元素。这表明我们的项目要以spring-boot-starter-parent作为其父POM。除了其他的一些功能之外，这个父POM为Spring项目常用的一些库提供了依赖管理。对于这些父POM中所涵盖到的库，我们不需要指定它们的版本，因为它会通过父POM继承下来

这里的2.5.3表明要使用Spring Boot 2.5.3，所以就会根据这个版本的Spring Boot定义来继承依赖管理。除了指定其他的依赖之外，2.5.3版本的Spring Boot依赖管理会指定底层的核心Spring框架的版本为5.3.9

#### 程序清单1.2 Tacp Cloud的引导类

```java
package tacos;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication　　⇽---Spring Boot应用
public class TacoCloudApplication {

public static void main(String[] args) {
SpringApplication.run(TacoCloudApplication.class, args);　　⇽---运行应用
}

}
```

@SpringBootApplication注解明确表明这是一个Spring Boot应用

- @SpringBootConfiguration 配置类

- @EnableAutoConfiguration  启动Spring自动配置，这个注释告诉 Spring Boot ⾃动配置它认为需要的任何组件

- @ComponentScan 启⽤组件扫描，这允许您声明其他带有@Component、@Controller、@Service 等注释的类，以便让 Spring⾃动发现它们并将它们注册为 Spring 应⽤程序上下⽂中的组

  件。

ain() ⽅法调⽤ SpringApplication 类上的静态 run() ⽅法

- 该⽅法执⾏应⽤程序的实际引导，创建Spring 应⽤程序上下文，其中有两个参数
  - 一个是配置类
  - 一个是命令行参数

@SpringBootTest 告诉 JUnit 使⽤ Spring Boot 功能引导测试

- 是一个复合注解
- 本身用@ExtendWith(SpringExtension.class)注解
- 任务：加载测试的Spring应用程序上下文

#### 1.3 编写Spring应用程序 Spring In Action

- 一个处理主页请求的控制器类
- 一个视图模块，定义了主页的外观

##### 1.3.1 处理web请求





### 第二章

讨论如何使用Spring MVC构建应用的Web层。我们会构建处理Web请求的控制器，并在浏览器中渲染信息的视图。



### 第三章

深入探讨Spring应用的后端，在这里数据会持久化到关系型数据库中。



### 第四章

会继续数据持久化的话题，学习如何将数据持久化到非关系型数据库Cassandra和MongoDB中。



### 第五章

介绍如何使用Spring Security认证用户并防止未认证的用户访问应用。



### 第六章

介绍如何使用Spring Boot的配置属性功能来配置Spring应用。我们还会在这章学习如何使用profile选择性地应用配置。



## 第2部分讨论了如何将Spring应用与其他应用进行集成

### 第七章

第2章对Spring MVC的讨论，我们会学习如何在Spring中编写和消费REST API

### 第八章

展示如何使用Spring Security和OAuth 2保护我们在第7章创建的API。

### 第九章

讨论如何使用异步通信技术让Spring应用发送和接收消息，这里会用到Java Message Service、RabbitMQ或Kafka

### 第十章

讨论如何使用Spring Integration进行声明式地应用集成

## 第3部分探讨了Spring对反应式编程提供的全新支持

### 第十一章

介绍Reactor项目，这是一个反应式编程库，支撑Spring 5的反应式特性

### 第十二章

重新探讨REST API开发，介绍全新的Web框架Spring WebFlex。该框架借用了很多Spring MVC的理念，为Web开发提供了新的反应式模型

### 第十三章

介绍如何使用Spring Data编写反应式数据持久化，我们会尝试读取和写入Cassandra与Mongo数据库

### 第十四章

介绍RSocket协议。这是一个新的通信协议，在创建API方面，它提供了HTTP协议的反应式替代方案

## 第4部分介绍了如何做好应用投入生产环境前的准备工作，以及如何进行部署

### 第十五章

介绍Spring Boot Actuator。这是Spring Boot的一个扩展，它通过REST端点的形式暴露Spring应用内部的运行状况

### 第十六章

介绍如何使用Spring Boot Admin。它是构建在Actuator之上的一个对用户友好的基于浏览器的管理应用

### 第十七章

讨论如何将Spring bean暴露为JMX MBean，以及如何消费它们

### 第十八章

介绍如何将Spring应用部署到各种生产环境中，包括Kubernetes