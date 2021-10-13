---
layout:     postno
title:    Google Voice 如何保号
date:       2021-10-13
author:     BY Lete乐特
hidden: true
header-img: img/post/hui.jpg
catalog: true
tags:
    - Google Voice
    - 转载
---
> 转载自 [Lete乐特-Google Voice 如何保号](https://blog.imlete.cn/article/Google-Voice-Protect.html)

Google Voice 如何保号 ？此篇文章不进行注册环节
国人注册的话还是免了吧，除非你已经有了一个美国号码，并且有一个美国ip才能注册
如果你是想用textnow进行验证的话，目前textnow已经不能接收到Google Voice的验证码了
我建议使用万能的淘宝10几块钱就能买到(我自己就是淘宝买的号)

买到之后
修改密码
修改辅助邮箱(你觉得还不够就绑定一个电话号码)
删除之前登陆过的设备
最后转号(当然在已得到号后就转号也可以，不转号也行)

关于如何转号我也不多bb了，话题已经扯很远了

## 正文

1.关于谷歌回收
谷歌政策目前是6个月不用（收短信不算用，必须是发短信或则打电话才算用）谷歌语音Google voice会被回收，政策有变动，所以这个要以谷歌政策官方通知为准，一般回收前一个月内每周都会有邮件通知，所以应多注意谷歌邮箱邮件

2.关于如何发短信和打电话这个不用教吧

如果你有空的话可以手动随便输入一个美国号电话号码发一条或几条短信就可以了
(或者到接码平台复制一个美国号码发几条短信，然后自己再去核对就也是可以的)
关于扣费问题因该是给美国或者加拿大手机号发短信和打电话是免费的
拨打/发送其他地区号码就会收费，咱们用Google Voice又不是为了打电话，只是为了注册国外网站或者产品用的，因为大陆手机号注册国外网站多多少少肯定是有一点限制的

像我这样的(程序员)肯定是要用全自动的啦~~

## 发送订阅短信

发送短信内容:JOIN到22122这个电话号码，这个号码会每月发送两条短信给你，但只是收短信，可能会保不了号
![GV1](/img/in-post/Google-Voice-Protect/GV1.png)

## 回复订阅短信
1. 打开GoogleVoice的设置，把将短信转发到电子邮件地址打开
![GV2](/img/in-post/Google-Voice-Protect/GV2.png)
2. 打开谷歌邮箱https://mail.google.com/
点击搜索栏右边的下拉图标，展开，创建过滤规则
![GV3](/img/in-post/Google-Voice-Protect/GV3.png)
![GV4](/img/in-post/Google-Voice-Protect/GV4.png)
3. 打开谷歌appsScript：https://script.google.com/home
选择左上角的新建项目，输入如下代码，修改自己的信息后保存
```js
function AutoReply() {
var labelObj = GmailApp.getUserLabelByName('AutoReply'); //这里面的AutoReply填过滤条件规则的标签
var gmailThreads;
var messages;
var sender;
//获取我们上面指定归档里面的未读邮件，然后读取，回复，删除
for (var gg = 0; gg < labelObj.getUnreadCount(); gg++) {
    gmailThreads = labelObj.getThreads()[gg];
    messages = gmailThreads.getMessages();
    for (var ii = 0; ii < messages.length; ii++) {
        if (messages[ii].isUnread()) {
            sender = messages[ii].getFrom();
            MailApp.sendEmail(sender, 'Auto Reply', "你好，您的来信已收到，主人将会尽快回复您。———来自机器人回复。");//回复邮件
            messages[ii].markRead(); //标记为已读
            messages[ii].moveToTrash();//删除邮件
        }
    }
 }
}
```
4. 点击左侧的触发器，然后右下角添加触发器，按如下图设置就可以了
![GV5](/img/in-post/Google-Voice-Protect/GV5.png)

到此处即已经完成了，接下来我们到GoogleVoice向22122发一条信息测试一下
可以看出我发送了test1和test2触发了两次(只得到了一条回复，延迟的原有稍后就会再收到一条，我这只截到了一条)
此处的test1和test2只是测试，前面已经发送JONI订阅了
每月会自动发送两条短信到号上，触发器就会自动回复，达到保号的目的
![GV6](/img/in-post/Google-Voice-Protect/GV6.png)
