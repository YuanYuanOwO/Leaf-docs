# Leaf global config

!!! info "Info"

    The YAML config below shows the structure and default config values of Leaf's global config (==config/leaf-global.yml==)

    The config bases on the latest 1.21.1 branch of Leaf

    Click arrow button behind the config node to show description of it

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
  # May cause the inconsistent order of future compose tasks.
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
    BAT: -1 # Recommended: 6000
    BEE: -1
    BLAZE: -1
    BOAT: -1
    BOGGED: -1
    BREEZE: -1
    BREEZE_WIND_CHARGE: -1 # Recommended: 200
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
    DRAGON_FIREBALL: -1 # Recommended: 400
    DROWNED: -1
    EGG: -1 # Recommended: 300
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
    FIREBALL: -1 # Recommended: 600
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
    SMALL_FIREBALL: -1 # Recommended: 400
    SNIFFER: -1
    SNOW_GOLEM: -1
    SNOWBALL: -1
    SPAWNER_MINECART: -1
    SPECTRAL_ARROW: -1 # Recommended: 200
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
    WIND_CHARGE: -1 # Recommended: 300
    WITCH: -1
    WITHER: -1
    WITHER_SKELETON: -1
    WITHER_SKULL: -1 # Recommended: 400
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
  sentry:
    # Obtain from https://sentry.io/
    dsn: '' #(74)!
    log-level: WARN #(75)!
    only-log-thrown: true #(76)!
  secure-seed: #(77)!
    enabled: false
  remove-vanilla-username-check: true #(78)!
  remove-spigot-check-bungee-config: true #(79)!
  remove-change-non-editable-sign-warning: false #(80)!
  region-format-settings: #(81)!
    region-format: MCA #(82)!
    linear-compress-level: 1 #(83)!
    throw-on-unknown-extension-detected: false #(84)!
    flush-interval-seconds: 5 #(85)!
  lag-compensation: #(86)!
    enabled: false
    enable-for-water: false #(87)!
    enable-for-lava: false #(88)!
  including-5s-in-get-tps: true #(89)!
  # NOTICE: You must know what you're filling in and how it works! It will handle all itemStacks!
  hidden-item-components: [] #(90)!
  connection-message: #(91)!
    join:
      enabled: true
      message: default #(92)!
    quit:
      enabled: true
      message: default #(93)!
  cache:
    cache-player-profile-result: true #(94)!
    # The timeout of the cache. Unit: Minutes.
    cache-player-profile-result-timeout: 1440 #(95)!
```

1. Asynchronous features below are aiming to reduce the load on main thread (Server Thread) by processing tasks asynchronously.
2. Make entity tracking asynchronously, can improve performance significantly, especially in some massive entities in small area situations.<br>
  <br>
  __Recommended value: `true` (set `enabled` below to true)__

    !!! note "Attention"

        if you installed plugins like Citizens, which uses real, and player type entity as "NPC", also read `compat-mode` below for more infomration.

3. Enable compat mode to be compatibile with plugins like Citizens or NPC plugins that use real, and player-type entity.<br>
  If `true`,  visibility issue that player-type NPCs may disappear sometimes can be fixed.<br>
  <br>
  You should enable `compat-mode` to use async entity tracker feature ==ONLY IF== you installed Citizens or any other kind of real entity NPC plugins.<br>
  <br>
  But we still recommend to use packet-based / virtual entity NPC plugin to gain better performance, e.g. [ZNPC Plus](https://github.com/Pyrbu/ZNPCsPlus), [Adyeshach](https://github.com/TabooLib/Adyeshach), [Fancy NPC](https://modrinth.com/plugin/fancynpcs), or else, and then `compat-mode` can be disabled.
4. Maximum number of threads for async entity tracker to use.<br>
   If the value is set to `0`, it automatically uses 1/4 of the number of CPU cores and no less than 1.<br>
  <br>
  __Recommended value: 1/2 of CPU cores__
5. Thread keepalive time, threads with no tasks will be terminated if they exceed the time.<br>
  (Unit: seconds)
6. Make PlayerData saving asynchronously.

    !!! warning "Warning"

        Experimental feature, may cause data lost in some circumstances!

7. Make mob pathfinding calculation asynchronously.<br>
  <br>
  __Recommended value: `true` (set `enabled` below to true)__
8. Maximum number of threads for async entity pathfinding to use.<br>
   If the value is set to `0`, it automatically uses 1/4 of the number of CPU cores and no less than 1.<br>
  <br>
  __Recommended value: 1/3 of CPU cores__
9. Thread keepalive time, threads with no tasks will be terminated if they exceed the time.<br>
  (Unit: seconds)
10. Whether asynchronous mob spawning should be enabled.<br>
  On servers with many entities, this can improve performance by up to 15%. You must have Paper's `per-player-mob-spawns` config set to `true` for this to work.<br>
  One quick note - this does not actually spawn mobs async (that would be very unsafe). This just offloads some expensive calculations that are required for mob spawning.<br>
  <br>
  __Recommended value: `true`__
11. Whether or not asynchronous locator should be enabled.<br>
  This offloads structure locating to other threads.<br>
  Currently available for:
    * /locate command
    * Dolphin treasure finding
    * Eye of ender stronghold finding
  <br><br>
  __Recommended value: `true` (set `enabled` below to true)__
12. Maximum number of threads for async locator to use.<br>
   If a value &leq; `0` is given, it automatically uses 1 thread.<br>
  <br>
  __Recommended value: `1` or `2`__
13. Thread keepalive time, threads with no tasks will be terminated if they exceed the time.<br>
  (Unit: seconds)

14. The features below are aiming to reduce unnecessary calculations and use more efficient methods to optimize the server.
15. Use the new Virtual Thread introduced in JDK 21 for Async Chat Executor.<br>
  <br>
  __Recommended value: `true`__
16. Use the new Virtual Thread introduced in JDK 21 for CraftAsyncScheduler, which could improve performance of plugin that uses async scheduler.<br>
  <br>
  __Recommended value: `true`__
17. Whether to create the snapshot of TileEntity / BlockState when retirving them.<br>
  <br>
  Some plugins may use getHolder to get the holder for a inventory, which invloved getting the blockstate.<br>
  For example, if there are tons of hoppers and plugins call this method when listening some events (e.g. hopper related events). It is very expensive to re-create blockstate and parse item stack in massive and frequently calls.<br>
  See Paper's [API-to-get-a-BlockState-without-a-snapshot.patch#L6](https://github.com/PaperMC/Paper-archive/blob/b48403bd69f534ffd43fe2afb4e8e1f1ffa95fe1/patches/server/0160-API-to-get-a-BlockState-without-a-snapshot.patch#L6) for more information.
    * If `true`, it will create snapshot (copy) of blockstate everytime when plugins call related methods.
    * If `false`, it will get real blockstate itself when plugins call related methods, unless the plugin defines to use snapshot.
  <br><br>
  __Recommended value: `false` (Only if you encounter specific lag described above)__
18. Throttles the AI goal selector in entity inactive ticks. This can improve performance by a few percent, but has minor gameplay implications.<br>
  <br>
  __Recommended value: `true`__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code></td></tr>
    </table>

19. Whether to throttle attempts on moving items for hopper if the target container is full.<br>
  <br>
  __Recommended value: `true` (set `enabled` below to true)__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code></td></tr>
    </table>

20. How many ticks to wait before the next move item attempt when the hopper is throttled.<br>
  If a value &leq; `0` is given, this throttling feature is disabled.<br>
  <br>
  __Recommended value: `5`__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>5</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>0</code></td></tr>
    </table>

21. Whether to skip map item data update if the map doesn't have a renderer.<br>
  This can improve performance if using image map kind of plugins.<br>
  <br>
  __Recommended value: `true`__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code></td></tr>
    </table>

    !!! note "Attention"

        This may cause vanilla map item data to stop be updated.

22. Whether to skip AI ticks if the mob is inactive and not being aware (e.g. being attacked).<br>
  <br>
  __Recommended value: `true`__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code></td></tr>
    </table>

23. This section is for the useless packet reducing features.
24. Enable this feature to reduce the useless entity movement packets sent to players.<br>
  <br>
  __Recommended value: `true`__
25. Whether to use optimized powered rails. Uses fully rewritten version of powered rail iteration logic, can achieve 4x faster performance.<br>
  <br>
  __Recommended value: `true`__
26. Wether to optimize minecarts ticking. By skipping tick collisions to reduce expensive `getEntities` calls and bukkit event calls.<br>
  Enables this feature to handle a large amount of stacked minecarts better which is useful for anarchy servers.<br>
  <br>
  __Recommended value: `true`__

    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code></td></tr>
    </table>

27. How many ticks to skip before checking for the next minecart collisions.<br>
  <br>
  __Recommended value: `30`__
28. Whether to use faster 

    !!! note "Attention"

        This may cause the inconsistent order of future compose tasks.

29. Use faster random generator? (Up to 100X faster) Requires a JVM that supports RandomGenerator and the LXM generators. __Some JREs don't support this and will cause a crash.__
30. TODO
31. TODO
32. Warn if you are not using legacy random source for slime chunk generation.
33. Use legacy random source for slime chunk generation to follow the vanilla behavior.
34. These values define an entity's maximum lifespan. If an entity is in this list, and it has survived for longer than that number of ticks, then it will be removed. Setting a value to -1 will disable the check.
35. Enable this to cache the expensive Minecraft EntityType to Bukkit EntityType conversion.
36. Optimizes entity brains when they're far away from players.
37. After enabling this, non-aquatic entities in the water will not be affected by DAB.
This could fix entities suffocate in the water. Fixed [Pufferfish issue#58](https://github.com/pufferfish-gg/Pufferfish/issues/58)
38. This value determines how far away an entity has to be from the player to start being affected by DEAR.
39. This value defines how often in ticks, the furthest entity will get their pathfinders and behaviors ticked. 20 = 1s
40. This value defines how much distance modifies an entity's tick frequency. freq = (distanceToPlayer^2) / (2^value). If you want further away entities to tick less often, use 7. If you want further away entities to tick more often, try 9.
41. A list of entities to ignore for activation. Example: [VILLAGER]
42. Disable save primed tnt on chunk unloads. Useful for redstone/technical servers, can prevent machines from being exploded by TNT when players disconnected.
43. Disable save falling block on chunk unloads.

44. This section contains bugfixes for specific issues.
45. Whether don't let player to join a server if the server is full.<br>
  If `true`, you should give player `purpur.joinfullserver` permission instead of using `PlayerLoginEvent#allow` to enable player to join a full server.

46. This section contains the features that modify the game mechanics.
47. Whether to use Spigot's dropped item merging mechanism.
48. TODO
49. Don't touch this unless you know what you are doing!
50. Maximum amount of dropped items to stack.
51. Maximum count of ItemStack to drop when container is destroyed.
52. TODO
53. Make snowball can knockback players.
54. Make egg can knockback players.
55. Players can knockback zombie.
56. Disable moved too quickly/wrongly checks.
__(Recommended value: true)__
57. The max distance of UseItem for players. Set to -1 to disable max-distance-check. NOTE: if set to -1 to disable the check, players are able to use some packet modules of hack clients, and NoCom exploit!!

58. Features below are server networking related.
59. This section contains protocol support for some QoL/Utility mods. (All protocols require client-side mod to be installed)
60. Whether to enable [Jade](https://modrinth.com/mod/jade) protocol support.
61. Whether to enable [AppleSkin](https://modrinth.com/mod/appleskin) protocol support.
62. Whether to enable [AsteorBar](https://modrinth.com/mod/asteorbar) protocol support.
63. Whether to enable [ChatImage](https://modrinth.com/mod/chatimage) protocol support.
64. Whether to enable [XaeroMap](https://modrinth.com/mod/xaeros-minimap) protocol support.
65. Numeric id for XaeroMap to indentify the server. This will generate randomly on first start.
66. Whether to enable [Syncmatica](https://modrinth.com/mod/syncmatica) protocol support.
67. Enable quota for Syncmatica.
68. Maximum file size per syncmatica in bytes.
69. Whether or not enable chat message signature, disable will prevent players to report chat messages. And also disables the popup when joining a server without 'secure chat', such as offline-mode servers.

70. Miscellaneous features
71. Unknown command message, using [MiniMessage](https://docs.advntr.dev/minimessage/format) format, set to "default" to use vanilla message, placeholder: <detail>, shows detail of the unknown command information.
72. Server brand name that will show in F3 menu.
73. Server GUI window name if you launched server without --nogui option.
74. Sentry DSN for improved error logging, leave blank to disable, obtain from [sentry.io](https://sentry.io)
75. Logs with a level higher than or equal to this level will be recorded.
76. Only log with a Throwable will be recorded after enabling this. 
77. Once you enable secure seed, all ores and structures are generated with 1024-bit seed instead of using 64-bit seed in vanilla, made seed cracker become impossible. __WARNING! You need to backup your server and prepare a new world if you want to enable it, at least for now.__
78. Remove Vanilla username check allowing all characters as username.
79. Enable player enter backend server through proxy without enabling bungeecord mode in spigot.yml.
80. Enable to prevent console spam. __(Recommended value: true)__
81. Linear is a region file format that uses ZSTD compression instead of ZLIB. This format saves about 50% of disk space. Read Documentation before using: https://github.com/xymb-endcrystalme/LinearRegionFileFormatTools __Disclaimer: This is an experimental feature, there is potential risk to lose chunk data. Backup your server before switching to Linear.__
82. Available region formats: MCA, LINEAR
83. Linear region file format compression level.
84. Whether to throw error when unknown region format extension is detected.
85. Linear region file format data flush interval in seconds.
86. TODO
87. TODO
88. TODO
89. Whether to include 5s in get TPS.
90. Controls whether specified component information is sent to clients. This may break resource packs and mods that rely on this information. It needs a component type list, incorrect things will not work. You can fill it with ["custom_data"] to hide components of CUSTOM_DATA. Also, it can avoid some frequent client animations. __NOTICE: You must know what you're filling in and how it works! It will handle all itemStacks!__
91. Connection message, using MiniMessage format, set to "default" to use vanilla join message. Available placeholders: __%player_name%__ - player name   __%player_displayname%__ - player display name
92. Join message of player.
93. Quit message of player.
94. Cache the player profile result on they first join. It's useful if Mojang's verification server is down.
95. The timeout of the cache. Unit: Minutes.
