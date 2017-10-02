
---------------------------------
自动生成工具的使用(mybatis-generator)
write by 玄子 at 2017.9.29 9:34 二〇一七年九月二十九日
---------------------------------


本工具主要用于自动生成数据库表中对应的
①model类(.java文件)
②mapper接口(.java文件)
③mapper映射文件(.xml文件)
---------------------------------

---------------------------------
使用步骤：
⑴修改配置文件src/main/resources/generatorConfig.properties
	--基本只需修改#目标包和#连接数据库参数(有“xuanzi”的部分，参照备份文件generatorConfig2.properties)
	--视情况修改#数据库驱动

⑵src/main/resources/mybatis/generatorConfig.xml
	--在文件底部添加<table/>标签，(需配置几个表，即写几个table)

⑶运行maven 配置项
(初始需添加配置一个maven运行命令，Command line:“mybatis-generator:generate -e”)

⑷生成三个包文件(②mapper接口和③mapper映射文件最终会编译到同一个mapper目录下)
	--src\main\java\com\xuanzi\demo\model	(model类)
		--文件放置与目录一致

	--src\main\java\com\xuanzi\demo\mapper	(mapper接口)
		-->文件最终放到src\main\java\com\xuanzi\demo\mapper 下(目录一致)

	--src\main\resources\com\xuanzi\demo\mapper	(mapper映射文件)
		-->文件最终放到src\main\resources\com\xuanzi\demo\mapper 下(目录一致)

---------------------------------
