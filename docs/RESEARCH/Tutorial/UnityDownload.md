# 如何下载国际版Unity

我们在`全局`的`Clash/Shadowrocket`模式下打开国际[Unity官网](https://unity.com/)

我们点击`Download`

下载和系统匹配的`UnityHub`

1.正常进行安装，如果要更改默认安装路径请记得更改到了哪里。

2.在安装完`UnityHub`后新建一个启动脚本

`Windows`为

```
@echo off
set HTTP_PROXY=http://127.0.0.1:1080
set HTTPS_PROXY=http://127.0.0.1:1080
start "" "C:\Program Files\Unity Hub\Unity Hub.exe"
```
这里的端口换成自己的代理软件里的端口，如果更改了安装地址也需要更改上面的地址。

`Mac`比较特殊，需要在终端运行这个脚本。

`Mac`为
```
echo '#!/bin/bash
export HTTP_PROXY=http://127.0.0.1:1080
export HTTPS_PROXY=http://127.0.0.1:1080
nohup "/Applications/Unity Hub.app/Contents/MacOS/Unity Hub" &>/dev/null &' > launchUnityHub.command
chmod +x launchUnityHub.command
```

## 注意事项

不用脚本启动直接打开，发现可以用手机或微信的登陆，链接的地址为`https://id.unity.cn/`

只要带`cn`则代表失败

用脚本启动可以正常打开。`https://id.unity.com/`
