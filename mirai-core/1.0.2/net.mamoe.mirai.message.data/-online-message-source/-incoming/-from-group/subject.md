[mirai-core](../../../../index.md) / [net.mamoe.mirai.message.data](../../../index.md) / [OnlineMessageSource](../../index.md) / [Incoming](../index.md) / [FromGroup](index.md) / [subject](./subject.md)

# subject

`val subject: `[`Group`](../../../../net.mamoe.mirai.contact/-group/index.md)

消息主体. 群消息时为 [Group](../../../../net.mamoe.mirai.contact/-group/index.md). 好友消息时为 [Friend](../../../../net.mamoe.mirai.contact/-friend/index.md), 临时消息为 [Member](../../../../net.mamoe.mirai.contact/-member/index.md)
不论是机器人接收的消息还是发送的消息, 此属性都指向机器人能进行回复的目标.

