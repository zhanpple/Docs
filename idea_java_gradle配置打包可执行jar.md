# idea_java_gradle配置打包可执行jar

[TOC]

#### 目录

##### 1.新建java-gradle工程

略...

##### 2.配置入口main类， 以及main方法

略...

##### 3.配置build.gradle 

```
plugins {
    id 'java'
    id 'application' // 可执行
}
//...
mainClassName = 'com.xx.Main' //配置主类
```

##### 4.配置Artifacts 打包jar

###### 4.1.1 方式一：from modules with dependencies...

 Project Structure > add jar



![Add jar](RES/15669004041553.png)



###### 4.1.2 create jar

![Create JAR from Modules](RES/15669008043731.png)

之后会生成META-INF文件

![生成META-INF文件](RES/15669012783050.png)

确保Alt+左键 能够正常索引到main方法才能保证执行jar包时找到入口

###### 4.2.1 方式二：Empty 选择指定的class文件构建Jar

![指定的class文件构建Jar](RES/15671333038763.png)

【注意】重新打包jar记得修改版本号或名称，否则一直使用的缓存

【注意】重新打包jar记得修改版本号或名称，否则一直使用的缓存

【注意】重新打包jar记得修改版本号或名称，否则一直使用的缓存

重要的事说三遍...

###### 4.3 build jar

Build菜单 > Build Artifacts... >Action 

之后就会在

![生成JAR](RES/1566901388-1.jpg)

###### 4.4 测试jar

dos命令 ` java -jar jar绝对路径`



















