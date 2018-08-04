# 满意度评价

接入方可以在客户端提供按钮，让用户点击反馈知识点回复的准确程度。统计结果可在后台展示，后续也可以用在知识点召回的正负反馈中，利用用户标注数据，自动优化问答模型。

![1451533406239_.pi](http://pcufcif6r.bkt.clouddn.com/1451533406239_.pic.jpg)

![-w1293](http://pcufcif6r.bkt.clouddn.com/15334060466031.jpg)

此功能只支持同步方式接入。

## 同步方式接入
接入方通过[获取机器人回复接口](http://openapi.wul.ai/1.3.0/docs#operation/GetBotResponse)，获取到要发送的候选回复的知识点id。

![-w1090](http://pcufcif6r.bkt.clouddn.com/15334066801022.jpg)

然后将知识点id作为参数传入[用户评价机器人回复](http://openapi.wul.ai/1.3.0/docs#operation/EvaluateBotResponseSatisfaction)接口，完成评价。
