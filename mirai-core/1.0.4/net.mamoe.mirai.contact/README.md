[mirai-core](../index.md) / [net.mamoe.mirai.contact](./index.md)

## Package net.mamoe.mirai.contact

### Types

| Name | Summary |
|---|---|
| [Contact](-contact/index.md) | 联系对象, 即可以与 [Bot](../net.mamoe.mirai/-bot/index.md) 互动的对象. 包含 [用户](-user/index.md), 和 [群](-group/index.md).`abstract class Contact : `[`ContactOrBot`](-contact-or-bot/index.md)`, CoroutineScope, ContactJavaFriendlyAPI` |
| [ContactList](-contact-list/index.md) | 只读联系人列表, 无锁链表实现`class ContactList<C : `[`Contact`](-contact/index.md)`> : `[`Collection`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-collection/index.html)`<C>` |
| [ContactOrBot](-contact-or-bot/index.md) | 拥有 [id](-contact-or-bot/id.md) 的对象. 此为 [Contact](-contact/index.md) 与 [Bot](../net.mamoe.mirai/-bot/index.md) 的唯一公共接口.`interface ContactOrBot : CoroutineScope` |
| [Friend](-friend/index.md) | 代表一位好友.`abstract class Friend : `[`User`](-user/index.md)`, CoroutineScope` |
| [Group](-group/index.md) | 群.`abstract class Group : `[`Contact`](-contact/index.md)`, CoroutineScope` |
| [GroupSettings](-group-settings/index.md) | 群设置`interface GroupSettings` |
| [Member](-member/index.md) | 代表一位群成员.`abstract class Member : MemberJavaFriendlyAPI, `[`User`](-user/index.md) |
| [MemberPermission](-member-permission/index.md) | 群成员的权限.`enum class MemberPermission : `[`Comparable`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-comparable/index.html)`<`[`MemberPermission`](-member-permission/index.md)`>` |
| [User](-user/index.md) | 代表一个 **用户**.`abstract class User : `[`Contact`](-contact/index.md)`, CoroutineScope` |

### Exceptions

| Name | Summary |
|---|---|
| [BotIsBeingMutedException](-bot-is-being-muted-exception/index.md) | 发送消息时 bot 正处于被禁言状态时抛出的异常.`class BotIsBeingMutedException : `[`RuntimeException`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-runtime-exception/index.html) |
| [MessageTooLargeException](-message-too-large-exception/index.md) | 发送消息时消息过长抛出的异常.`class MessageTooLargeException : `[`RuntimeException`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-runtime-exception/index.html) |
| [PermissionDeniedException](-permission-denied-exception/index.md) | 权限不足`class PermissionDeniedException : `[`IllegalStateException`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-illegal-state-exception/index.html) |

### Properties

| Name | Summary |
|---|---|
| [botMuteRemaining](bot-mute-remaining.md) | `val `[`BotIsBeingMutedException`](-bot-is-being-muted-exception/index.md)`.botMuteRemaining: `[`Int`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-int/index.html) |
| [idContentString](id-content-string.md) | ID 列表的字符串表示. 如:`val `[`ContactList`](-contact-list/index.md)`<*>.idContentString: `[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html) |
| [isBotMuted](is-bot-muted.md) | 返回机器人是否正在被禁言`val `[`Group`](-group/index.md)`.isBotMuted: `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html) |
| [isFriend](is-friend.md) | 判断此成员是否为好友`val `[`Member`](-member/index.md)`.isFriend: `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html) |
| [isMuted](is-muted.md) | 判断群成员是否处于禁言状态.`val `[`Member`](-member/index.md)`.isMuted: `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html) |
| [nameCardOrNick](name-card-or-nick.md) | 获取非空群名片或昵称.`val `[`Member`](-member/index.md)`.nameCardOrNick: `[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html)<br>`val `[`User`](-user/index.md)`.nameCardOrNick: `[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html) |

### Functions

| Name | Summary |
|---|---|
| [asFriend](as-friend.md) | 得到此成员作为好友的对象.`fun `[`Member`](-member/index.md)`.asFriend(): `[`Friend`](-friend/index.md) |
| [asFriendOrNull](as-friend-or-null.md) | 得到此成员作为好友的对象, 当此成员不是好友时返回 `null``fun `[`Member`](-member/index.md)`.asFriendOrNull(): `[`Friend`](-friend/index.md)`?` |
| [checkBotPermission](check-bot-permission.md) | 要求 [Bot](../net.mamoe.mirai/-bot/index.md) 在这个群里的权限至少为 [required](check-bot-permission.md#net.mamoe.mirai.contact$checkBotPermission(net.mamoe.mirai.contact.Group, net.mamoe.mirai.contact.MemberPermission, kotlin.Function0((kotlin.String)))/required), 否则抛出异常 [PermissionDeniedException](-permission-denied-exception/index.md)`fun `[`Group`](-group/index.md)`.checkBotPermission(required: `[`MemberPermission`](-member-permission/index.md)`, lazyMessage: () -> `[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html)` = {
        "Permission denied: required $required, got actual $botPermission for $bot in group $id"
    }): `[`Unit`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-unit/index.html) |
| [isAdministrator](is-administrator.md) | 判断权限是否为管理员`fun `[`MemberPermission`](-member-permission/index.md)`.isAdministrator(): `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html)<br>`fun `[`Member`](-member/index.md)`.isAdministrator(): `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html) |
| [isOperator](is-operator.md) | 判断权限是否为管理员或群主`fun `[`MemberPermission`](-member-permission/index.md)`.isOperator(): `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html)<br>`fun `[`Member`](-member/index.md)`.isOperator(): `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html) |
| [isOwner](is-owner.md) | 判断权限是否为群主`fun `[`MemberPermission`](-member-permission/index.md)`.isOwner(): `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html)<br>`fun `[`Member`](-member/index.md)`.isOwner(): `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html) |
| [mute](mute.md) | `suspend fun `[`Member`](-member/index.md)`.mute(duration: `[`Duration`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.time/-duration/index.html)`): `[`Unit`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-unit/index.html)<br>`suspend fun `[`Member`](-member/index.md)`.mute(durationSeconds: `[`Long`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-long/index.html)`): `[`Unit`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-unit/index.html) |
| [recall](recall.md) | `suspend fun `[`Contact`](-contact/index.md)`.recall(source: `[`MessageChain`](../net.mamoe.mirai.message.data/-message-chain/index.md)`): `[`Unit`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-unit/index.html)<br>`suspend fun `[`Contact`](-contact/index.md)`.recall(source: `[`MessageSource`](../net.mamoe.mirai.message.data/-message-source/index.md)`): `[`Unit`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-unit/index.html) |
| [recallIn](recall-in.md) | `fun `[`Contact`](-contact/index.md)`.recallIn(message: `[`MessageChain`](../net.mamoe.mirai.message.data/-message-chain/index.md)`, millis: `[`Long`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-long/index.html)`, coroutineContext: `[`CoroutineContext`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.coroutines/-coroutine-context/index.html)` = EmptyCoroutineContext): Job`<br>`fun `[`Contact`](-contact/index.md)`.recallIn(source: `[`MessageSource`](../net.mamoe.mirai.message.data/-message-source/index.md)`, millis: `[`Long`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-long/index.html)`, coroutineContext: `[`CoroutineContext`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.coroutines/-coroutine-context/index.html)` = EmptyCoroutineContext): Job` |
| [takeIfIsFriend](take-if-is-friend.md) | 如果此成员是好友, 则执行 [block](take-if-is-friend.md#net.mamoe.mirai.contact$takeIfIsFriend(net.mamoe.mirai.contact.Member, kotlin.Function1((net.mamoe.mirai.contact.Friend, net.mamoe.mirai.contact.takeIfIsFriend.R)))/block) 并返回其返回值. 否则返回 `null``fun <R> `[`Member`](-member/index.md)`.takeIfIsFriend(block: (`[`Friend`](-friend/index.md)`) -> R): R?` |
