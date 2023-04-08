---
layout: post
title: Monitor your deep learning program with Feishu notification!
date: 2024-01-26 10:59:00-0400
description: Utilities for monitoring python programs using Feishu API
tags: [skills]
giscus_comments: true
related_posts: false
---




我们做深度学习的，经常需要运行耗时很长的python脚本。如果不能知道程序何时结束，或者程序异常退出的时候不能及时察觉，对于时间和资源都是很大的浪费。

 

为了及时得到提醒，我们可以使用邮件、短信或应用的SMS服务。但是，邮件往往需要单独的SMTP或POP3客户端访问密码，有些老式的邮件服务商可以提供一个密码到处访问的SMTP或POP3服务，但是这些往往在国内访问不了；而短信服务则需要花钱，且有一定的限制：

 
<div class="row" style="width: 50%">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/feishu_monitor/image1.png" class="img-fluid rounded z-depth-1" zoomable=true  %}
    </div>
</div>


考虑易用性、及时性、经济性、跨平台，我们可以采用一种非常适用于个人用户的提醒方式：飞书群聊机器人。

 

效果：

 

<div class="row" style="width: 50%">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/feishu_monitor/image2.png" class="img-fluid rounded z-depth-1" zoomable=true  %}
    </div>
</div>

## 使用方法：

1. 接下来的所有操作，在你的python解释器所在机器上进行。
2. `pip install -U echo_logger` 来下载最新版本的 echo_logger (没错，这个包是我写的)
3. 打开电脑版飞书，新建一个只有你自己的群聊。
4. 用电脑版飞书在群聊里添加自定义机器人

<div class="row" style="width: 50%">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/feishu_monitor/image3.png" class="img-fluid rounded z-depth-1" zoomable=true  %}
    </div>
</div>

<div class="row" style="width: 50%">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/feishu_monitor/image4.png" class="img-fluid rounded z-depth-1" zoomable=true  %}
    </div>
</div>

<div class="row" style="width: 50%">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/feishu_monitor/image5.png" class="img-fluid rounded z-depth-1" zoomable=true  %}
    </div>
</div>

<div class="row" style="width: 50%">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/feishu_monitor/image6.png" class="img-fluid rounded z-depth-1" zoomable=true  %}
    </div>
</div>

<div class="row" style="width: 50%">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/feishu_monitor/image7.png" class="img-fluid rounded z-depth-1" zoomable=true  %}
    </div>
</div>

名称、描述什么的随便。

<div class="row" style="width: 50%">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/feishu_monitor/image8.png" class="img-fluid rounded z-depth-1" zoomable=true  %}
    </div>
</div>

然后复制这个webhook地址。

 

5. 在你的home目录 (Windows示例 `C:/Users/XXX/` , Linux示例  `/home/xxx/` ) 放一个文件。文件名： `.feishu_bot`, 内容为刚刚复制的地址，然后就可以开始使用了。


## 使用样例：

#### 使用封装好的 @monit_feishu() 装饰器

<div class="row" style="width: 50%">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/feishu_monitor/image9.png" class="img-fluid rounded z-depth-1" zoomable=true  %}
    </div>
</div>

默认参数的效果：

 

正常运行：

 
<div class="row" style="width: 50%">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/feishu_monitor/image10.png" class="img-fluid rounded z-depth-1" zoomable=true  %}
    </div>
</div>

报错时发送的信息：


<div class="row" style="width: 50%">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/feishu_monitor/image11.png" class="img-fluid rounded z-depth-1" zoomable=true  %}
    </div>
</div>

 

#### 直接发送任意飞书信息：

<div class="row" style="width: 50%">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/feishu_monitor/image12.png" class="img-fluid rounded z-depth-1" zoomable=true  %}
    </div>
</div>

<div class="row" style="width: 50%">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/feishu_monitor/image13.png" class="img-fluid rounded z-depth-1" zoomable=true  %}
    </div>
</div>

 

欢迎使用、提出issue。

 

GitHub： [echo_logger](https://github.com/void-echo/echo_logger) 

Mail: [void@mail.sdu.edu.cn](mailto:void@mail.sdu.edu.cn) 