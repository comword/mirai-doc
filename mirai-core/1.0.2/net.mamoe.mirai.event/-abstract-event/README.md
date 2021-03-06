[mirai-core](../../index.md) / [net.mamoe.mirai.event](../index.md) / [AbstractEvent](./index.md)

# AbstractEvent

`abstract class AbstractEvent : `[`Event`](../-event/index.md)

所有实现了 [Event](../-event/index.md) 接口的类都应该继承的父类.

在使用事件时应使用类型 [Event](../-event/index.md). 在实现自定义事件时应继承 [AbstractEvent](./index.md).

### Constructors

| Name | Summary |
|---|---|
| [&lt;init&gt;](-init-.md) | 所有实现了 [Event](../-event/index.md) 接口的类都应该继承的父类.`AbstractEvent()` |

### Properties

| Name | Summary |
|---|---|
| [isCancelled](is-cancelled.md) | `val isCancelled: `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html) |
| [isIntercepted](is-intercepted.md) | `open val isIntercepted: `[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html) |

### Functions

| Name | Summary |
|---|---|
| [cancel](cancel.md) | `fun cancel(): `[`Unit`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-unit/index.html) |
| [intercept](intercept.md) | `open fun intercept(): `[`Unit`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-unit/index.html) |

### Extension Functions

| Name | Summary |
|---|---|
| [__broadcastJava](../__broadcast-java.md) | 在 Java 广播一个事件的唯一途径.`fun <E : `[`Event`](../-event/index.md)`> E.__broadcastJava(): E` |
| [broadcast](../broadcast.md) | 广播一个事件的唯一途径.`suspend fun <E : `[`Event`](../-event/index.md)`> E.broadcast(): E` |

### Inheritors

| Name | Summary |
|---|---|
| [BeforeImageUploadEvent](../../net.mamoe.mirai.event.events/-before-image-upload-event/index.md) | 图片上传前. 可以阻止上传.`data class BeforeImageUploadEvent : `[`BotEvent`](../../net.mamoe.mirai.event.events/-bot-event/index.md)`, `[`BotActiveEvent`](../../net.mamoe.mirai.event.events/-bot-active-event.md)`, `[`AbstractEvent`](./index.md)`, `[`CancellableEvent`](../-cancellable-event/index.md) |
| [BotAvatarChangedEvent](../../net.mamoe.mirai.event.events/-bot-avatar-changed-event/index.md) | [Bot](../../net.mamoe.mirai/-bot/index.md) 头像被修改（通过其他客户端修改了头像）. 在此事件广播前就已经修改完毕.`data class BotAvatarChangedEvent : `[`BotEvent`](../../net.mamoe.mirai.event.events/-bot-event/index.md)`, Packet, `[`AbstractEvent`](./index.md) |
| [BotGroupPermissionChangeEvent](../../net.mamoe.mirai.event.events/-bot-group-permission-change-event/index.md) | Bot 在群里的权限被改变. 操作人一定是群主`data class BotGroupPermissionChangeEvent : `[`BotPassiveEvent`](../../net.mamoe.mirai.event.events/-bot-passive-event.md)`, `[`GroupEvent`](../../net.mamoe.mirai.event.events/-group-event/index.md)`, Packet, `[`AbstractEvent`](./index.md) |
| [BotInvitedJoinGroupRequestEvent](../../net.mamoe.mirai.event.events/-bot-invited-join-group-request-event/index.md) | [Bot](../../net.mamoe.mirai/-bot/index.md) 被邀请加入一个群.`data class BotInvitedJoinGroupRequestEvent : `[`BotEvent`](../../net.mamoe.mirai.event.events/-bot-event/index.md)`, Packet, `[`AbstractEvent`](./index.md) |
| [BotJoinGroupEvent](../../net.mamoe.mirai.event.events/-bot-join-group-event/index.md) | Bot 成功加入了一个新群`sealed class BotJoinGroupEvent : `[`GroupEvent`](../../net.mamoe.mirai.event.events/-group-event/index.md)`, Packet, `[`AbstractEvent`](./index.md) |
| [BotLeaveEvent](../../net.mamoe.mirai.event.events/-bot-leave-event/index.md) | 机器人被踢出群或在其他客户端主动退出一个群. 在事件广播前 [Bot.groups](../../net.mamoe.mirai/-bot/groups.md) 就已删除这个群.`sealed class BotLeaveEvent : `[`BotEvent`](../../net.mamoe.mirai.event.events/-bot-event/index.md)`, Packet, `[`AbstractEvent`](./index.md) |
| [BotMuteEvent](../../net.mamoe.mirai.event.events/-bot-mute-event/index.md) | Bot 被禁言`data class BotMuteEvent : `[`GroupEvent`](../../net.mamoe.mirai.event.events/-group-event/index.md)`, Packet, `[`BotPassiveEvent`](../../net.mamoe.mirai.event.events/-bot-passive-event.md)`, `[`AbstractEvent`](./index.md) |
| [BotOfflineEvent](../../net.mamoe.mirai.event.events/-bot-offline-event/index.md) | [Bot](../../net.mamoe.mirai/-bot/index.md) 离线.`sealed class BotOfflineEvent : `[`BotEvent`](../../net.mamoe.mirai.event.events/-bot-event/index.md)`, `[`AbstractEvent`](./index.md) |
| [BotOnlineEvent](../../net.mamoe.mirai.event.events/-bot-online-event/index.md) | [Bot](../../net.mamoe.mirai/-bot/index.md) 登录完成, 好友列表, 群组列表初始化完成`data class BotOnlineEvent : `[`BotActiveEvent`](../../net.mamoe.mirai.event.events/-bot-active-event.md)`, `[`AbstractEvent`](./index.md) |
| [BotReloginEvent](../../net.mamoe.mirai.event.events/-bot-relogin-event/index.md) | [Bot](../../net.mamoe.mirai/-bot/index.md) 主动或被动重新登录. 在此事件广播前就已经登录完毕.`data class BotReloginEvent : `[`BotEvent`](../../net.mamoe.mirai.event.events/-bot-event/index.md)`, `[`BotActiveEvent`](../../net.mamoe.mirai.event.events/-bot-active-event.md)`, `[`AbstractEvent`](./index.md) |
| [BotUnmuteEvent](../../net.mamoe.mirai.event.events/-bot-unmute-event/index.md) | Bot 被取消禁言`data class BotUnmuteEvent : `[`GroupEvent`](../../net.mamoe.mirai.event.events/-group-event/index.md)`, Packet, `[`BotPassiveEvent`](../../net.mamoe.mirai.event.events/-bot-passive-event.md)`, `[`AbstractEvent`](./index.md) |
| [FriendAddEvent](../../net.mamoe.mirai.event.events/-friend-add-event/index.md) | 成功添加了一个新好友的事件`data class FriendAddEvent : `[`FriendEvent`](../../net.mamoe.mirai.event.events/-friend-event/index.md)`, Packet, `[`AbstractEvent`](./index.md) |
| [FriendAvatarChangedEvent](../../net.mamoe.mirai.event.events/-friend-avatar-changed-event/index.md) | [Friend](../../net.mamoe.mirai.contact/-friend/index.md) 头像被修改. 在此事件广播前就已经修改完毕.`data class FriendAvatarChangedEvent : `[`FriendEvent`](../../net.mamoe.mirai.event.events/-friend-event/index.md)`, Packet, `[`AbstractEvent`](./index.md) |
| [FriendDeleteEvent](../../net.mamoe.mirai.event.events/-friend-delete-event/index.md) | 好友已被删除的事件.`data class FriendDeleteEvent : `[`FriendEvent`](../../net.mamoe.mirai.event.events/-friend-event/index.md)`, Packet, `[`AbstractEvent`](./index.md) |
| [FriendRemarkChangeEvent](../../net.mamoe.mirai.event.events/-friend-remark-change-event/index.md) | 好友昵称改变事件. 目前仅支持解析 (来自 PC 端的修改).`data class FriendRemarkChangeEvent : `[`FriendEvent`](../../net.mamoe.mirai.event.events/-friend-event/index.md)`, Packet, `[`AbstractEvent`](./index.md) |
| [GroupAllowAnonymousChatEvent](../../net.mamoe.mirai.event.events/-group-allow-anonymous-chat-event/index.md) | 群 "匿名聊天" 功能状态改变. 此事件广播前修改就已经完成.`data class GroupAllowAnonymousChatEvent : `[`GroupSettingChangeEvent`](../../net.mamoe.mirai.event.events/-group-setting-change-event/index.md)`<`[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html)`>, Packet, `[`GroupOperableEvent`](../../net.mamoe.mirai.event.events/-group-operable-event/index.md)`, `[`AbstractEvent`](./index.md) |
| [GroupAllowConfessTalkEvent](../../net.mamoe.mirai.event.events/-group-allow-confess-talk-event/index.md) | 群 "坦白说" 功能状态改变. 此事件广播前修改就已经完成.`data class GroupAllowConfessTalkEvent : `[`GroupSettingChangeEvent`](../../net.mamoe.mirai.event.events/-group-setting-change-event/index.md)`<`[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html)`>, Packet, `[`AbstractEvent`](./index.md) |
| [GroupAllowMemberInviteEvent](../../net.mamoe.mirai.event.events/-group-allow-member-invite-event/index.md) | 群 "允许群员邀请好友加群" 功能状态改变. 此事件广播前修改就已经完成.`data class GroupAllowMemberInviteEvent : `[`GroupSettingChangeEvent`](../../net.mamoe.mirai.event.events/-group-setting-change-event/index.md)`<`[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html)`>, Packet, `[`GroupOperableEvent`](../../net.mamoe.mirai.event.events/-group-operable-event/index.md)`, `[`AbstractEvent`](./index.md) |
| [GroupEntranceAnnouncementChangeEvent](../../net.mamoe.mirai.event.events/-group-entrance-announcement-change-event/index.md) | 入群公告改变. 此事件广播前修改就已经完成.`data class GroupEntranceAnnouncementChangeEvent : `[`GroupSettingChangeEvent`](../../net.mamoe.mirai.event.events/-group-setting-change-event/index.md)`<`[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html)`>, Packet, `[`GroupOperableEvent`](../../net.mamoe.mirai.event.events/-group-operable-event/index.md)`, `[`AbstractEvent`](./index.md) |
| [GroupMuteAllEvent](../../net.mamoe.mirai.event.events/-group-mute-all-event/index.md) | 群 "全员禁言" 功能状态改变. 此事件广播前修改就已经完成.`data class GroupMuteAllEvent : `[`GroupSettingChangeEvent`](../../net.mamoe.mirai.event.events/-group-setting-change-event/index.md)`<`[`Boolean`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-boolean/index.html)`>, Packet, `[`GroupOperableEvent`](../../net.mamoe.mirai.event.events/-group-operable-event/index.md)`, `[`AbstractEvent`](./index.md) |
| [GroupNameChangeEvent](../../net.mamoe.mirai.event.events/-group-name-change-event/index.md) | 群名改变. 此事件广播前修改就已经完成.`data class GroupNameChangeEvent : `[`GroupSettingChangeEvent`](../../net.mamoe.mirai.event.events/-group-setting-change-event/index.md)`<`[`String`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/index.html)`>, Packet, `[`GroupOperableEvent`](../../net.mamoe.mirai.event.events/-group-operable-event/index.md)`, `[`AbstractEvent`](./index.md) |
| [ImageUploadEvent](../../net.mamoe.mirai.event.events/-image-upload-event/index.md) | 图片上传完成.`sealed class ImageUploadEvent : `[`BotEvent`](../../net.mamoe.mirai.event.events/-bot-event/index.md)`, `[`BotActiveEvent`](../../net.mamoe.mirai.event.events/-bot-active-event.md)`, `[`AbstractEvent`](./index.md) |
| [MemberCardChangeEvent](../../net.mamoe.mirai.event.events/-member-card-change-event/index.md) | 成员群名片改动. 此事件广播前修改就已经完成.`data class MemberCardChangeEvent : `[`GroupMemberEvent`](../../net.mamoe.mirai.event.events/-group-member-event/index.md)`, Packet, `[`AbstractEvent`](./index.md) |
| [MemberJoinEvent](../../net.mamoe.mirai.event.events/-member-join-event/index.md) | 成员已经加入群的事件`sealed class MemberJoinEvent : `[`GroupMemberEvent`](../../net.mamoe.mirai.event.events/-group-member-event/index.md)`, `[`BotPassiveEvent`](../../net.mamoe.mirai.event.events/-bot-passive-event.md)`, Packet, `[`AbstractEvent`](./index.md) |
| [MemberJoinRequestEvent](../../net.mamoe.mirai.event.events/-member-join-request-event/index.md) | 一个账号请求加入群事件, [Bot](../../net.mamoe.mirai/-bot/index.md) 在此群中是管理员或群主.`data class MemberJoinRequestEvent : `[`BotEvent`](../../net.mamoe.mirai.event.events/-bot-event/index.md)`, Packet, `[`AbstractEvent`](./index.md) |
| [MemberLeaveEvent](../../net.mamoe.mirai.event.events/-member-leave-event/index.md) | 成员已经离开群的事件. 在事件广播前成员就已经从 [Group.members](../../net.mamoe.mirai.contact/-group/members.md) 中删除`sealed class MemberLeaveEvent : `[`GroupMemberEvent`](../../net.mamoe.mirai.event.events/-group-member-event/index.md)`, `[`AbstractEvent`](./index.md) |
| [MemberMuteEvent](../../net.mamoe.mirai.event.events/-member-mute-event/index.md) | 群成员被禁言事件. 被禁言的成员都不可能是机器人本人`data class MemberMuteEvent : `[`GroupMemberEvent`](../../net.mamoe.mirai.event.events/-group-member-event/index.md)`, Packet, `[`GroupOperableEvent`](../../net.mamoe.mirai.event.events/-group-operable-event/index.md)`, `[`AbstractEvent`](./index.md) |
| [MemberPermissionChangeEvent](../../net.mamoe.mirai.event.events/-member-permission-change-event/index.md) | 成员权限改变的事件. 成员不可能是机器人自己.`data class MemberPermissionChangeEvent : `[`GroupMemberEvent`](../../net.mamoe.mirai.event.events/-group-member-event/index.md)`, `[`BotPassiveEvent`](../../net.mamoe.mirai.event.events/-bot-passive-event.md)`, Packet, `[`AbstractEvent`](./index.md) |
| [MemberSpecialTitleChangeEvent](../../net.mamoe.mirai.event.events/-member-special-title-change-event/index.md) | 成员群头衔改动. 一定为群主操作`data class MemberSpecialTitleChangeEvent : `[`GroupMemberEvent`](../../net.mamoe.mirai.event.events/-group-member-event/index.md)`, `[`GroupOperableEvent`](../../net.mamoe.mirai.event.events/-group-operable-event/index.md)`, `[`AbstractEvent`](./index.md) |
| [MemberUnmuteEvent](../../net.mamoe.mirai.event.events/-member-unmute-event/index.md) | 群成员被取消禁言事件. 被禁言的成员都不可能是机器人本人`data class MemberUnmuteEvent : `[`GroupMemberEvent`](../../net.mamoe.mirai.event.events/-group-member-event/index.md)`, Packet, `[`GroupOperableEvent`](../../net.mamoe.mirai.event.events/-group-operable-event/index.md)`, `[`AbstractEvent`](./index.md) |
| [MessageRecallEvent](../../net.mamoe.mirai.event.events/-message-recall-event/index.md) | 消息撤回事件. 可是任意消息被任意人撤回.`sealed class MessageRecallEvent : `[`BotEvent`](../../net.mamoe.mirai.event.events/-bot-event/index.md)`, `[`AbstractEvent`](./index.md) |
| [MessageSendEvent](../../net.mamoe.mirai.event.events/-message-send-event/index.md) | 主动发送消息`sealed class MessageSendEvent : `[`BotEvent`](../../net.mamoe.mirai.event.events/-bot-event/index.md)`, `[`BotActiveEvent`](../../net.mamoe.mirai.event.events/-bot-active-event.md)`, `[`AbstractEvent`](./index.md) |
| [NewFriendRequestEvent](../../net.mamoe.mirai.event.events/-new-friend-request-event/index.md) | 一个账号请求添加机器人为好友的事件`data class NewFriendRequestEvent : `[`BotEvent`](../../net.mamoe.mirai.event.events/-bot-event/index.md)`, Packet, `[`AbstractEvent`](./index.md) |
