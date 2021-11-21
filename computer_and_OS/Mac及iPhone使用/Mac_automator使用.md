# Mac_automator使用

what is automator(自动操作) on a mac?

Automator 是苹果公司为他们的Mac OS X系统开发的一款软件。只要通过点击拖拽鼠标等操作就可以将一系列动作组合成一个工作流程，从而帮助你自动的（可重复的）完成一些复杂的工作。Automator还能横跨很多不同种类的程序，包括：访达（Finder）、Safari网络浏览器、iCal、地址簿或者其他的一些程序。它还能和一些第三方的程序一起工作<sub>[1]</sub>。

PS: Starting in macOS Monterey, Automator is being replaced by Shortcuts<sub>[2]</sub>.

## 接口

自动操作提供了图形化的界面用来建立工作流，所以你不需要熟悉编程或者脚本语言。任务可以在操作的时候被记录下来，也可以从列表里选择。上一个动作的输出可以是下一个动作的输入。

不过，看起来用脚本会更灵活些，支持的脚本包含AppleScript，JavaScript（但似乎不是标准的JS），Shell Script等。

AppleScript简单的入门学习<sub>[3]</sub>，比如：

```AppleScript
tell application "/Applications/Kindle.app" to activate
```

或者（下面的命令需要替换路径为实际路径及工作空间名）：

```AppleScript 
tell application "Visual Studio Code" to open "/Users/your_user_name/notebook/notebook.code-workspace"
```

## 程序特点

自动操作实际上是一些列动作（文件重命名，找链接的图片、写邮件等等）组合在一个工作流文档里。工作流文档用来执行一系列的重复劳动，可以保存和重复执行。Unix命令行操作或者AppleScript也可以被当作一个动作在流里面执行。工作流也可以另存为一个程序，一个工作流文件，或者菜单项。在工作流创建或者执行的时候，是可以设置一些选项的。

## 比较方便的一些操作

1. 退出所有程序
   1. 但可以选择排除一些特定的程序不退出。

## 参考及引用

[1] Automator. Wikipedia. <https://zh.wikipedia.org/wiki/Automator>
[2] List of macOS components. Wikipedia. <https://en.wikipedia.org/wiki/List_of_macOS_components#Automator>
[3] 《AppleScript 入门：探索 macOS 自动化》. 少数派. <https://sspai.com/post/46912>
