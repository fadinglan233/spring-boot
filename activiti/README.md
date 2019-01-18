# Activiti
### this is a Activiti Spring Boot project repository

# Activiti项目简介
### 这是一个Activiti Spring Boot的学习项目

### maven依赖
````
 <dependency>
      <groupId>org.activiti</groupId>
      <artifactId>activiti-spring-boot-starter-basic</artifactId>
       <version>6.0.0</version>
  </dependency>
  ````
  ### jdbc配置
  #### spring2.0 开始默认使用的是hikari为数据源连接，具体druid和harike的对比，请移步[harike官网](https://github.com/brettwooldridge/HikariCP)
  ````
spring:
   datasource:
    driver-class-name: com.mysql.jdbc.Driver
    type: com.zaxxer.hikari.HikariDataSource
    url: jdbc:mysql://localhost:3306/activiti_test?useUnicode=true&characterEncoding=utf-8
    username: root
    password: 111111
    hikari:
      minimum-idle: 5
      maximum-pool-size: 15
      auto-commit: true
      idle-timeout: 30000
      pool-name: DatebookHikariCP
      max-lifetime: 1800000
      connection-timeout: 30000
      connection-test-query: SELECT 1

  activiti:
    check-process-definitions: true # activti是否自动部署
    db-identity-used: true #是否使用activti自带的用户体系
    database-schema-update: true #是否每次都更新数据库
    #    check-process-definitions: false # activti是否自动部署
    #    db-identity-used: false #是否使用activti自带的用户体系
    #    database-schema-update: false #是否每次都更新数据库
````
### application配置
#### 这里我们将禁用activiti的安全配置，如果需要使用acitiviti rest api，请按需要进行安全配置
````
@SpringBootApplication(exclude = {org.activiti.spring.boot.SecurityAutoConfiguration.class})
public class ActivitiApplication {

    public static void main(String[] args) {
        SpringApplication.run(ActivitiApplication.class, args);
    }

}
````
### 创建bpmn文件
#### 1.使用acitiviti的 admin及web项目创建bpmn文件
#### 2.下载安装 actiBPM插件
![image](https://github.com/bijialin/spring-boot/raw/master/activiti/rdimages/actiBPMWindow.png)
##### 在resources下创建个processes目录，在这个目录下创建bpmn文件，deploy的时候直接使用文件名部署即可.
##### 例如test.bpmn
![image](https://github.com/bijialin/spring-boot/raw/master/activiti/rdimages/testbpm.png)


### if you want to visit more articles please click [my blog](https://www.jianshu.com/u/1bb4b4eaef1e)
### of course you can send email to me [bijialin05@gmail.com](bijialin05@gmail.com)

### 如果你想查看更多我分享的技术博客，请访问[我的博客](https://www.jianshu.com/u/1bb4b4eaef1e)
### 如果问题，请发送邮件到我的邮箱[bijialin05@gmail.com](bijialin05@gmail.com)
