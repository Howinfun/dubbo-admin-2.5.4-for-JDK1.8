# dubbo-admin-jdk1.8

一、Dubbo-admin-2.5.4如果在jdk为1.8的环境下部署tomcat启动是会报错的。

因为com.alibaba.citrus.service.uribroker.uri.GenericURIBroker的UserType的set方法不符合JDK1.8的标准

二、解决方法：
 1.更换服务器的JDK
 2.修改dubbo-admin tomcat默认的JDK
 3.修改dubbo-admin项目的依赖，然后重新打包
	1.webx的依赖改为3.1.6版
	2.添加velocity的依赖，用了1.7
	3.对依赖项dubbo添加exclusion，避免引入旧spring
	4.webx已有spring 3以上的依赖，因此注释掉dubbo-admin里面的spring依赖
	参考博客：https://blog.csdn.net/blue_dd/article/details/51298438
 
三、这里已经是解决好的并且已编译的，直接拿去就可以用了。
	解压到Tomcat的webapps下，然后修改WEB-INF下的dubbo.properties即可。