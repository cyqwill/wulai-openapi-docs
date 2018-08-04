# 相似问题

相似问题指在机器人回复的消息后增加相似问题列表，以供用户了解更多内容。

![-w269](http://pcufcif6r.bkt.clouddn.com/15333994037118.jpg)

同步和异步方式接入，实现方式有所不同。

## 同步方式接入
[获取机器人回复接口](http://openapi.wul.ai/1.3.0/docs#operation/GetBotResponse)返回的候选回复列表中，is_send=false，即不发送的候选回复，也可以说，置信度较低的候选回复，可以直接当做相似问题展示。

## 异步方式接入
[消息投递接口](http://openapi.wul.ai/1.3.0/docs#operation/CallbackMessage)返回的suggested_response字段即为相似问题。