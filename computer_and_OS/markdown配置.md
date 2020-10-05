# markdown配置

markdown初看起来非常简单，不过，有些东西配置起来还是挺琐碎甚至烦人的的，比如：

- 公式在不同的渲染器，不同的平台，有不同的语法；
- 图片默认展示的方式大小有很大差异；

关于这些，这些我期望配置并使用同样的编写方式，在不同平台上展示出来是一样的。其他不兼容的语法尽量不使用，虽然找一个好用好记又在各个平台上效果一致的语法比较烦，但这是值得的。

另外，有些东西配置起来又比较有趣，比如：

- snippets配置
- 公式自动补齐
- 预览
- 导出pdf（这个没有配置）

## 工具

- 将Excel表格等转换为Markdown的在线工具：[tableconvert](https://tableconvert.com/)

## 字体

一般需要用到不同字体及颜色，可以用html的方式，比如：

```html
<font face="黑体" color=red size = 10>你好啊！</font>
```

<font face="黑体" color=red size = 10>你好啊！</font>

## 插件配置

1、预览
[Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)

| Shortcuts                   | Functionality              |
| --------------------------- | -------------------------- |
| cmd-k v or ctrl-k v         | Open preview to the Side   |
| cmd-shift-v or ctrl-shift-v | Open preview               |
| ctrl-shift-s                | Sync preview / Sync source |
| shift-enter                 | Run Code Chunk             |
| ctrl-shift-enter            | Run all Code Chunks        |
| cmd-= or cmd-shift-=        | Preview zoom in            |
| cmd-- or cmd-shift-_        | Preview zoom out           |
| cmd-0                       | Preview reset zoom         |
| esc                         | Toggle sidebar TOC         |

2、公式自动补齐
[Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one),Markdown Support for Visual Studio Code

## 公式编辑

在gitbook，嵌入inline公式和block公式（一般写的是inline和display，但是我不是很理解display，所以我用blockmath这种说法），都是使用的一样的标识符：两个美元字符开头\$\$，两个美元字符结尾\$\$，唯一的区分就是，在写的时候换行；
但是在默认的markdown中，比如我在VSCode中下载的markdown的插件，使用单个美元字符表示inline math，使用两个美元字符代表bockmath。

### block公式

测试一：

```Latex
$$
{ax^2+bx+c=0}
$$
```

$$
{ax^2+bx+c=0}
$$

 vscode：成功；
 gitbook：成功；

测试二：

```Latex
$$
\displaystyle \int^{L}_{x=0}I_ddx = \int^{V_{DS}}_{V=0}WC_{ox}(V_{GS}-V(x)-V_{TH})\mu_ndV\tag{1.2.0}
$$
```

效果如下
$$
\displaystyle \int^{L}_{x=0}I_ddx = \int^{V_{DS}}_{V=0}WC_{ox}(V_{GS}-V(x)-V_{TH})\mu_ndV\tag{1.2.0}
$$

 vscode：成功；
 gitbook：成功；

### inline

测试一：

```Latex
$$ax^2+bx+c=0$$
```

求一元二次方程$$ax^2+bx+c=0$$的解。

 vscode：成功，但需要配置"markdown-preview-enhanced.mathInlineDelimiters"；
 gitbook：成功；

测试二：

```Latex
\(inline\) and \[display\]
```

能否用下面的方式：\(inline\) and \[display\]

 vscode：成功
 gitbook：不成功

测试三：

```Latex
{% math %}\int_{-\infty}^\infty g(x) dx{% endblock %}
```

{% math %}\int_{-\infty}^\infty g(x) dx{% endblock %}

 vscode：不成功，基本只是显示原文  
 gitbook：不成功，但是认出了\{% math %\}，这个没有显示。

测试四：

```Latex
$$a=b*\frac{1}{2}$$
```

 Here is some inline math: $$ a = b*\frac{1}{2} $$ 

 vscode： 成功  
 gitbook： 成功

对应的配置是这样的：

```json
    "markdown-preview-enhanced.mathInlineDelimiters": [
        [
            "$$",
            "$$"
        ],
        [
            "$",
            "$"
        ],
        [
            "\\(",
            "\\)"
        ]
    ],
    "markdown-preview-enhanced.mathBlockDelimiters": [
        [
            "$${",
            "}$$"
        ],
        [
            "\\[",
            "\\]"
        ]
    ],
```

另外，当我的windows的解释器莫名奇妙改成了KateX，我就将配置添加了两个，就解决了，如下：

```json
{
    "markdown.extension.math.enabled": false,
    "markdown-preview-enhanced.mathRenderingOption": "MathJax",
}
```

但是，有里两个疑问：

1. Windows上，我只要改变 "markdown-preview-enhanced.mathRenderingOption" 从KateX改为MathJax就能成功，但我在Mac上这样改动是不会成功的，why？
2. 为什么我将"markdown.extension.math.enabled"这个设置成了false，math公式的解释器仍然启动了呢？

### 多行的blockmath

但是，多行的公式该如何换行呢？

测试一：

```Latex
$$
\begin{align}
x &= v_0\cos\theta t \tag{1} \\
y &= v_0\sin\theta t - \frac{1}{2}gt^2 \tag{2}
\end{align}
$$
```

$$
\begin{align}
x &= v_0\cos\theta t \tag{1} \\
y &= v_0\sin\theta t - \frac{1}{2}gt^2 \tag{2}
\end{align}
$$

 vscode： 成功  
 gitbook： 成功

测试二：

```Latex
$$
\begin{aligned}
E_{max}&=\frac{1}{2}I_{max}^2 L\\
&=\frac{1}{2}\frac{(B_{max}NA_e)^2}{L}
\end{aligned} \tag{2.1}
$$
```

$$
\begin{aligned}
E_{max}&=\frac{1}{2}I_{max}^2 L\\
&=\frac{1}{2}\frac{(B_{max}NA_e)^2}{L}
\end{aligned} \tag{2.1}
$$

 vscode： 成功  
 gitbook： 成功

 所以，就是说，\begin{aligned}和\begin{aligned}这样的语法是支持的，但需要注意，这个和美元符号（开始和结束符号）之间需要换行。同时，还有个bug，Katex好像不支持\begin{align}，但是支持\begin{aligned}这种，可如果用\begin{aligned}，MathJax似乎不支持多个tag，如下不成功:

```Latex
$$
\begin{aligned}
x &= v_0\cos\theta t \tag{1} \\
y &= v_0\sin\theta t - \frac{1}{2}gt^2 \tag{2}
\end{aligned}
$$
```

$$
\begin{aligned}
x &= v_0\cos\theta t \tag{1} \\
y &= v_0\sin\theta t - \frac{1}{2}gt^2 \tag{2}
\end{aligned}
$$

 vscode： 不成功  
 gitbook： 不成功

## 图片展示

使用html语法，这样既方便配置，也好不同平台展现更一致。
如下是我简单的图片插入方式。

```html
<div  align="center">
<img src="图片路径及文件名" width = "100%" height = "100%" alt="图片名称" align=center />
</div>
```

或者复杂一些的

```html
<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    src="./为什么要增加开关电源的开关频率/figure1_buck_current.png">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">图1.0 buck电路</div>
</center>
```

## snippets配置

snippets如何配置，详情请查看微软官方的[Snippets in Visual Studio Code](https://code.visualstudio.com/docs/editor/userdefinedsnippets#_variables)
我当前的配置，（但我决定要改）

```json
{
 // Place your snippets for markdown here. Each snippet is defined under a snippet name and has a prefix, body and 
 // description. The prefix is what is used to trigger the snippet and the body will be expanded and inserted. Possible variables are:
 // $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. Placeholders with the 
 // same ids are connected.
 // Example:
 // "Print to console": {
 // "prefix": "log",
 // "body": [
 // "console.log('$1');",
 // "$2"
 // ],
 // "description": "Log output to console"
 // }

 "HEADER":{
  "prefix": "md_header",
  "body": [
  "---",
  "title: $TM_FILENAME_BASE",
  "date: $CURRENT_YEAR/$CURRENT_MONTH/$CURRENT_DATE $CURRENT_HOUR:$CURRENT_MINUTE:$CURRENT_SECOND",
  "categories: $0",
  "tags:",
  " - ",
  "mathjax: true",
  "---",
  "## 摘要",
  "",
  "<!-- more -->"
  ],
 },
 //"figure insert":{
 //"prefix": "figure",
 //"body": [
 //"![$0]()"
 //],
 //},
 "figure insert":{
 "prefix": "figure",
 "body": [
 "<div  align=\"center\">",
 "<img src=\"./$0\" width = \"100%\" height = \"100%\" alt=\"图片\" align=center />",
"</div>"
  ],
 },
 "inline math":{
 "prefix": "inlinemath",
 "body": "$${$0}$$"
},
 "block math":{
 "prefix": "blockmath",
 "body": [
  "$$",
  "\\begin{aligned}",
  "",
  "\\end{aligned}\\tag{$0}",
  "$$"
  ]
 },
}
```

一些周边配置：
编辑器字体大小设置：editor.fontSize:16（默认是14，我改成16）

2020年10月18日
忽然很想说脏话，因为我的VScode忽然挂了，不能正常解析我的math公式，我现在不知道出了什么问题，但若是要用Time Machine恢复我的电脑，我是拒绝的。
Parse Error: KaTex Parse error: No such environment: align at position 7: \begin{aligned}
可是，我的配置明明没有改，仍然使用的是：

```json
    "markdown-preview-enhanced.mathRenderingOption": "MathJax",
```

为什么最后帮忙解析的是KaTex，难道是忽然MathJax挂了，所以又调用了KaTex？，那为什么MathJax不报错？

我看了一下，我的typora是正常的。

不过说起来，我刚刚更新了typora，You’re up-to-date!Typora Beta 0.9.9.35.2 is currently the newest version available.

难道这也有鬼？

他妈的，找不到原因，可是，我本来计划好了，等过两个月，完整重装Macbook Pro的啊！因为可能我是一直没有重装过我的mac OS，我就觉得越来越乱，就想重装，你这样是逼我尽早重装？
那也不能，我还是得坚持用typora多两个月（因为我找不到简单的解决办法），等吧！想就这样逼我，没门！

20201019:

我更加困惑了，因为，现在我发现不同的预览打开方式，得到的公式渲染相差太远.  

[用vscode写markdown的正确姿势](https://blog.csdn.net/zyx_ly/article/details/89642315)
:vscode默认是支持markdown的，只需要装一个预览插件神器：Markdown Preview Enhanced。
安装完成之后，键盘输入"Ctrl + K, V"，即可调出预览视图。

"Cmd + K, V"这个快捷键和我用鼠标点右上角的preview，得到的结果是不同的，他妈的。