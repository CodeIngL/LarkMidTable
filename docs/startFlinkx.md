## 1.查看shell脚本

使用idea打开flinkx项目，查看bin/flinkx文件

```
JAVA_RUN="java"
JAR_DIR=$FLINKX_HOME/lib/*    
CLASS_NAME=com.dtstack.flinkx.launcher.Launcher
$JAVA_RUN -cp $JAR_DIR $CLASS_NAME $@ &

# 1.java的命令
# 2.查看lib文件,flinkx-launcher-1.6.jar 
# 3.加载的主类
# 4.$@为传递的参数
# 5.&为后端运行
# 6.翻译解释
# java -cp flinkx-launcher-1.6.jar com.dtstack.flinkx.launcher.Launcher $@ &

```

## 2.查看Launcher类

找到main方法 118行 ，本地模式

实际上调用  com.dtstack.flinkx.Main类

1.获取传递的参数，78-84行

2.解析我们jobpath传递的json文件，得到具体的reader和writer类名，87行

3.StreamExecutionEnvironment ，调用Datastream的环境 103行

4.设置读的reader    114行

5.设置写的writer      124行

6.得到执行的结果      138行




