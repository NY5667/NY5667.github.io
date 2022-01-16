---
layout: post
title:  "如何在 ubuntu 18.04 上安装 java 17 LST（JDK 17）"
date:   2022-01-16 09:53:42 +0800
categories: NY5667 update
---
[参考文章（how-to-install-java-17-lts-jdk-17-on-ubuntu-20-04）][how-to-install-java-17-lts-jdk-17-on-ubuntu-20-04]
## 安装 Java JDK 17 – 手动方法
### 下载最新的 Java 17 版本
下载[Oracle Java 17][Oracle-Java-17]
```bash
wget https://download.oracle.com/java/17/archive/jdk-17.0.1_linux-x64_bin.deb
```
### 配置和安装 Java 17
安装jdk-17
```bash
sudo dpkg -i jdk-17_linux-x64_bin.deb
``` 
 更新配置
```bash
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk-17/bin/java 1
sudo update-alternatives --install /usr/bin/javac javac /usr/lib/jvm/jdk-17/bin/javac 1
```
查看Java版本
```bash
java --version
javac --version
```
更新Java配置
```bash
sudo update-alternatives --config java
```
现在你需要去设置环境变量如下：
```bash
sudo gedit /etc/profile
```
```bash
JAVA_HOME=/usr/lib/jvm/jdk-17
```
```bash
source /etc/profile
```
Java 17 现在已经安装。去确认，用如下命令：
```bash
echo $JAVA_HOME
```

### 测试 Java - 创建Hello World 应用程序
最后, 测试所有程序都正确安装是非常难的。简单的方法是创建一个小程序脚本来测试著名的Hello World。

首先，按如下方式创建Java程序文件：
```bash
touch hello.java
```
```bash
gedit hello.java
```
接下来，将以下Java代码添加到文件中：
```java
public class hello {
  public static void main(String[] args) {
    System.out.println("G'day from LinuxCapable!");
  }
}
```
接下来，编译代码：
```bash
javac hello.java
```
最后，使用以下命令运行Java代码：
```bash
java hello
```

[Oracle-Java-17]: https://www.oracle.com/java/technologies/downloads/#JDK17
[how-to-install-java-17-lts-jdk-17-on-ubuntu-20-04]: https://www.linuxcapable.com/how-to-install-java-17-lts-jdk-17-on-ubuntu-20-04/