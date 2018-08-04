# 如何选择适合自己的接入方式

目前吾来开放平台提供同步、异步两种接入方式，分别适用于不同应用场景、前置条件的客户，本节将帮助大家更快速的决策使用哪种方式对接开放平台。

## 什么是同步和异步？

同步\(Synchronous\)、异步\(Asynchronous\)源自于计算机术语，分别指：

* 同步：调用方向接口发送请求后，接口处理完所有流程后才返回结果  
* 异步：调用方向接口发送请求后，接口立即返回，调用方没有马上获得结果；接口处理完请求后，通过回调的方式将结果发送给调用方  

举个实际生活中的例子：老张爱喝茶，烧水

* 老张把水壶放到火上，立等水开后沏茶 --&gt; 同步  
* 老张把水壶放到火上，让老婆等水开后给自己沏茶 --&gt; 异步  

本例中出现几个词：

* 名词：老张、水壶、老婆  
* 动词：放到火上、沏茶  
* 事件：水开  

对应到吾来开放平台，分别代表：

* 名词：接入方后端、用户query、[消息投递接口](http://openapi.wul.ai/1.3.0/docs#operation/CallbackMessage)
* 动词：将用户query发送给吾来、生成回复内容  
* 事件：获取到机器人候选回复列表（列表中包含一些冗余信息，如置信度较低的相似问题）

即：

* 接入方后端将用户query作为参数调用[获取机器人回复接口](http://openapi.wul.ai/1.3.0/docs#operation/GetBotResponse)，接口返回机器人回复列表，接入方后端选择其中一条或多条发送给用户 --&gt; 同步  
* 接入方后端将用户query作为参数调用[接收用户消息接口](http://openapi.wul.ai/1.3.0/docs#operation/ReceiveMessage)，吾来接收到消息后，经过一系列处理，选择出置信度较高的一条或多条机器人回复，发送到接入方后端提供的[消息投递接口](http://openapi.wul.ai/1.3.0/docs#operation/CallbackMessage)，接入方后端将消息回复给用户 --&gt; 异步  

## 选择接入方式Checklist

同步、异步接入吾来开放平台，虽然接入方式有所差异，最终效果基本一致。但在个别应用场景和前置条件下，接入方式的选择有一定倾向性。下面总结了一些应用场景，帮助大家判断，应该使用哪种方式接入。

### 我正在使用saas还是使用私有部署的机器人平台？

![](http://pcufcif6r.bkt.clouddn.com/15332719258405.jpg)

### 我是否有支持异步投递的客户端？

![](http://pcufcif6r.bkt.clouddn.com/15333928606429.jpg)

### 我是否需要使用吾来工作台人工服务用户？

![](http://pcufcif6r.bkt.clouddn.com/15333928730032.jpg)

### 我是否需要自定义发送策略

![](http://pcufcif6r.bkt.clouddn.com/15333928867715.jpg)

### 我希望可以使用满意度评价功能，在吾来后台看到用户对答案的点赞或点踩

![](http://pcufcif6r.bkt.clouddn.com/15333800260441.jpg)

## 具体接入流程

### 同步方式

![](https://laiye-im-saas.oss-cn-beijing.aliyuncs.com/mweb/15329676556009.png)

### 异步方式

![](https://laiye-im-saas.oss-cn-beijing.aliyuncs.com/mweb/15329676754301.png)

