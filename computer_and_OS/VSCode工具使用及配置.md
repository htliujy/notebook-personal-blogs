# VSCode工具使用及配置

使用的插件：
[C/C++]([https://link](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools))
[Anaconda Extension Pack](https://marketplace.visualstudio.com/items?itemName=ms-python.anaconda-extension-pack)
[Chinese (Simplified) Language Pack for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=MS-CEINTL.vscode-language-pack-zh-hans) 汉化
[LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
[Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
[Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)
算了，其他先不列举了。

## 快捷键

| 快捷键               | 功能            |
| -------------------- | --------------- |
| ctrl+shift+k         | 删除整行        |
| fn + control + space | trigger suggest |

代码格式化：  
On Windows 　　Shift + Alt + F
On Mac 　　Shift + Option + F
On Ubuntu　　 Ctrl + Shift + I

代码提示：  
正常： Ctrl + Space，但这个在mac上被系统占用了
替代：fn + control + space
也可以自己设置，Code > Preferences > Keyboard Shortcuts, Search for "Trigger Suggest". The default value is ⌃Space.

## 设置

1. 自动识别编码：`files.autoGuessEncoding`;
2. 窗口放大（字体、布局）：`"window.zoomLevel": 1`;
