[mirai-core](../../index.md) / [net.mamoe.mirai.message.data](../index.md) / [MessageMetadata](./index.md)

# MessageMetadata

`interface MessageMetadata : `[`SingleMessage`](../-single-message.md)

消息元数据, 即不含内容的元素.

这种类型的 [Message](../-message/index.md) 只表示一条消息的属性. 其子类为 [MessageSource](../-message-source/index.md), [QuoteReply](../-quote-reply/index.md)

所有子类的 [contentToString](content-to-string.md) 都应该返回空字符串.

**See Also**

[MessageSource](../-message-source/index.md)

[QuoteReply](../-quote-reply/index.md)

[CustomMessageMetadata](../-custom-message-metadata/index.md)

[ConstrainSingle](../-constrain-single/index.md)

### Functions

| Name | Summary |
|---|---|
| [contentToString](content-to-string.md) | 返回空字符串`open fun contentToString(): `[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html) |

### Extension Properties

| Name | Summary |
|---|---|
| [content](../content.md) | [Message.contentToString](../-message/content-to-string.md) 的捷径`val `[`Message`](../-message/index.md)`.content: `[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html) |

### Extension Functions

| Name | Summary |
|---|---|
| [flatten](../flatten.md) | 扁平化 [Message](../-message/index.md)`fun `[`Message`](../-message/index.md)`.flatten(): `[`Sequence`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.sequences/-sequence/index.html)`<`[`SingleMessage`](../-single-message.md)`>` |
| [isContentEmpty](../is-content-empty.md) | 判断消息内容是否为空.`fun `[`Message`](../-message/index.md)`.isContentEmpty(): `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html) |
| [isContentNotEmpty](../is-content-not-empty.md) | `fun `[`Message`](../-message/index.md)`.isContentNotEmpty(): `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html) |
| [isNotPlain](../is-not-plain.md) | `fun `[`Message`](../-message/index.md)`.isNotPlain(): `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html) |
| [isPlain](../is-plain.md) | `fun `[`Message`](../-message/index.md)`.isPlain(): `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html) |
| [plus](../plus.md) | `suspend operator fun `[`Message`](../-message/index.md)`.plus(another: Flow<`[`Message`](../-message/index.md)`>): `[`MessageChain`](../-message-chain/index.md) |
| [repeat](../repeat.md) | 将此消息元素按顺序重复 [count](../repeat.md#net.mamoe.mirai.message.data$repeat(net.mamoe.mirai.message.data.Message, kotlin.Int)/count) 次.`fun `[`Message`](../-message/index.md)`.repeat(count: `[`Int`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-int/index.html)`): `[`MessageChain`](../-message-chain/index.md) |
| [sendTo](../send-to.md) | `suspend fun <C : `[`Contact`](../../net.mamoe.mirai.contact/-contact/index.md)`> `[`Message`](../-message/index.md)`.sendTo(contact: C): `[`MessageReceipt`](../../net.mamoe.mirai.message/-message-receipt/index.md)`<C>` |
| [times](../times.md) | 将此消息元素按顺序重复 [count](../times.md#net.mamoe.mirai.message.data$times(net.mamoe.mirai.message.data.Message, kotlin.Int)/count) 次.`operator fun `[`Message`](../-message/index.md)`.times(count: `[`Int`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-int/index.html)`): `[`MessageChain`](../-message-chain/index.md) |
| [toForwardMessage](../to-forward-message.md) | 转换为 [ForwardMessage](../-forward-message/index.md)`fun `[`Message`](../-message/index.md)`.toForwardMessage(sender: `[`User`](../../net.mamoe.mirai.contact/-user/index.md)`, time: `[`Int`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-int/index.html)` = currentTimeSeconds.toInt(), displayStrategy: DisplayStrategy = DisplayStrategy): `[`ForwardMessage`](../-forward-message/index.md)<br>`fun `[`Message`](../-message/index.md)`.toForwardMessage(senderId: `[`Long`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-long/index.html)`, senderName: `[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html)`, time: `[`Int`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-int/index.html)` = currentTimeSeconds.toInt(), displayStrategy: DisplayStrategy = DisplayStrategy): `[`ForwardMessage`](../-forward-message/index.md) |

### Inheritors

| Name | Summary |
|---|---|
| [ConstrainSingle](../-constrain-single/index.md) | 约束一个 [MessageChain](../-message-chain/index.md) 中只存在这一种类型的元素. 新元素将会替换旧元素, 保持原顺序.`interface ConstrainSingle<out M : `[`Message`](../-message/index.md)`> : `[`MessageMetadata`](./index.md) |
| [CustomMessageMetadata](../-custom-message-metadata/index.md) | 自定义消息元数据.`abstract class CustomMessageMetadata : `[`CustomMessage`](../-custom-message/index.md)`, `[`MessageMetadata`](./index.md) |
| [MessageSource](../-message-source/index.md) | 消息源, 它存在于 [MessageChain](../-message-chain/index.md) 中, 用于表示这个消息的来源.`sealed class MessageSource : `[`Message`](../-message/index.md)`, `[`MessageMetadata`](./index.md)`, `[`ConstrainSingle`](../-constrain-single/index.md)`<`[`MessageSource`](../-message-source/index.md)`>` |
| [QuoteReply](../-quote-reply/index.md) | 引用回复.`class QuoteReply : `[`Message`](../-message/index.md)`, `[`MessageMetadata`](./index.md)`, `[`ConstrainSingle`](../-constrain-single/index.md)`<`[`QuoteReply`](../-quote-reply/index.md)`>` |
