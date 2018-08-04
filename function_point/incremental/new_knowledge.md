# 知识点审核
首先，先明确：什么样的query会触发知识点审核？

用户在吾来平台上发送一个query，如果命中了一些回复，并且置信度较高，并且知识库里没有保存该条知识点，会进到新知识点审核里。

同步异步方式都可以进入知识点审核，接入方式有所不同。

## 同步方式接入
对于调用[获取机器人回复接口](http://openapi.wul.ai/1.3.0/docs#operation/GetBotResponse)的每一条用户query，吾来都会判断是否需要进入知识点审核。

## 异步方式接入
对于调用[接收用户消息接口](http://openapi.wul.ai/1.3.0/docs#operation/ReceiveMessage)的每一条用户query，吾来都会判断是否需要进入知识点审核。