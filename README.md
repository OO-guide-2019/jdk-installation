# JDK安装配置指南

在我们开始使用Java编写、运行程序之前，我们首先需要手动配置JDK。

本文将简单讲述JDK的一般配置过程。

## 下载JDK

首先，我们需要在官方网站上下载JDK安装包。

网站链接：[https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)。或者百度搜索JDK，也可以找到官网链接。（**注意：推荐在官方网站上下载。**）

### 下载版本的选择

#### 对于Windows用户

- 如果你的操作系统字长为64位，则选择Windows x64版本。
- 如果你的操作系统字长为32位，则选择Windows x86版本。

#### 对于Linux或MacOS用户

对于非Windows的用户，则需要按照自己操作系统的类型自行进行选择。

## 安装与配置

### 安装JDK

直接运行安装下载下来的安装包文件即可。（Linux和MacOS操作类似）

### 配置环境变量

安装完毕后，我的电脑右键属性，点击左边的`高级系统设置`，点击`高级`-->`环境变量`。

（本部分将围绕windows进行讲解，Linux和MacOS的配置方式可以自行了解）

#### JAVA_HOME

在下方系统变量栏中，新建环境变量`JAVA_HOME`。

变量值为`C:\Program Files\Java\jdk1.8.0_101`（具体路径因安装路径而异，不要包含`bin`）。

如下图所示

![](http://misaka-oss.oss-cn-beijing.aliyuncs.com/cs/oo_assistant_files/installation/pic-1.png)

#### CLASSPATH

在系统变量栏中，新建变量`CLASSPATH`，变量值为`.;%JAVA_HOME%\lib;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;`。

（注意，一定要留有前面的`.`符号）

如下如所示：

![](http://misaka-oss.oss-cn-beijing.aliyuncs.com/cs/oo_assistant_files/installation/pic-2.png)

#### PATH

在系统环境变量中，设置`PATH`，变量值`%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;`（**不要覆盖掉原本的内容，将这个值加入到`PATH`的最前面**）。

如下图所示：

![](http://misaka-oss.oss-cn-beijing.aliyuncs.com/cs/oo_assistant_files/installation/pic-3.png)

## 其他

### 常见疑问的解答

#### 如何知道我操作系统（Windows）的字长？

对于Windows10系统，可以右键我的电脑，进入属性，查看即可查看操作系统类型。（具体细节可能略有差异，更多细节可以百度）

对于Linux和MacOS系统，一般也有类似的通过GUI或者命令行的方式查看系统信息，具体可以自行百度。

#### 如何知道是否已经完成了安装呢？

打开`cmd`（Linux或MacOS下的终端），输入`java`，应该出现类似这样的内容。

![](http://misaka-oss.oss-cn-beijing.aliyuncs.com/cs/oo_assistant_files/installation/pic-4.png)

#### 系统评测机使用的Java版本是什么呢？

Java版本：`java -version`

```
java version "1.8.0_101"
Java(TM) SE Runtime Environment (build 1.8.0_101-b13)
Java HotSpot(TM) 64-Bit Server VM (build 25.101-b13, mixed mode)
```

Javac版本：`javac -version`

```
javac 1.8.0_101
```

#### 是否必须使用官方版本的JDK呢？OpenJDK是否可以呢？

推荐使用官方版本的JDK（不过具体的版本号不需要严格一致，保证是`java 1.8.0`即可）

OpenJDK的话，在绝大部分场合下问题不大，但是课程组没有就所有的细节做过相关的具体测试，故不保证不会出现因为OpenJDK版本问题导致的评测异常，还请大家自行选择判断。（另：如果你是Mac或者Linux用户的话，OpenJDK安装会远比Oracle JDK方便）

