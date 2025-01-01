# Leaf 全局配置

!!! info "信息"

    以下 YAML 配置展示了 Leaf 全局配置 (==config/leaf-global.yml==) 的结构及其默认的值

    此配置文件基于最新的 Leaf 1.21.1 分支

    点击配置项后面的箭头按钮以显示其描述

```yaml title="leaf-global.yml"
# Leaf Global Config
config-version: 3.0

###########
#  ASYNC  #
###########
async: #(1)!
  async-entity-tracker: #(2)!
    enabled: false
    compat-mode: false #(3)!
    max-threads: 0 #(4)!
    keepalive: 60 #(5)!
  # **Experimental feature, may cause data lost in some circumstances!**
  async-playerdata-save: #(6)!
    enabled: false
  async-pathfinding: #(7)!
    enabled: false
    max-threads: 0 #(8)!
    keepalive: 60 #(9)!
  async-mob-spawning: #(10)!
    enabled: true
  async-locator: #(11)!
    enabled: false
    threads: 0 #(12)!
    keepalive: 60 #(13)!

##########
#  PERF  #
##########
performance: #(14)!
  use-virtual-thread-for-async-chat-executor: true #(15)!
  use-virtual-thread-for-async-scheduler: true #(16)!
  create-snapshot-on-retrieving-blockstate: true #(17)!
  inactive-goal-selector-throttle: true #(18)!
  throttle-hopper-when-full: #(19)!
    enabled: false
    skip-ticks: 0 #(20)!
  skip-map-item-data-updates-if-map-does-not-have-craftmaprenderer: true #(21)!
  skip-ai-for-non-aware-mob: true #(22)!
  reduce-packets: #(23)!
    reduce-entity-move-packets: false #(24)!
  optimized-powered-rails: true #(25)!
  optimize-minecart: #(26)!
    enabled: false
    skip-tick-count: 30 #(27)!
  # This may cause the inconsistent order of future compose tasks.
  faster-structure-gen-future-sequencing: true #(28)!
  # Requires a JVM that supports RandomGenerator and the LXM generators.
  # Some JREs don't support this and will cause a crash.
  faster-random-generator: #(29)!
    enabled: false
    random-generator: Xoroshiro128PlusPlus #(30)!
    enable-for-worldgen: false #(31)!
    warn-for-slime-chunk: true #(32)!
    use-legacy-random-for-slime-chunk: false #(33)!
  entity-timeouts: #(34)!
    ALLAY: -1
    AREA_EFFECT_CLOUD: -1
    ARMADILLO: -1
    ARMOR_STAND: -1
    ARROW: -1
    AXOLOTL: -1
    BAT: -1
    BEE: -1
    BLAZE: -1
    BOAT: -1
    BOGGED: -1
    BREEZE: -1
    BREEZE_WIND_CHARGE: -1
    CAMEL: -1
    CAT: -1
    CAVE_SPIDER: -1
    CHEST_BOAT: -1
    CHEST_MINECART: -1
    CHICKEN: -1
    COD: -1
    COMMAND_BLOCK_MINECART: -1
    COW: -1
    CREEPER: -1
    DOLPHIN: -1
    DONKEY: -1
    DRAGON_FIREBALL: -1
    DROWNED: -1
    EGG: -1
    ELDER_GUARDIAN: -1
    ENDER_DRAGON: -1
    ENDER_PEARL: -1
    ENDERMAN: -1
    ENDERMITE: -1
    EVOKER: -1
    EVOKER_FANGS: -1
    EXPERIENCE_BOTTLE: -1
    EXPERIENCE_ORB: -1
    EYE_OF_ENDER: -1
    FIREWORK_ROCKET: -1
    FOX: -1
    FROG: -1
    FURNACE_MINECART: -1
    GHAST: -1
    GIANT: -1
    GLOW_SQUID: -1
    GOAT: -1
    GUARDIAN: -1
    HOGLIN: -1
    HOPPER_MINECART: -1
    HORSE: -1
    HUSK: -1
    ILLUSIONER: -1
    IRON_GOLEM: -1
    ITEM: -1
    OMINOUS_ITEM_SPAWNER: -1
    FIREBALL: -1
    LIGHTNING_BOLT: -1
    LLAMA: -1
    LLAMA_SPIT: -1
    MAGMA_CUBE: -1
    MOOSHROOM: -1
    MULE: -1
    OCELOT: -1
    PANDA: -1
    PARROT: -1
    PHANTOM: -1
    PIG: -1
    PIGLIN: -1
    PIGLIN_BRUTE: -1
    PILLAGER: -1
    POLAR_BEAR: -1
    POTION: -1
    PUFFERFISH: -1
    RABBIT: -1
    RAVAGER: -1
    SALMON: -1
    SHEEP: -1
    SHULKER: -1
    SHULKER_BULLET: -1
    SILVERFISH: -1
    SKELETON: -1
    SKELETON_HORSE: -1
    SLIME: -1
    SMALL_FIREBALL: -1
    SNIFFER: -1
    SNOW_GOLEM: -1
    SNOWBALL: -1
    SPAWNER_MINECART: -1
    SPECTRAL_ARROW: -1
    SPIDER: -1
    SQUID: -1
    STRAY: -1
    STRIDER: -1
    TADPOLE: -1
    TNT_MINECART: -1
    TRADER_LLAMA: -1
    TRIDENT: -1
    TROPICAL_FISH: -1
    TURTLE: -1
    VEX: -1
    VILLAGER: -1
    VINDICATOR: -1
    WANDERING_TRADER: -1
    WARDEN: -1
    WIND_CHARGE: -1
    WITCH: -1
    WITHER: -1
    WITHER_SKELETON: -1
    WITHER_SKULL: -1
    WOLF: -1
    ZOGLIN: -1
    ZOMBIE: -1
    ZOMBIE_HORSE: -1
    ZOMBIE_VILLAGER: -1
    ZOMBIFIED_PIGLIN: -1
    FISHING_BOBBER: -1
  enable-cached-minecraft-to-bukkit-entitytype-convert: true #(35)!
  dab: #(36)!
    enabled: true
    dont-enable-if-in-water: false #(37)!
    start-distance: 12 #(38)! # Recommended: 8
    max-tick-freq: 20 #(39)!
    activation-dist-mod: 8 #(40)!
    blacklisted-entities: [] #(41)!
  dont-save-entity:
    dont-save-primed-tnt: false #(42)!
    dont-save-falling-block: false #(43)!

###########
#  FIXES  #
###########
fixes: #(44)!
  dont-place-player-if-server-full: false #(45)!

##############
#  GAMEPLAY  #
##############
gameplay-mechanisms: #(46)!
  use-spigot-item-merging-mechanism: true #(47)!
  # **Experimental feature, report any bugs you encounter!**
  smooth-teleport: false #(48)!
  # Don't touch this unless you know what you are doing!
  max-item-stack-count: #(49)!
    max-dropped-items-stack-count: 0 #(50)!
    max-container-destroy-count: 0 #(51)!
  knockback: #(52)!
    snowball-knockback-players: false #(53)!
    egg-knockback-players: false #(54)!
    can-player-knockback-zombie: true #(55)!
  player:
    disable-moved-wrongly-threshold: false #(56)!
    max-use-item-distance: 1.0000001 #(57)!

#############
#  NETWORK  #
#############
network: #(58)!
  protocol-support: #(59)!
    jade-protocol: false #(60)!
    appleskin-protocol: false #(61)!
    asteorbar-protocol: false #(62)!
    chatimage-protocol: false #(63)!
    xaero-map-protocol: false #(64)!
    xaero-map-server-id: 513317 #(65)!
    syncmatica-protocol: false #(66)!
    syncmatica-quota: false #(67)!
    syncmatica-quota-limit: 40000000 #(68)!
  chat-message-signature: true #(69)!

##########
#  MISC  #
##########
misc: #(70)!
  message:
    unknown-command: <red><lang:command.unknown.command><newline><detail> #(71)!
  rebrand:
    server-mod-name: Leaf #(72)!
    server-gui-name: Leaf Console #(73)!
  sentry: #(74)!
    # Obtain DSN key from https://sentry.io/
    dsn: '' #(75)!
    log-level: WARN #(76)!
    only-log-thrown: true #(77)!
  secure-seed: #(78)!
    enabled: false
  remove-vanilla-username-check: true #(79)!
  remove-spigot-check-bungee-config: true #(80)!
  remove-change-non-editable-sign-warning: false #(81)!
  region-format-settings: #(82)!
    region-format: MCA #(83)!
    linear-compress-level: 1 #(84)!
    throw-on-unknown-extension-detected: false #(85)!
    flush-interval-seconds: 5 #(86)!
  lag-compensation: #(87)!
    enabled: false
    enable-for-water: false #(88)!
    enable-for-lava: false #(89)!
  including-5s-in-get-tps: true #(90)!
  # NOTICE: You must know what you're filling in and how it works! It handles all item stacks!
  hidden-item-components: [] #(91)!
  connection-message: #(92)!
    join:
      enabled: true
      message: default #(93)!
    quit:
      enabled: true
      message: default #(94)!
  cache:
    cache-player-profile-result: true #(95)!
    cache-player-profile-result-timeout: 1440 #(96)!
```

1. 本节包含异步相关的特性, 旨在通过异步处理任务来减少主线程 (Server Thread) 的负载.
2. 是否使用异步实体追踪, 可以显著提高性能, 特别是在小范围内拥有大量实体的场景中.<br>
  <br>
  __推荐值: `true` (将以下的 `enabled` 设为 true)__

    !!! note "注意"

        如果你安装了类似 Citizens, 使用真实实体或玩家类型的实体作为 "NPC" 的插件, 请参阅下文的 `async-entity-tracker.compat-mode` 以获取更多信息.

3. 是否开启兼容模式, 以兼容类似 Citizens 或其他使用真实实体或玩家类型的实体作为 "NPC" 的插件.<br>
  如果设为 `true`, 可以修复玩家类型的 NPC 有时消失的可见性问题.<br>
  <br>
  ==仅当== 安装了 Citizens 或其他任意类似的基于真实实体的 NPC 插件时，才需开启 `compat-mode` 来使用异步实体追踪功能.<br>
  <br>
  我们仍然推荐使用基于发包 / 虚拟实体的 NPC 插件以获得更好的性能, 例如: [ZNPC Plus](https://github.com/Pyrbu/ZNPCsPlus), [Adyeshach](https://github.com/TabooLib/Adyeshach), [Fancy NPC](https://modrinth.com/plugin/fancynpcs), 等，使用这类插件后可以关闭 `compat-mode`.
4. 异步实体追踪可使用的最大线程数.<br>
   如果设为 `0`，将自动选择 CPU 核心数 1/4 的线程数，且不少于 1.<br>
  <br>
  __推荐值: CPU 核心数的 1/2__
5. 空闲线程的超时时间, 超过该时间并且无任务的线程将被终止.<br>
  (以 秒 为单位)
6. 是否开启异步玩家数据保存.

    !!! warning "警告"

        实验性功能，在某些情况下可能导致玩家数据丢失!

7. 是否开启异步生物寻路.<br>
  <br>
  __推荐值: `true` (将以下的 `enabled` 设为 true)__
8. 异步生物寻路可使用的最大线程数.<br>
   如果设为 `0`，将自动选择 CPU 核心数 1/4 的线程数，且不少于 1.<br>
  <br>
  __推荐值: CPU 核心数的 1/3__
9. 空闲线程的超时时间, 超过该时间并且无任务的线程将被终止.<br>
  (以 秒 为单位)
10. 是否开启异步生物生成.<br>
  对于拥有大量实体的服务器，开启此配置项可以提升近 15% 的性能. 并且你必须将 Paper 的 `per-player-mob-spawns` 设为 `true`, 此功能才能生效.<br>
  需要注意的是: 此功能并不会完全异步生物生成 (这样做非常不安全). 它只是将生物生成所需的一些耗时计算分担到其他线程上.<br>
  <br>
  __推荐值: `true`__
11. 是否开启异步定位.<br>
  此功能将结构定位任务的负载分担到其他线程.<br>
  目前仅支持:
    * `/locate` 命令
    * 海豚寻找附近的沉船, 海底废墟或埋葬的宝藏
    * 末影之眼定位要塞
  <br><br>
  __推荐值: `true` (将以下的 `enabled` 设为 true)__
12. 异步定位可使用的最大线程数.<br>
   如果设为 &leq; `0`，将自动使用 1 个线程.<br>
  <br>
  __推荐值: `1` 或 `2`__
13. 空闲线程的超时时间, 超过该时间并且无任务的线程将被终止.<br>
  (以 秒 为单位)



14. 本节包含性能调优相关的配置, 旨在通过减少不必要的计算, 或采用更高效的逻辑 / 算法优化服务器.
15. 是否使用 JDK 21 引入的 [虚拟线程 (Virtual Thread)](https://javaguide.cn/java/concurrent/virtual-thread.html) 处理异步聊天任务.<br>
  <br>
  __推荐值: `true`__
16. 是否使用 JDK 21 引入的 [虚拟线程 (Virtual Thread)](https://javaguide.cn/java/concurrent/virtual-thread.html) 处理 CraftAsyncScheduler, 这可以提高使用异步调度器的插件的性能.<br>
  <br>
  __推荐值: `true`__
17. 是否在获取 TileEntity / BlockState 时创建并使用其快照.<br>
  <br>
  一些插件可能会使用 `getHolder` 方法来获取物品栏的所有者, 这涉及获取 BlockState 的副本. 而创建 BlockState 的副本或解析物品数据相当耗时, 其中涉及 NBT 的解析.<br>
  例如, 在拥有大量密集漏斗的场景中, 如果插件在监听某些事件 (例如与漏斗相关的事件) 时调用此类方法, 频繁的调用将会显著影响性能.<br>
  参阅 Paper 的 [API-to-get-a-BlockState-without-a-snapshot.patch#L6](https://github.com/PaperMC/Paper-archive/blob/b48403bd69f534ffd43fe2afb4e8e1f1ffa95fe1/patches/server/0160-API-to-get-a-BlockState-without-a-snapshot.patch#L6) 补丁以获取更多信息.
    * 如果设为 `true`, 每次插件调用相关方法时, 都会创建 BlockState 的快照 (副本).
    * 如果设为 `false`, 每次插件调用相关方法时将, 直接获取目标 BlockState 本身, 除非插件指定要求使用其快照.
  <br><br>
  __推荐值: (推荐仅在遇到上述卡顿时设为 `false`)__
18. 当实体处在 *inactive tick* 时, 是否将 *goal selector* 的 tick 计算限制为每秒一次. 这可以略微提高性能, 但会对游戏机制有略微影响.<br>
  <br>
  __推荐值: `true`__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

19. 当目标容器已满时, 是否冷却漏斗, 以避免其尝试移动物品.<br>
  <br>
  __推荐值: `true` (将以下的 `enabled` 设为 true)__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

20. 当漏斗冷却时, 等待多长时间再次将再次尝试移动物品的操作.<br>
  (以 tick 为单位)<br>
  如果设为 &leq; `0`, 将禁用此冷却功能.<br>
  <br>
  __推荐值: `8`__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>8</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>0</code></td></tr>
    </table>

21. 如果地图没有 Renderer, 是否跳过地图内容的更新.<br>
  这可以提高使用 ImageMap 之类插件时的性能.<br>
  <br>
  __推荐值: `true`__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

    !!! note "注意"

        开启此配置项可能会导致原版地图的内容停止更新.

22. 当生物处在 *不活跃* 且 *无感知* 的状态时, 是否跳过其 AI tick 的计算. *无感知* 的生物会像呆子一样, 不会自主活动, 也不会在与其交互时作出反应.<br>
  <br>
  __推荐值: `true`__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

23. 本节包含减少发送无用数据包的配置.
24. 是否减少发送给玩家的无用实体移动数据包.<br>
  <br>
  __推荐值: `true`__
25. 是否使用性能更好的动力铁轨逻辑. 将使用完全重写的动力铁轨迭代逻辑, 可提升近 4 倍 的性能.<br>
  <br>
  __推荐值: `true`__
26. 是否优化矿车的 tick 计算. 通过跳过部分碰撞检测的方式, 以减少 `getEntities()` 调用和一些 Bukkit 事件调用的耗时.<br>
  这可以更好地承载大量的堆叠矿车, 特别适用于 [无政府服](https://minecraftservers.org/type/anarchy).<br>
  <br>
  __推荐值: `true`__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

27. 每隔多少 tick 检测一次矿车碰撞.<br>
  (以 tick 为单位)<br>
  <br>
  __推荐值: `30`__
28. 是否为世界结构生成使用更快的任务排序.

    !!! note "注意"

        此配置项可能导致结构生成任务的合并顺序不一致.

29. 是否使用更快的随机数生成器.<br>
  随机数生成在 Minecraft 中几乎无处不在, 此功能可以显著提升性能.<br>
  <br>
  __推荐值: `true` (将以下的 `enabled` 设为 true)__

    !!! note "注意"

        需要使用支持 `RandomGenerator` 和 LXM 生成器的 JVM 来运行服务器. 一些 JRE 不支持此功能, 可能会导致崩溃.

30. 需要使用哪种随机数生成器?<br>
  可参阅 [Java 随机数生成器](https://www.baeldung.com/java-17-random-number-generators#1-api-design-1), 了解所有可用的随机数生成器.<br>
  <br>
  __推荐值: `Xoroshiro128PlusPlus`__
31. 是否为世界生成使用更快的随机数生成器.<br>
    * 如果设为 `true`, 与世界生成相关的 `Random` 调用将使用上述 `random-generator` 指定的随机数生成器, 世界生成将会与原版略有不同.
    * 如果设为 `false`, 与世界生成相关的 `Random` 调用将使用原版的传统随机数生成器.
  <br><br>
  __推荐值: `true`__

    <table>
    <tr><td><b>基于目标的推荐值</b></td><td></td></tr>
    <tr><td><i>优化</i></td><td><code>true</code></td></tr>
    <tr><td><i>原版行为</i></td><td><code>false</code></td></tr>
    </table>

