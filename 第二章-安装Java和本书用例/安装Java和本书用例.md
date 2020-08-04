# 第二章 安装Java和本书用例

现在，我们来为这次阅读之旅做些准备吧！

在开始学习Java之前，你必须要先安装好Java和本书的源代码示例。因为考虑到可能有“专门的初学者”从本书开始学习编程，所以我会详细地教你如何使用命令行，如果你已经有此方面的经验了，可以跳过这段安装说明。如果你对此处描述的任何术语或过程仍不清楚，还可以通过Google去搜索找到答案。具体问题或困难请试着在StackOverflow上提问。或者去TouTube看有没有相关的安装说明。

## 编辑器

首先你需要安装一个编辑器来创建和修改本书用例里的Java代码。有可能你还需要使用编辑器来更改系统配置文件。

相比一些重量级的IDE（Integrated Development Environments，集成开发环境），如Eclipse、NetBeans和Intelij IDEA（译者注：做项目强烈推荐IDEA），编辑器是一种更纯粹的文本编辑器。如果你已经有了一个用着顺手的IDE，那就可以直接用了。为了方便后面的学习和统一下教学环境，我推荐大家使用Atom这个编辑器。大家可以在atom.io上下载。

Atom是一个免费开源、易于安装且跨平台（支持Windows、Mac和Linux）的文本编辑器。内置支持Java文件。相比于IDE的厚重，它比较轻量级，是学习本书的理想工具。Atom包含了许多方便的编辑功能，相信你一定会爱上它！更多关于Atom使用的细节问题可以到它的网站上寻找。

还有很多其他的编辑器。有一种亚文化的群体，他们热衷于争论哪个更好用！如果你找到一个你更喜欢的编辑器，换一种使用也没什么难度。重要的是，你要找一个用着舒服的。

## Shell

如果你之前没有接触过编程，那么有可能对Shell（命令行窗口）不太熟悉。shell的历史可以追溯到早期的计算时代，当时在计算机上的操作都是通过输入命令进行的，计算机通过回显响应。所有的操作都是基于文本的。

尽管和现在的图形用户界面相比，Shell操作方式很原始。但是同时shell也为我们提供了许多有用的功能特性。在学习本书的过程中，我们会经常使用到Shell，包括现在这部分的安装，还有运行Java程序。

Mac：单击聚光灯（屏幕右上角的放大镜图标），然后键入terminal。单击看起来像小电视屏幕的应用程序（你也可以单击“return”）。这就启动了你的用户下的shell窗口。

windows：首先，通过目录打开windows资源管理器：

- windows 7：单击屏幕左下角的“开始”图标，输入“explorer”后按回车键。
- windows 8：按Windows + Q，输入“explorer”后按回车键。
- windows 10：按Windows + E打开资源管理器，导航到所需目录，单击窗口左上角的“文件”选项卡，选择“打开Windows PowerShell”启动Shell。

Linux：在home目录打开Shell。

- Debian：按Alt+F2，在弹出的对话框中输入“gnome-terminal”
- Ubuntu：在屏幕中鼠标右击，选择“打开终端”，或者按住Ctrl+Alt+T
- Redhat：在屏幕中鼠标右击，选择“打开终端”
- Fedora：按Alt+F2，在弹出的对话框中输入“gnome-terminal”

### 目录

目录是Shell的基础元素之一。目录用来保存文件和其他目录。目录就好比树的分支。如果书籍是你系统上的一个目录，并且它有两个其他目录作为分支，例如数学和艺术，那么我们就可以说你有一个书籍目录，它包含数学和艺术两个子目录。注意：windows使用“\\\”而不是“\\/”来分隔路径。

### Shell基本操作

我在这展示的Shell操作和系统中大体相同。出于本书的原因，下面列举一些在Shell中的基本操作：

```bash
更改目录： cd <路径> 
          cd .. 移动到上级目录 
          pushd <路径> 记住来源的同时移动到其他目录，popd 返回来源

目录列举： ls 列举出当前目录下所有的文件和子目录名（不包含隐藏文件），
             可以选择使用通配符 * 来缩小搜索范围。
             示例(1)： 列举所有以“.java”结尾的文件，输入 ls *.java (Windows: dir *.java)
             示例(2)： 列举所有以“F”开头，“.java”结尾的文件，输入ls F*.java (Windows: dir F*.java)

创建目录： 
    Mac/Linux 系统：mkdir  
              示例：mkdir books 
    Windows   系统：md 
              示例：md books

移除文件： 
    Mac/Linux 系统：rm
              示例：rm somefile.java
    Windows   系统：del 
              示例：del somefile.java

移除目录： 
    Mac/Linux 系统：rm -r
              示例：rm -r books
    Windows   系统：deltree 
              示例：deltree books

重复命令： !!  重复上条命令
              示例：!n 重复倒数第n条命令

命令历史：     
    Mac/Linux 系统：history
    Windows   系统：按 F7 键

文件解压：
    Linux/Mac 都有命令行解压程序 unzip，你可以通过互联网为 Windows 安装命令行解压程序 unzip。
    图形界面下（Windows 资源管理器，Mac Finder，Linux Nautilus 或其他等效软件）右键单击该文件，
    在 Mac 上选择“open”，在 Linux 上选择“extract here”，或在 Windows 上选择“extract all…”。
    要了解关于 shell 的更多信息，请在维基百科中搜索 Windows shell，Mac/Linux用户可搜索 bash shell。

```

## Java安装

为了编译和运行代码示例，首先你必须安装JDK（Java Development Kit，JAVA软件开发工具包）。本书中采用的是JDK 8。

### Windows

1. 以下为Chocolatey的安装说明。
2. 在命令行提示符下输入下面的命令，等待片刻，结束后Java安装完成并自动完成环境变量设置。

```bash'
choco install jdk8
```

### Nacubrish

Mac 系统自带的Java版本太老了，为了确保本书的代码示例能背正确执行，你必须将它更新到Java 8。我们需要管理员权限来运行下面的步骤：

1. 以下为HomeBrew的安装说明。安装完成后执行命令brew update更新到最新版本
2. 在命令行下执行下面的命令来安装java。

```bash
brew cask install java
```

当以上安装都完成后，如果你有需要，可以使用游客账户来运行本书中的代码示例。

### Linux

- Ubuntu/Debian:

```bash
sudo apt-get update
sudo apt-get install default-jdk
```

- Fedora/Redhat

```bash
    su-c "yum install java-1.8.0-openjdk"(注：执行引号内的内容就可以安装)
```

## 校验安装

打开新的命令行输入：

```bash
java -version
```

正常情况下你应该看到以下类似信息（版本号信息可能不一样）：

```bash
java version "1.8.0_112"
Java(TM) SE Runtime Environment (build 1.8.0_112-b15)
Java HotSpot(TM) 64-Bit Server VM (build 25.112-b15, mixed mode)
```

如果提示命令找不到或者无法被识别，请根据安装说明重试；如果还不行，尝试到StackOverflow寻找答案。

## 安装和运行代码示例

当Java安装完毕，下一步就是安装本书的代码示例了。安装步骤所有平台一致：

1. 从GitHub仓库中下载本书代码示例
2. 解压到你所选目录里。
3. 使用Windows资源管理器，Mac Finder，Linux的Nautilus或其他等效工具浏览，在该目录下打开Shell。
4. 如果你在正确的目录中，你应该看到该目录中名为gradlew和gradlew.bat的文件，以及许多其他文件和目录。目录与书中的章节相对应。
5. 在shell中输入下面的命令运行：

```bash
     Windows 系统：
          gradlew run

     Mac/Linux 系统：
        ./gradlew run
```

第一次安装时Gradle需要安装自身和其他的相关的包，请稍等片刻。安装完成后，后续的安装将会快很多。

注意：第一次运行gradlew命令时必须连接互联网。

### Gradle基础任务

本书构建的大量Gradle任务都可以自动运行。Gradle使用约定大于配置的方式，简单设置即可具备高可用性。本书中“一起去骑行”的某些任务不适用于此或无法执行成功。以下是你通常会使用上的Gradle任务列表。

```bash
    编译本书中的所有 java 文件，除了部分错误示范的
    gradlew compileJava

    编译并执行 java 文件（某些文件是库组件）
    gradlew run

    执行所有的单元测试（在本书第16章会有详细介绍）
    gradlew test

    编译并运行一个具体的示例程序
    gradlew <本书章节>:<示例名称>
    示例：gradlew objects:HelloDate
```