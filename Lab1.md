# Lab 1

本Lab中，我们将学习配置Java环境，编译运行Java环境，并学会使用Atom。

[TOC]

## Java 开发环境配置

学校机房内的电脑已经安装、配置好Java环境。

带了电脑的同学们请在自己电脑上安装配置Java环境。没有带电脑的同学也要认真阅读文档，并在机房电脑上按照下面的步骤查看已经配好的Java环境是怎样的。

> 注：推荐大家使用自己的电脑来编程。学校机房开放时间有限，并且每次编程都来机房不是很方便。



### 一、安装Java：jdk与jre

1. 登录ftp，进入`classes - 16 - 161 程序设计A （戴开宇）- Materials`。

2. 复制安装文件`jre-8u101-windows-x64.exe`与`jdk-8u101-windows-x64.exe`到电脑中。

3. 双击打开这两个安装包，安装过程中不需要额外配置，一直点下一步即可。

4. 安装完成后，打开目录`C:\Program Files\Java` ，可以看到两个文件夹，jre和jdk就安装在这里。 

5. 进入jdk的目录，再进入bin目录。在这个目录中，可以找到`java.exe`和`javac.exe`两个程序，`javac.exe`用来编译Java代码，`java.exe`用来运行编译好的Java程序，几乎所有的Java程序都是使用`javac`和`java`来编译运行的。

6. 这两个程序与常见的应用程序不同，并不是双击打开的。我们需要在命令行中运行这两个程序：在这个目录下按住shift再单击鼠标右键，选择`在此处打开命令行窗口`。 ![](https://cloud.githubusercontent.com/assets/6532225/18418483/f771cf06-7879-11e6-8091-1784317b9a56.png)

7. 在打开的窗口内，输入`javac -version`回车，和`java -version`回车，可以看到如下输出：

   ![](https://cloud.githubusercontent.com/assets/6532225/18418499/3139329c-787a-11e6-9cd7-f25534be647d.png)

8. 但是到目前为止，这两个命令只能在现在这个存放着`java.exe`和`javac.exe`的文件夹中使用。而我们需要做的，就是当我们在其他目录下打开命令行时，命令行也能知道我们运行的`java`和`javac`是`C:\Program Files\Java\jdk1.8.0_101\bin`目录下的两个程序。这个步骤叫做"Java环境配置"。

### 二、Java环境配置

1. 在桌面上右键`计算机`(或者`此电脑`，`我的电脑`，不同系统显示名称可能不同)，点击`属性`:
2. 点击`高级系统设置`
3. 点击`环境变量`
4. 在`系统变量`中，选中名为`Path`的条目，点击编辑。

   ![](https://cloud.githubusercontent.com/assets/6532225/18434149/11c793c8-791e-11e6-9f41-63ea328452e6.png)

   如果使用的是Windows 10，点击新建，输入`C:\Program Files\Java\jdk1.8.0_101\bin`，确定。

   ![](https://cloud.githubusercontent.com/assets/6532225/18434153/14159efe-791e-11e6-87dc-8570af650adf.png)

   命令行会从上图中所有的路径中搜索你输入的命令。在我们把目录添加进去后，不管在哪个文件夹下，命令行都能找到`java`和`javac`。

5. 接下去我们配置`CLASSPATH`。

   在`系统变量`中，点击`添加`，`变量名`填`CLASSPATH`，`变量值`填`.`，确定。

   ![](https://cloud.githubusercontent.com/assets/6532225/18438460/0bc3c558-7934-11e6-8cce-8dd27d1135a2.png)

Windows 7 和 Windows 8 的配置在界面上有一些小区别，可以参考http://jingyan.baidu.com/article/925f8cb836b26ac0dde0569e.html。在这个链接中，还添加了一些其他的路径到Path和CLASSPATH，这个是过时的做法，高版本的Java不需要这样设置。

如果有同学使用其他操作系统，如`Max OS X`，`Linux`等，请在Lab课上或者微信上咨询TA如何配置Java环境。


## Java 程序的编译和运行

1. 将 ftp 上 Lab 目录下的 lab1 文件夹下载到电脑中。

2. 打开 lab1 文件夹，右键`HelloWorld.java`文件，点击`编辑`，会用记事本打开`HelloWorld.java`。阅读代码，这是我们运行的第一个程序，这个程序将输出一句话：Hello World!

3. 回到 lab1 文件夹窗口，并在文件夹下按住 shift 并单击鼠标右键，选择`在此处打开命令行窗口`。这是打开命令行窗口的方法，下文不再重复说明。![](https://cloud.githubusercontent.com/assets/6532225/18440329/48d2607e-793b-11e6-9e3f-0d28592d66dc.png)

4. 首先我们编译`HelloWorld.java`。在命令行中输入`javac HelloWorld.java`并回车，这个命令可以编译`HelloWorld.java`文件。`javac`编译程序的用法是`javac [文件名]`。如果没有报错信息，说明我们成功编译了`HelloWorld.java`，可以注意到，在文件夹中多了个`HelloWorld.class`文件，这个文件就是编译好的二进制程序

5. 在命令行中输入`java HelloWorld`并回车，可以看到运行结果。`java`命令的使用方式是`java [文件名(不带后缀名)]`。`java`命令实际运行的是`HelloWorld.class`，运行时和`HelloWorld.java`无关。

   成功运行样例：

   ![](https://cloud.githubusercontent.com/assets/6532225/18440330/490e75d2-793b-11e6-932c-bd57e4f6d728.png)



Bonus：尝试运行`javac Game2048.java`和`java Game2048`，看看会发生什么？



## Atom的配置与使用

使用记事本编辑代码，再使用命令行来编译运行代码，是非常不方便的，所以我们要借助开发工具的支持。Intellij 是最好的开发工具，但使用起来比较复杂，我们初学时先使用Atom来开发。

### 一、使用Atom打开、编辑文件

1. 如何打开文件夹：在菜单栏选中`File`，再选择`Open Folder`，找到 lab1 目录并打开。 ![](https://cloud.githubusercontent.com/assets/6532225/18446113/60b94816-7953-11e6-89ac-0210df2a1eec.png)
2. 如何新建文件：在左侧工程栏中，右键目录，选择New File。然后输入文件名，回车。![](https://cloud.githubusercontent.com/assets/6532225/18446114/61e520fc-7953-11e6-826a-f4fdb401d098.png)
3. 在左侧工程栏中双击打开想要编辑的文件，编辑完后，记得按`Ctrl+s`或者菜单栏 File - Save 保存。

### 二、在Atom中运行Java程序

在 Atom 中运行 Java 程序需要安装插件，而Atom的插件管理使用Git，我们需要先安装Git。

1. 从 ftp 的 Materials 中下载 `Git-2.10.0-64-bit.exe`，双击安装，除了下图的一步选择第二项`Use Windows's default console window` 之外，其他步骤都直接按`Next` ![](https://cloud.githubusercontent.com/assets/6532225/18446084/2fb6b00a-7953-11e6-9735-55c1c18998d5.png)

2. 安装好后，打开命令行，输入`git`回车，查看环境变量是否已经自动配好。如果没有配好，像配 Java 环境一样，在环境变量中加入下图的路径： ![](https://cloud.githubusercontent.com/assets/6532225/18446082/2c9ac244-7953-11e6-9f7f-6d3bc766b89e.png)

3. 打开Atom，选择 File - Settings，然后在打开的设置窗口中选择 Install： ![Screen Shot 2016-09-07 at 7.16.44 PM](/Users/lifengshuang/Desktop/atom config/Screen Shot 2016-09-07 at 7.16.44 PM.png)

   ​

   ![](https://cloud.githubusercontent.com/assets/6532225/18446053/0d6bfe60-7953-11e6-9f0f-7ac0e93fa0b4.png)

4. 在Search Packages里输入`script-fudan`，回车。等待搜索结果出现后，点击`script-fudan` 中的 `Install`。(使用英文版系统的同学安装出现在第二位的`script`，`script-fudan`是助教为解决在中文版 Windows 中由于编码问题出现乱码而专门上传的) ![](https://cloud.githubusercontent.com/assets/6532225/18446006/cac7be64-7952-11e6-843b-15beaf92260e.png)

5. 等待一段时间安装完成后，打开想运行的文件，然后点击菜单栏的 Package - Script - Run Script 即可运行，也可以使用快捷键`Ctrl+Shift+B`。(重启Atom后Script菜单会出现在菜单中间位置，而不是最下方) ![](https://cloud.githubusercontent.com/assets/6532225/18446032/ed0a7b92-7952-11e6-9ee9-d557645903f3.png)

6. 尝试修改双引号中的`Hello World!`(双引号不能去掉)，让程序输出其他文字：![](https://cloud.githubusercontent.com/assets/6532225/18446005/ca96f8b0-7952-11e6-92f9-02269e657c81.png)



## Lab1 检查项

1. 成功安装 jdk 与 jre
2. 正确配置 Java 环境
3. 使用命令行编译运行一个 Java 程序
4. 正确配置 Atom 并在 Atom 内运行 Java 程序

同学们需要向助教演示第三、第四项。

推荐在自己电脑上演示，如果没带电脑或者由于时间不够或者网络太差等问题来不及在自己电脑上完成的，可以在机房电脑上演示。



> 注：机房电脑中的Atom安装的是`script`而不是`script-fudan`，代码中出现中文很有可能会运行错误，在机房电脑中运行程序的同学请将代码中的中文删除后运行。