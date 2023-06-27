# 介绍
本代码主要是模拟了一个产生full gc 的案例，使用者可以根据该代码进行相关jvm调优的相关操作

# 如何使用
jvm启动参数
```shell
 -Xms1536M -Xmx1536M -Xmn512M -Xss256K -XX:SurvivorRatio=6  -XX:MetaspaceSize=256M -XX:MaxMetaspaceSize=256M  -XX:+UseParNewGC  -XX:+UseConcMarkSweepGC  -XX:CMSInitiatingOccupancyFraction=75 -XX:+UseCMSInitiatingOccupancyOnly             
```
1. 启动main程序，使用`jstat -gc 进程号 2000 10000` 发现不会出现full gc
2. 打开测试test包下的文件，并运行，发现频繁出现full gc
3. 用户可根据具体情况进行调优，具体可以参考文章: [JVM调优](https://2290653824.github.io/pages/f070cc/)

# 学习视频
图灵课堂架构师第五期：`10.7 JVM调优工具详解及调优实战`
