﻿  ## 中文 | [English](README_EN.md)  
  
  ## 项目介绍　　
  jforgame，是一个用java编写的轻量级高性能手游服务端框架。项目提供各种支持快速二次开发的组件，以及对生产环境的服务进行管理的工具。同时，为了使用户能够快速上手，项目提供了若干常用业务功能作为演示。

  ## 项目特点  
  * 搭配框架博客栏目教程，快速理解项目模块原理  
  * 支持socket/websocket接入，兼容手游/页游服务端架构  
  * 通信协议支持protobuf或java反射，为客户端提供多种选择   
  * 框架提供多种组件，可以直接二次开发业务逻辑  
  * 提供热更机制以及jmx接口，方便对生产项目进行监控与维护   
  * 有独立http后台网站，为游戏运维/运营提供支持  --> [后台管理系统](https://github.com/kingston-csj/gamekeeper)  


  ## 模块组织结构  
  ``` 
  jforgame
  ├── jforgame-common  --基础公共服务  
  ├── jforgame-admin   --后台管理web工具  
  ├── jforgame-match   --跨服匹配服       
  ├── jforgame-net     --包括io网关模块，玩家消息自动映射到业务模块，异步处理玩家消息的线程模型      
  ├── jforgame-orm     --使用自定义的orm框架，用于数据库表记录与程序pojo对象的相互转换        
  ├── hotswap-agent  支持游戏业务热更新的agent机制  
  ├── jforgame-server  --游戏基础组件以及业务逻辑模块  
  |    ├──  cache包，使用guava cache库，用于支持系统的缓存框架    
  |    ├──  db包，使用独立线程，异步处理玩家及公共数据的持久化  
  |    ├──  monitor包，系统监控模块，包括使用jmx对程序进行监控  
  |    ├──  listener包，事件驱动模型  
  |    ├──  doctor包，采用Groovy执行任意动态代码，或JDK的instrument机制修改类方法体  
  |    ├──  game/gm包，游戏内部金手指命令
  |    ├──  game/admin包，游戏运营/运维后台命令  
  |    ├──  redis包，跨服通信（比如跨服排行榜）  
  |    ├──  tools包，简化项目开发的辅助小工具  
  |    └──  utils包，各种工具类    
  ```  

  
  ## 第三方技术栈 
  名称 | 用途 | 官网  
  ----|------|----     
  Mina | nio socket 框架 | [http://mina.apache.org/](http://mina.apache.org/)  
  jprotobuf | 通信双方消息编解码 | [https://github.com/jhunters/jprotobuf](https://github.com/jhunters/jprotobuf)  
  Guava | 玩家数据缓存系统 | [https://github.com/google/guava](https://github.com/google/guava)  
  Jedis | 跨服数据内存数据库 | [https://redis.io](https://redis.io/)  
  quartz | job调度任务 | [http://www.quartz-scheduler.org/](http://www.quartz-scheduler.org/) 
  groovy | 基于类替换的热更新 | [http://www.groovy-lang.org/](http://www.groovy-lang.org/)　　  
  proxool | mysql数据链接池 | [http://proxool.sourceforge.net/](http://proxool.sourceforge.net/)   
  slf4j+log4j | 日志系统 | [https://www.slf4j.org/](https://www.slf4j.org/)  
  maven | 依赖管理及项目构建 | [http://maven.apache.org/](http://maven.apache.org/)  


  ## ToDoList    
  * 跨服玩法基础  
  * 登录服工程  
  * 更多基础设施与业务演示  
  

  ## 快速开始  
  1. 使用git下载代码 git clone https://github.com/kingston-csj/jforgame;  
  2. 将代码导入带有maven插件的IDE(选择主目录下的pom.xml文件);  
  3. 新建数据库game_data_001和game_user_001，并分别导入config下的同名sql文件;  
  4. 启动服务端，入口为ServerStartup类（开发工具需要将src同目录的configs视为代码目录！）;  
  5. 启动客户端，入口为ClientStartup类;


  各模块demo教程 --> [wiki](https://github.com/kingston-csj/jforgame/wiki/Examples)  

  本栏目详细教程 --> [csdn博客](http://blog.csdn.net/column/details/16043.html)

  欢迎star/fork，欢迎学习/使用，期待一起贡献代码！！

  ## 一起交流
  如果您发现bug，或者有任何疑问，请提交issue !!
  
