# Gale 全局配置

!!! info "信息"

    以下 YAML 配置展示了 Gale 全局配置 (==config/gale-global.yml==) 的结构及其默认的值

    此配置文件基于最新的 Leaf 1.21.1 分支

    点击配置项后面的箭头按钮以显示其描述

```yaml title="gale-global.yml"
# This is the global configuration file for Gale.
# As you can see, there's a lot to configure. Some options may impact gameplay, so use
# with caution, and make sure you know what each option does before configuring.
# 
# If you need help with the configuration or have any questions related to Gale,
# join us in our Discord, or check the GitHub Wiki pages.
# 
# The world configuration options are inside
# their respective world folder. The files are named gale-world.yml
# 
# Wiki: https://github.com/GaleMC/Gale/wiki
# Discord: https://discord.gg/gwezNT8c24

_version: 1
gameplay-mechanics:
  enable-book-writing: true #(1)!
log-to-console: #(2)!
  chat:
    empty-message-warning: false #(3)!
    expired-message-warning: false #(4)!
    not-secure-marker: true #(5)!
  ignored-advancements: true #(6)!
  invalid-pool-element-error-log-level: info #(7)!
  invalid-statistics: true #(8)!
  legacy-material-initialization: false #(9)!
  null-id-disconnections: true #(10)!
  player-login-locations: true #(11)!
  plugin-library-loader:
    downloads: true #(12)!
    library-loaded: true #(13)!
    start-load-libraries-for-plugin: true #(14)!
  set-block-in-far-chunk: true #(15)!
  unrecognized-recipes: false #(16)!
misc:
  ignore-null-legacy-structure-data: false #(17)!
  keepalive:
    send-multiple: true #(18)!
  last-tick-time-in-tps-command:
    add-oversleep: false #(19)!
    enabled: false #(20)!
  premium-account-slow-login-timeout: -1 #(21)!
  verify-chat-order: true #(22)!
small-optimizations:
  reduced-intervals:
    increase-time-statistics: 20 #(23)!
    update-entity-line-of-sight: 4 #(24)!
  use-xor-shift-random: #(25)!
    auto-replenish-lootable-refill: true #(26)!
    elytra-firework-speed: true #(27)!
    entity-wake-up-duration: true #(28)!
    generate-tree-with-bukkit-api: true #(29)!
    lightning-random-tick: true #(30)!

```

1. 是否允许书本可写入.<br>
  如果设为 `false`, 拥有权限 `gale.writebooks` 的玩家 (默认: op) 仍然可以写入并使用书本.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>
    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td>-</td></tr>
    <tr><td><i>原版行为</i></td><td><code>true</code></td></tr>
    </table>

2. 是否将特定文本和事件记录到控制台和日志中.
3. 当玩家发送一个空的消息数据包时.<br>
  (这无害, 通常是由于玩家的客户端版本过旧)

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>true</code></td></tr>
    </table>

4. 当玩家的消息数据包已失效时.<br>
  (这无害, 通常是由于玩家客户端的聊天有些不同步)

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>true</code></td></tr>
    </table>

5. 是否在未签名的聊天消息前添加 [NOT SECURE] 标记.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

6. 当加载玩家数据时, 发现他们拥有已经不存在的进度内容.
  (这无害, 通常是通常发生在服务器升级 MC 版本后)

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

7. 当服务器在世界数据中遇到 *无效的池元素* 时的错误日志级别.<br>
  <br>
  *无效的池元素* 是生成的结构 (如矿井) 中由于版本更新不完全或损坏的部分.<br>
  <br>
  这些错误通常会出现在更新过许多 Minecraft 版本的旧服务器中.<br>
  <br>
  这些错误通常没有意义: 无法对此采取任何操作.<br>
  <br>
  此配置项的有效值为: `"none"`, `"info"`, `"warn"` 和 `"error"`.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td><code>"none"</code> 🛈</td><td><code>"info"</code></td><td><code>"error"</code></td><td><code>"error"</code></td></tr>
    </table>

    > 🛈 = 默认值为 `"info"`, 以防止任何潜在错误被默认忽略, 但推荐值为 `"none"`, 因为这些错误通常没有实际意义且无法解决.

8. 当加载玩家数据时, 发现他们拥有已经不存在的统计数据.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

9. 当加载一个非常旧的 Bukkit 插件时.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>true</code></td></tr>
    </table>

10. 当玩家在进服时没有发送有效的用户信息.<br>
  (通常表明有黑客试图通过占用服务器性能进行攻击)

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

11. 是否在记录到控制台的玩家进服消息中包含玩家的坐标.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

12. 当插件的库加载器开始下载依赖库文件时.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

13. 当插件库的加载器完成依赖库文件加载时.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

14. 当插件的库加载器开始为插件加载依赖库文件时.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

15. 当玩家尝试与一个 *非常* 远的方块交互时.<br>
  (通常表明有黑客试图获取其他玩家位置信息, 或正在使用黑客端)

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

16. 当加载玩家数据时, 发现他们拥有已经不存在的配方书配方数据.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>true</code></td></tr>
    </table>

17. 如果任何旧版结构数据的 NBT tag 解析器因某些原因返回 null, 是否忽略这些数据.
    * 如果设为 `true`, 当这种情况发生时不会显示警告.
    * 如果设为 `false`, 当这种情况发生时会在控制台中抛出异常.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td><code>true</code> 🛈</td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td>-</td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

    > 🛈 = 默认值为 `false`, 以防止任何潜在错误被默认忽略, 但推荐值为 `true`, 因为这些错误通常没有意义且无法解决

18. 是否发送比原版更频繁的 keepalive 数据包.
    * 如果设为 `true`, 每秒向每个客户端发送一个 keepalive 数据包, 如果他们在 30 秒内响应至少一个数据包, 则不会被踢出.
    * 如果设为 `false`, 每 15 秒向每个客户端发送一个 keepalive 数据包, 如果他们未响应, 则会被踢出.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td>-</td></tr>
    <tr><td><i>原版行为</i></td><td>- (此配置项不会影响游戏机制)</td></tr>
    </table>

19. 是否将上一 tick 的超时部分添加到 `/tps` 命令中.<br>
  仅当上方的 `enabled` 为 `true` 时, 此配置项才会生效.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td>-</td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td>-</td></tr>
    <tr><td><i>Paper 行为</i></td><td>-</td></tr>
    </table>

20. 是否在 `/tps` 命令中显示上一 tick 的耗时.<br>
  上一 tick 的耗时仅代表那一个 tick 的时间, 因此通常不太有用.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td>-</td></tr>
    <tr><td><i>Paper 行为</i></td><td><code>false</code></td></tr>
    </table>

21. 进服时, 允许正版账户成功进入的最大时间.<br>
  (以 tick 为单位)
    * 如果超出此时间, 玩家的连接将被关闭.
    * 如果设为 &leq; `0`, 将默认与原版一致, 目前为 `600` ticks (30 秒).

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td>-</td><td><code>-1</code></td><td><code>-1</code></td><td><code>-1</code></td></tr>
    </table>
    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td>-</td></tr>
    <tr><td><i>原版行为</i></td><td><code>-1</code></td></tr>
    </table>

22. 是否验证聊天消息的顺序.
    * 如果设为 `true`, 并且玩家由于某些原因发送了乱序的聊天数据包, 他们将被踢出.
    * 如果设为 `false`, 将不会进行验证, 玩家也不会被踢出.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>
    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td>-</td></tr>
    <tr><td><i>原版行为</i></td><td><code>true</code></td></tr>
    </table>

23. 与时间相关的统计信息增加的频率 (总游戏时间, 自上次死亡以来的时间等等的时间增长频率).<br>
  (以 tick 为单位)<br>
  修改此值不会改变统计数据自原版以来的增长速度.<br>
  <br>
  例如:
    * 如果设为 `20`, 总游戏时间将每隔 1 秒增加 20 ticks.
    * 如果设为 `100`, 总游戏时间将每隔 5 秒增加 100 ticks.
    * 如果设为 &leq; `0`, 将默认与 Paper 一致.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td><code>100</code></td><td><code>20</code></td><td><code>1</code></td><td><code>1</code></td></tr>
    </table>
    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>100</code></td></tr>
    <tr><td><i>原版行为</i></td><td>较低的值更贴合原版<br>(设为 <code>20</code> 就够了, 设为 <code>1</code> 没必要)</td></tr>
    </table>

24. 更新一个实体是否在另一个实体视线内的频率.<br>
  (以 tick 为单位)<br>
  如果设为 &leq; `0`, 将默认与 Paper 一致.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td><code>4</code></td><td><code>4</code></td><td><code>1</code></td><td><code>1</code></td></tr>
    </table>
    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>10</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>1</code></td></tr>
    </table>

25. 是否使用 [XorShift](https://www.codeproject.com/Articles/9187/A-fast-equivalent-for-System-Random) 随机数生成器代替 Java 默认的随机数生成器.
26. 是否在 Paper 的 `auto-replenish` 功能中使用 XorShift 随机数生成器为战利品补充物品.<br>
  此配置项不会影响普通的 Minecraft 战利品箱.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>Paper 行为</i></td><td>- (玩家注意不到这细微的差别)</td></tr>
    </table>

27. 是否在玩家使用火箭滑翔时, 为加速效果使用 XorShift 随机数生成器.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

28. 是否在实体激活时间的变化中使用 XorShift 随机数生成器.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td>-</td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    </table>

29. 是否在使用 Bukkit API (`World#generateTree`) 生成树时使用 XorShift 随机数生成器.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>Paper 行为</i></td><td><code>false</code></td></tr>
    </table>

30. 是否在闪电击中几率的计算中使用 XorShift 随机数生成器.

    <table>
    <tr><td></td><td><b>默认值</b></td><td></td><td></td></tr>
    <tr><td><b>推荐值&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>原版</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>Paper 行为</i></td><td><code>false</code></td></tr>
    </table>
