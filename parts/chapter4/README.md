###pom.xml

要使用分布式任务组件`se.tools.quartz.toc`只需要引入一个jar包：


* se.tools.quartz.toc 

 依赖 quartz、quartz-jobs 两个quartz 基本包，版本号 2.2.2
 
 依赖 sqljdbc4 ， quartzToc 使用的 sqlServer 数据源


pom.xml如下：


```xml
 <dependencies>
        <dependency>
		<groupId>com.lianjia.sh</groupId>
		<artifactId>se.tools.quartz-toc</artifactId>
		<version>0.2.1</version>
	</dependency>
 </dependencies>
```
