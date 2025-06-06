**V1 已被归档，重构版的V2正在编写中……**

<p align = "center">
<h1><center>DiskNext Desktop</center></h1>
原名HFR-Cloud Desktop 或 Cloudreve Desktop，一个基于Tkinter的可跨平台的 HFR-Cloud/DiskNext/Cloudreve v3 客户端，兼容Cloudreve V3，并使用 ttkBootstrap 库进行美化
<br><br>

程序更新日志请翻阅UPDATE.md。

## 重要通知
**不要连接Cloudreve官方演示站 https://demo.cloudreve.org ，会出现JSON读取错误(被WAF拦截)，目前正在分析解决方案，有能力的朋友在测试环境中尝试**

**我们已经准备好向sqlite3数据库迁移，请保存好相关数据。同时，为了保证单文件程序正常可用，我们在后期版本中需要占用%appdata%/HeyFun/HFR-Cloud Desktop Community/这个文件夹来保存数据**

## 目前已经实现的功能
- 登录 & 注销
- 登录记录持久化
- 文件夹浏览
- 文件搜索（功能掉了，暂不可用，在修）
- 新建文件 / 文件夹
- 删除文件 / 文件夹
- 文件分类浏览
- 文件预览 / 下载
- 文件传输列表
- WebDAV列表
- 新建WebDAV账户
- iOS版 Cloudreve 扫码
- 本地策略文件上传
- Onedrive存储策略上传

## 目前存在的Bug
- 文件列表选中后，将无法再触发未选择时的右键菜单 解决办法：地址栏回车刷新

## 目前未实现但严重影响体验的功能
- 很多功能只做了UI，并没有实现对应功能（所以是功能补全版）
- 显示比例在100%-125%体验为佳（未适配高分屏）
- 无法登录需要谷歌与腾讯验证码的 HFR-Cloud / Cloudreve
- 账号（不包括密码）与Cookies为明文保存

## 兼容的 HFR-Cloud / Cloudreve 版本
- HFR-Cloud：V0.0.x
- Cloudreve：V3 `推荐：3.8.4 Pro 因为本人基于此版本开发，使用早期版本可能出现问题`

## 程序配置设置
需要在程序根目录新建文件`config.ini`。示例内容如下，真正填写时请去掉分号以及分号后的内容：
```
[account]
url = http://localhost:5212         ;这里填写服务端的地址，若为ip访问，HFR-Cloud默认使用7030端口，Cloudreve默认使用5212端口；填写你需要接入的地址，结尾不需要加“/”
username = admin@yuxiaoqiu.cn       ;(可不填)邮箱，自动登录失败时会自动将此邮箱填入输入框
id = AqbS                           ;(可不填)用户ID
nickname = Cloudreve                ;(可不填)用户名
groupname = Admin                   ;(可不填)头衔（在Cloudreve被称为用户组名称）
allowshare = True                   ;(可不填)是否允许分享
allowremotedownload = True          ;(可不填)是否允许多线程下载
allowarchivedownload = True         ;(可不填)是否允许打包下载
advancedelete = True                ;(可不填)是否允许高级删除
allowwebdavproxy = False            ;(可不填)是否允许webdav代理

[settings]
Server = Hfrcloud                   ;服务器采用的是HFR-Cloud就填写Hfrcloud，否则请填写Cloudreve_V3
theme = light                       ;(可不填)程序主题，可自行填写light或者dark
fonts = 思源黑体                     ;(可不填)程序字体，推荐思源黑体，留空会检测系统是否安装思源黑体，有则使用无则宋体(Windows)或者苹方(macOS)
```

如果是本地调试，则无需新建`config.ini`，程序会请求http://localhost:5212

## 食用方式

安装相关依赖：
> pip install -r requirements.txt

安装思源黑体（可选，推荐）
> https://github.com/adobe-fonts/source-han-sans/releases/download/2.004R/SourceHanSansSC.zip

启动程序：
> python GUI_Launcher.py

## 打包成可执行文件

**重要提示：打包前请务必删除**`Cookies.txt`**，并删除**`config.ini`**中[account]字段，否则您的个人信息将会随之一起被打包！**

打包前请先安装Pyinstaller模块：
>pip install pyinstaller

然后在项目根目录执行：
>pyinstaller build.spec

最终可执行文件将会出现在/dist目录中

## 升级到捐助版
开始着手这个项目时，我学Python并没有多久，现在回过头来看这个项目已经让我看不上了。所以我对这个代码进行了重构，新的程序拥有着更现代化的界面以及更完善的功能更新，它的名字叫做 DiskNext Desktop。

当然，持续为爱发电的项目注定活不长久，我希望能依靠这个产品来补充一下自己不多的生活费，让我更有动力来维护这个项目。

DiskNext Desktop 将在未来可选订阅与买断。
目前仅开放站长购买，预售价为199元一个根域名永久授权，正式版推出后价格翻倍，需要请联系微信 `yuxiaoqiu2333` 购买. 更多版本敬请关注。

## 开源许可 & 杂谈
本来我并不想开源这个项目的（因为之前我的项目开源之后被别人申请著作权以后返回来告我抄袭，加之这个项目也是自己很久做出来的心血），现在想通了，所以采用**GPL v3**进行开源。但是你也可以赞助我，感谢您的投喂！感谢您的star！
