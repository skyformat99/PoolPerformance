工具说明
---
JDBC连接池性能测试

测试目标
---
以单线程或多线程访问连接池100万次，并打印耗时分布，平时耗时，失败次数等，最后依据平均耗时对各连接池进行排名。

单次耗时说明
---
1：取连接耗时 [datasource.getConenciton(), conneciton.close()]

2：查询耗时   [datasource.getConenciton(), conneciton.prepareStatement(), statement.execute(), conneciton.close()]

连接池清单(版本请见lib目录)
---
1：DBCP，       老牌连接池

2：DBCP2        老牌连接池

3：C3P0         老牌连接池

4：TOMCAT-JDBC  Tomcat新开发的连接池

5：Vibur        (暂未了解)

6：Druid        德鲁伊连接池(阿里知名JDBC专家温少开发)

7：HikariCP    ‘光’连接池(美国大咖开发，被很多人追捧为Java世界最快的连接池)

8：BeeCP       小蜜蜂连接池（学习锻炼小作品，请从这里 (https://github.com/Chris2018998/BeeCP) 下载最新Jar包，并放入lib）

各连接池的性能测试结果，请访问地址：https://github.com/Chris2018998/BeeCP


测试配置与工具:
---
1：Java:     Java8_64(推荐使用最新版本的Java8)

2：Driver：  支持JDBC标准接口的驱动均可

3：CPU:     频率尽量高，推荐使用新版64位多核CPU

4：内存：    8G(尽量高点)


执行文件说明
---
1：run/TestMutilBorrow.bat  (多线程并发取连接：默认1000个线程各自执行1000次）

2：run/TestMutilQuery.bat   (多线程并发取查询：默认1000个线程各自执行1000次）

3: run/TestSingleBorrow     (单线程并发取连接: 默认1个线程各自执行100万次）

4: run/TestSingleQuery.bat  (单线程并发取查询：默认1个线程各自执行100万次）

5: run/TestAll.bat          (执行上述4个测试））

6: run/Link.properties      (测试参数配置文件）

*提示：测试前，请先设置JAVA_HOME(setJAVA_HOME.bat)

测试使用的表
---

DROP TABLE TEST_USER;

CREATE TABLE TEST_USER(

  USER_ID     VARCHAR(10),
  
  USER_NAME   VARCHAR(10)
  
);

可依据实际情况再调整，编译后打包替换文件:lib/performance.jar

交流与讨论
---

Email:Chris2018998@tom.com


