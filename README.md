# 企业微信机器人-随机色图

通过企业微信机器人，定时向企业微信群中推送随机色图。一次会推送三种格式，`News` `Text` `Image` （因为企业微信有屏蔽功能，可能导致一些`News`格式推送的图片没办法打开，所以加上了后面两种。同时，`Text` 可以设置是否@所有人）

<img src="https://raw.githubusercontent.com/zhangyu0310/wechat-setu-bot/main/pic/Snow.jpg" alt="avatar" style="zoom:25%;" />

## 使用方法

```shell
.\setuServer.exe -at-all -dl-dir="./pic" -pic-msg -wechat-url="xxx" -intervals=3600 -r18
```

|      参数       |             说明             |                    备注                    |
| :-------------: | :--------------------------: | :----------------------------------------: |
|    `-at-all`    |   具有该选项会自带@所有人    |                  bool类型                  |
|    `-dl-dir`    |      指定下载图片的路径      |         仅在`-pic-msg`被指定时生效         |
|     `-help`     |             帮助             |                                            |
|  `-intervals`   | 色图推送间隔时间（单位：秒） | 默认60，最小10（别把人家色图服务搞挂了！） |
|   `-pic-msg`    |     是否推送`Image`消息      |     bool类型，有这个参数的具体原因见下     |
|     `-r18`      |           懂得都懂           |                  bool类型                  |
| `-setu-api-url` |         色图API Url          |  默认为`https://api.lolicon.app/setu/v1`   |
|  `-wechat-url`  |    微信机器人Webhook地址     |                    必填                    |



## 关于`-pic-msg`这个参数

企业微信会屏蔽一些网站的`News`消息，为了能在点进链接前看到是否是喜欢的图片，这里做了`Image`消息的推送。

`Image`消息需要先将图片下载到本地（所以需要指定`-dl-dir`图片的下载路径）

由于企业微信要求图片大小不能超过2M，所以对下载好的图片进行了大小调整。群里看到的很有可能不是原图。

## 效果截图

![avatar](https://raw.githubusercontent.com/zhangyu0310/wechat-setu-bot/main/pic/%E6%88%AA%E5%9B%BE.png)

## 感谢

THX [Lolicon API](https://api.lolicon.app/)

愿我们的未来能有光芒照耀！