# 编程基础

## JAVA语法

#### Java基础

* 基础语法

* 面向对象

* 接口

* 容器

* 异常

* 泛型

* 反射

* 注解

* I/O

* ~~图形化(Swing)~~

  

####  JVM(虚拟机)
- 类加载机制
- 字节码执行机制
- JVM内存模型
- GC垃圾回收
- JVM性能监控与故障定位
- JVM调优

#### 多线程/并发
- 并发编程的基础
- 线程池
- 锁
- 并发容器
- 原子类
- JUC并发工具类

## 数据结构与算法

#### 数据结构
- 字符串
- 数组
- 链表
- 堆、栈、队列
- 二叉树
- 哈希
- 图

#### 算法
- 排序
- 查找
- 贪心
- 分治
- 动态规划
- 回溯

## 计算机网络

- ARP协议
- IP、ICMP协议
- TCP、UDP协议
- DNS、HTTP/HTTPS协议
- Session/Cookie

##  MySQL数据库

- SQL语句的书写(增删改查)
- SQL语句的优化
- 事务、隔离级别
- 索引
- 锁

##  操作系统

- 进程、线程
- 并发、锁
- 内存管理和调度
- I/O原理

##  设计模式

- 单例
- 工厂
- 代理
- 策略
- 模板方法
- 观察者
- 适配器
- 责任链
- 建造者

# 研发工具

## 集成开发环境

- Eclipse
- Intellij IDEA 
- VSCode

## Linux系统

* 常用命令
*  Shell脚本

## 项目管理/构建工具

-  Maven 
-  Gradle

## 代码管理工具

* SVN 
* Git

# 应用框架

## 后端

### Spring家族框架

* Spring   
  - IoC  
  - AOP
* SpringMVC
* Spring Boot  
  - 自动配置，开箱即用
  - 整合Web
  - 整合数据库（事物问题）
  - 整合权限
    - Shiro
    - Spring Security

* 整合各种中间件
  - Redis,MQ,RPC框架,NIO框架

### 服务器软件

* Web服务器
  - Nginx

* 应用服务器
  - TomCat
  - Jetty
  - Undertow

###  中间件（应对高并发、大容量）

- 缓存
  - **Redis**（掌握，重要,2week）
    - 《Redis设计与实践》
    - 5大基础数据类型
    - 事务
    - 管道
    - 持久化
    - 集群

- 消息队列（学一个即可）
  - RocketMQ
  - RabbitMQ
  - Kafka（大数据）

* RPC框架
  - Dubbo
  - gRPC
  - Thrift
  - Spring Cloud
  - Netty

### 数据库框架

* **ORM层框架**（掌握）
  - Mybatis
  - Hibernate
  - JPA

- **连接池**（掌握）
  - Druid
  - HikariCP
  - C3P0
- 分库分表
  - MyCAT
  - Sharding-JDBC
  - Sharding-Sphere

### 搜索引擎(了解)

- ElasticSearch
- Solr

### 分布式/微服务（了解,2-3week）

- 服务发现/注册
  - Eureka
  - Consul
  - Zookeeper（重要）
  - Nacos
- 网关
  - Zuul
  - Gateway
- 服务调用（负载均衡）
  - Ribbon
  - Feign
- 熔断/降级
  - Hystrix
- 配置中心
  - Config
  - Apollo
  - Nacos
- 认证和鉴权（稍微重要些）
  - Spring Security
  - OAuth2
  - SSO单点登录
- 分布式事务
  - JTA接口
    - Atomikos组件
  - 2PC、3PC
  - XA模式
  - TCC模式
    - tcc-transaction
    - ByteTCC
    - EasyTransaction
    - SeaTa
  - SAGA模式
    - ServiceComb、
    - Seata
  - LCN模式
    - tx-Icn
- 任务调度
  - Quartz
  - Elastic-Job
- 链路追踪和监控
  - Zipkin
  - Sleuth
  - Skywalking
- 日志分析与监控
  - ELK
    - ElasticSearch
    - Logstash
    - Kibana

### 虚拟化/容器化

- 容器技术
  - Docker
- 容器编排技术
  - Kubernetes
  - Swarm

## 前端

* 基础套餐（大致了解，2-3天）
  - 三大件
    - HTML
    - JavaScript
    - CSS
  - 基础库
    - jQuery
    - Ajax

* 
   模板框架
  - ~~JSP/JSTL~~（已过时）
  - Thymeleaf
  - FreeMarker
*  组件化框架
  - Vue
  - React
  - Angular

# 运维知识（配置）

- Web服务器
   - Nginx

- 应用服务器
   - Tomcat
   - Jetty
   - Undertow

- CDN加速
-  持续集成/持续部署
  - Jenkins

- 代码质量检查
  - sonar

- 日志收集和分析
  - ELK