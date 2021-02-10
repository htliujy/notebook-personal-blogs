# VPN翻墙及配置

这里记录各种工具，Mac的，Windows的，用于上网时快速有效查找资料。
比如[shadowsocks](https://shadowsocks.org/en/download/clients.html)，或者 [ShadowsocksX-NG](https://github.com/shadowsocks/ShadowsocksX-NG/releases/tag/v1.9.4)
一般就三种模式：

- 自动模式（Proxy Automatic Configure Mode, PAC)，一般都选用这个；
- 全局模式（Global Mode），有些网站在自动模式下，会不走VPN通道，而这些网站又似乎被墙给限速了，那就选用全局，让这些特殊网站也走VPN；
- 手动模式（Manual Mode），这个我基本没有用过，不懂；

但是，仍然有些问题需要解决的：

- 在学校网络，很多域名被污染了，比如youtube，github.io，好像只能设置DNS服务器解决；
- 我没有认真分类并理解哪些通道走了VPN，只知道浏览器可以简单用全局模式或自动模式；
- 对于其他特殊通道，基本上都是靠google解决的，比如终端中有些场景需要使用VPN：[简书-Mac终端代理和git代理设置](https://www.jianshu.com/p/205aff65954a)
比如我用git，我经常就用下面这个命令，确保push和pull走的是VPN通道，加快速度（同时，为了加快git clone的速度，我还用参数 <--depth>。

    ```shell
    export ALL_PROXY=socks5://127.0.0.1:1086
    ```

    恢复代码我也用的是这个，自己摸索的：

    ```shell
    export ALL_PROXY=
    ```

- 比如google的文件同步工具‘backup and sync from google’，也是需要使用特殊的方法，让其走VPN通道，才可以正常同步（今日20201006，因为几年没使用这个软件，已经忘了怎么配置了，后面的都是我刚刚去百度，且未验证的）。
配置方法如：[Google Drive登录时遇到问题，怎么解决？](https://www.zhihu.com/question/62318694)

## Liber网站上的配置

网址：<www.liber.plus>

订阅信息链接：<https://liber.plus/modules/servers/V2RaySocks/subscribe/surge.php?sid=4611&token=12345461>
