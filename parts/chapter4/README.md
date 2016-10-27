###分布式任务组件接入教程

* 项目介绍

        se.tools.quartz-toc 是一个依赖于 quartz 与 sqlserver  做任务调度的组件。主要特点是易用！
        基本无缝托管 spring-task

* 项目依赖

 依赖 quartz、quartz-jobs 两个quartz 基本包，版本号 2.2.2
 
 依赖 sqljdbc4 ， quartzToc 使用的 sqlServer 数据源

 pom.xml 中引入 se.tools.quartz-toc 依赖


* pom.xml如下：


```xml
 <dependencies>
        <dependency>
		<groupId>com.lianjia.sh</groupId>
		<artifactId>se.tools.quartz-toc</artifactId>
		<version>0.2.1</version>
	</dependency>
 </dependencies>
```


---

1. 使用前提

    应用项目为 spring  项目，且使用 `org.springframework.scheduling.annotation.Scheduled` 注解
    来实现的定时任务。无需去掉 spring-task 的配置，也就是说在不开启 quartz-toc 的情况下，项目的定时
    任务是可以正常运行的。

2. 项目配置

    * spring-boot 或  spring-cloud 项目， 在 `start-class` 中使用注解 `@EnableQuartzToC`开启托管, 完工
    * 老项目，在任意一个单例的类上使用注解 `@EnableQuartzToC`开启托管，在 applicationContext.xml 中声明一个`com.lianjia.sh.se.tools.quartz.toc.config.EnvironmentConfiguration` Bean，用于提供 环境与项目名给quartz-toc。 

    `applicationContext.xml 示例代码如下:`

    ```xml
    <bean class="com.lianjia.sh.se.tools.quartz.toc.config.EnvironmentConfiguration"> 
        <property name="env" value="development"></property> 
        <property name="applicationName" value="QuartzTest"></property> 
    </bean>
    ```
3. 任务查看

    * [简陋版](http://10.22.15.2:19900/triggers "简陋版")

![简陋版 任务查看](/parts/chapter4/images/triggers page.png)
4. 完毕！！


