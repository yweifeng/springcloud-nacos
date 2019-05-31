nacos-provider 服务提供方
===

1、pom.xml
---
    父模块：
    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>org.springframework.cloud</groupId>
                <artifactId>spring-cloud-alibaba-dependencies</artifactId>
                <version>${spring-cloud-alibaba-dependencies.version}</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>
    
    子模块：
    <dependency>
        <groupId>org.springframework.cloud</groupId>
        <artifactId>spring-cloud-starter-alibaba-nacos-discovery</artifactId>
    </dependency>

2、application.yml
---
    server:
      port: 18085
    spring:
      cloud:
        nacos:
          discovery:
            server-addr: 127.0.0.1:8848 

3、application.java 添加注解 @EnableDiscoveryClient
---


nacos 配置中心
===

1、pom.xml
---
     <dependency>
         <groupId>org.springframework.cloud</groupId>
         <artifactId>spring-cloud-starter-alibaba-nacos-config</artifactId>
     </dependency>

2、bootstrap.yml
---
    spring:
      application:
        name: nacos-server #这里对应dataId
      cloud:
        nacos:
          config:
            server-addr: 127.0.0.1:8848

3、使用类中添加自动刷新注解 @RefreshScope, 使用属性 使用 @Value方式获取
---

4、网页修改配置信息，配置属性信息自动修改
--- 
   