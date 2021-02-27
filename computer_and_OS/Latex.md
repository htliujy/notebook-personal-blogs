# Latex

介绍：...

## Image2LaTeX工具

### Image2LaTeX是什么？

有时候需要截图并生成Latex公式，有一个好用的工具：Mathpix Snipping Tool，但是这个工具每个月只能使用50次，再多就要付费了。

但Mathpix有另一个工具：MathpixOCR API，这个工具是图像识别转文本的接口（根据Mathpix的条款，每个账户每月可以免费使用1000次）。

Image2LaTeX：就是一个类似Mathpix Snipping Tool的工具，它的作用就是调用MathpixOCR API，将图像上传，从接口获取转化后的文本，然后再行转换为Latex公式（或者从获取到的文本就是已经转化后的Latex了，不得而知？）。

### Image2LaTeX下载安装

进入github仓库<https://github.com/blaisewang/img2latex-mathpix>就可以找到对应的release下载并安装使用了。没有特殊步骤，不再详解。

### Image2LaTeX如何配置

需要调用MathpixOCR API，就必须要先配置MathpixOCR API Key：

- 进入<https://mathpix.com>
- 登陆自己的账号
- 进入账户配置界面
- 点击OCR APIs
- 根据指引，新建API Keys

注意：  
新建MathpixOCR API Key，需要有信用卡，我用了广发VISA的，首次扣费1美元，且不退回（这没有问题），但他们的条款看起来消费是上不封顶的（按次计费）。感觉若是泄漏了API key，后患无穷！

条款如下：

**Our billing policy**

- First 1K requests are free per month.
- $0.004 per request for 1-100K API calls.
- $0.002 per request for 100K-300K API calls
- $0.001 per request for 300K-infinity API calls
- Billed monthly (1st of every month)

**Setup fee**

- To prevent automated abuse we charge a one-time non-refundable setup fee of $1.

### 如何使用

就是先截图，然后用空格键粘贴到Image2LaTeX，再按enter键就可以调用接口，上传并获取到Latex公式了。

原介绍文档如下：  
Use your operating system's default methods (or other tools) to take a screenshot of equations or text (Shift (⇧)-Control (⌃)-Command (⌘)-4 on macOS by default).

Then, press the Space key to preview the screenshot. Or, press the Return or Enter key to send the OCR request directly.

参考及引用：

[1] 公式免费转 LaTex 代码，截图、转换一气呵成，每月 1000 次全免费<https://cloud.tencent.com/developer/news/486610>
[2] img2latex-mathpix <https://github.com/blaisewang/img2latex-mathpix>
