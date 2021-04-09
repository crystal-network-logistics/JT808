
**易联车联网网关中间件** 

易联车联网网关中间件采用微内核架构，以netty/mina作为底层通讯架构，是一个基于JT/T808 2011《道路运输车辆卫星定位系统终端通信协议及数据格式》、JT/T808 2013《道路运输车辆卫星定位系统北斗兼容车载终端通信协议技术规范》、《JT/T808 2019道路运输车辆卫星定位系统终端通讯协议及数据格式》、《JT/T 1078道路运输车辆卫星定位系统视频通信协议》、苏标ADAS《道路运输车辆主动安全智能防控系统（通讯协议规范）》协议等808协议的协议网关中间件。网关中间件独立于其他业务系统，通过消息中间件（json消息传输，支持RabbitMQ/ActiveMQ）与业务平台进行交互，能够无缝接入各种异构系统，协助企业快速构建车联网平台。

**技术特点** 

1、软件绿色免安装      
2、软件架构特点详情请参考：https://www.legaoyi.com/elink-jt808-gateway.html          
3、软件平台演示地址：https://iov.legaoyi.com (点击体验账号登录即可)        
4、技术支持QQ：78772895 574360187（QQ群）    
5、若不想编译打包源码，可直接下载打包好的应用程序，下载地址：https://www.legaoyi.com/software.html  

**设备模拟器**     
可配合车载设备模拟器进行测试跑通部标808协议整个流程，下载地址：https://www.legaoyi.com/software.html          
设备模拟器支持协议：          
jT/T 808 2011----模拟0200消息          
jT/T 808 2013----模拟0200、0704、0702等消息          
jT/T 808 1078----模拟音视频、音频、对讲等功能          
苏标 T/JSATL ----模拟ADAS等告警以及告警附件上传功能          


**版本对比** 

|特性|免费版|旗舰版|说明|
|:----    |:----    |:--- |-----   |
|JT/T808协议2011版本 |大部分支持|支持 |免费版本暂时不支持分包消息，可根据需要自行开发扩展|
|JT/T808协议2013版本 |不支持  |支持 |    |
|JT/T808协议2019版本 |不支持  |支持 |    |
|JT/1078协议 |不支持  |支持 |    |
|苏标T/JSATL协议 |不支持  |支持 |    |
|JT/T1257协议 |不支持  |支持 |    | 
|JT/T905协议 |不支持  |支持 |    |出租车
|GB 32960协议 |不支持  |支持 |    |新能源汽车 
|同族协议扩展 |支持  |支持 |旗舰版支持各种协议的扩展，包括808协议以外的各种私有协议    |
|异族协议扩展 |不支持  |支持 |旗舰版支持各种协议的扩展    |
|终端接入数量 |500台  |不限制 |    |
|通讯架构 | mina | netty |    |
|性能 | 一般 | 优秀 | mina版本高并发时由于无法及时处理大量并发消息可能导致内存溢出风险  |
|ActiveMQ |支持  |不支持|    |
|RabbitMQ |不支持  |支持|    |
|kafka |不支持  |支持|    |
|集群部署 |不支持  |支持 |    |
|安全策略|不支持  |支持 |是否流量控制、过载保护、数据加密、IP黑名单等安全策略 |

     
**软件运行环境** 

- 操作系统     
操作系统支持window以及linux等，建议使用linux，64位centOS 7以上版本     

- Java环境     
平台的运行依赖java环境，安装jdk1.8以上版本     

- ActiveMQ环境     
平台的运行依赖ActiveMQ环境，ActiveMQ安装最新版本    


**程序打包编译**     
maven环境中运行：mvn package appassembler:assemble    

**配置文件** 

软件conf目前下的所有配置文件都必须保留，不能删除，否则将会导致软件无法运行。使用软件时，请根据实际情况修改conf目录下的配置文件application.properties中的activemq配置部分，如下：

************************************************************     
     
#activemq 配置      
spring.activemq.broker-url=tcp://localhost:61616      
spring.activemq.user=admin     
spring.activemq.password=admin     
     
*************************************************************

注：server.tcp.port=6030 该配置为车载终端连接的TCP端口，操作系统防火墙需要开放该端口     

**软件模块** 

1、elink-iov-message-gateway 为协议网关中间件，车载终端连接该软件程序     

2、elink-iov-message-processor  为上行消息处理应用程序，开发者可根据自身业务进行二次开发


**软件运行** 

1、window：双击bin/startup.bat文件即可启动；

2、linux：使用命令启动（注：启动前先赋予该文件startup.sh执行权限，chmod 777 startup.sh）： nohup ./bin/startup.sh & 


本软件为免费版本，觉得好用请支持正版软件，后续会陆续退出更多免费的版本，敬请关注，谢谢！    

**捐助** 
   
若喜欢，请支持，谢谢！

![image](https://www.legaoyi.com/images/pay.png) 






