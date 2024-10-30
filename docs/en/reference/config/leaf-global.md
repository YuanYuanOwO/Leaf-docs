# Leaf global config

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
  async-playerdata-save: #(6)!
    enabled: false
  async-pathfinding: #(7)!
    enabled: false
    max-threads: 0 #(8)!
    keepalive: 60 #(9)!
  async-mob-spawning: #(10)!
    enabled: true
  # ***Experimental feature, report any bugs you encounter!***
  async-locator: #(11)!
    enabled: false
    threads: 0 #(12)!

##########
#  PERF  #
##########
performance: #(13)!
  use-virtual-thread-for-async-chat-executor: true #(14)!
  use-virtual-thread-for-async-scheduler: true #(15)!
  inactive-goal-selector-throttle: true #(16)!
  skip-map-item-data-updates-if-map-does-not-have-craftmaprenderer: true #(17)!
  skip-ai-for-non-aware-mob: true #(18)!
  reduce-packets: #(19)!
    reduce-entity-move-packets: false #(20)!
  optimized-powered-rails: true #(21)!
  optimize-minecart:
    enabled: false #(22)!
    skip-tick-count: 30 #(23)!
  # May cause the inconsistent order of future compose tasks.
  faster-structure-gen-future-sequencing: true #(24)!
  # Requires a JVM that supports RandomGenerator and the LXM generators.
  # Some JREs don't support this and will cause a crash.
  faster-random-generator: #(25)!
    enabled: false
    warn-for-slime-chunk: true #(26)!
    use-legacy-random-for-slime-chunk: false #(27)!
  entity-timeouts: #(28)!
    SNOWBALL: -1 # Recommended: 200
    LLAMA_SPIT: -1 # Recommended: 150
    ALLAY: -1
    AREA_EFFECT_CLOUD: -1
    ARMADILLO: -1
    ARMOR_STAND: -1
    ARROW: -1
    AXOLOTL: -1
    BAT: -1 # Recommended: 6000
    BEE: -1
    BLAZE: -1
    BLOCK_DISPLAY: -1
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
    END_CRYSTAL: -1
    ENDER_DRAGON: -1
    ENDER_PEARL: -1
    ENDERMAN: -1
    ENDERMITE: -1
    EVOKER: -1
    EVOKER_FANGS: -1
    EXPERIENCE_BOTTLE: -1
    EXPERIENCE_ORB: -1
    EYE_OF_ENDER: -1
    FALLING_BLOCK: -1
    FIREWORK_ROCKET: -1
    FOX: -1
    FROG: -1
    FURNACE_MINECART: -1
    GHAST: -1
    GIANT: -1
    GLOW_ITEM_FRAME: -1
    GLOW_SQUID: -1
    GOAT: -1
    GUARDIAN: -1
    HOGLIN: -1
    HOPPER_MINECART: -1
    HORSE: -1
    HUSK: -1
    ILLUSIONER: -1
    INTERACTION: -1
    IRON_GOLEM: -1
    ITEM: -1
    ITEM_DISPLAY: -1
    ITEM_FRAME: -1
    OMINOUS_ITEM_SPAWNER: -1
    FIREBALL: -1 # Recommended: 600
    LEASH_KNOT: -1
    LIGHTNING_BOLT: -1
    LLAMA: -1
    MAGMA_CUBE: -1
    MARKER: -1
    MINECART: -1
    MOOSHROOM: -1
    MULE: -1
    OCELOT: -1
    PAINTING: -1
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
    SPAWNER_MINECART: -1
    SPECTRAL_ARROW: -1 # Recommended: 200
    SPIDER: -1
    SQUID: -1
    STRAY: -1
    STRIDER: -1
    TADPOLE: -1
    TEXT_DISPLAY: -1
    TNT: -1
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
  enable-cached-minecraft-to-bukkit-entitytype-convert: true #(29)!
  dab: #(30)!
    enabled: true
    start-distance: 12 #(31)! # Recommended: 8
    max-tick-freq: 20 #(32)!
    activation-dist-mod: 8 #(33)!
    blacklisted-entities: [] #(34)!
  dont-save-entity:
    dont-save-primed-tnt: false #(35)!
    dont-save-falling-block: false #(36)!

###########
#  FIXES  #
###########
fixes: #(37)!
  dont-place-player-if-server-full: false #(38)!

##############
#  GAMEPLAY  #
##############
gameplay-mechanisms: #(39)!
  use-spigot-item-merging-mechanism: true #(40)!
  # Don't touch this unless you know what you are doing!
  max-item-stack-count: #(41)!
    max-dropped-items-stack-count: 0 #(42)!
    max-container-destroy-count: 0 #(43)!
  knockback:
    snowball-knockback-players: false #(44)!
    egg-knockback-players: false #(45)!
    can-player-knockback-zombie: true #(46)!
  player:
    disable-moved-wrongly-threshold: false #(47)!
    max-use-item-distance: 1.0000001 #(48)!

#############
#  NETWORK  #
#############
network: #(49)!
  protocol-support: #(50)!
    jade-protocol: false #(51)!
    appleskin-protocol: false #(52)!
    asteorbar-protocol: false #(53)!
    chatimage-protocol: false #(54)!
    xaero-map-protocol: false #(55)!
    xaero-map-server-id: 513317 #(56)!
    syncmatica-protocol: false #(57)!
    syncmatica-quota: false #(58)!
    syncmatica-quota-limit: 40000000 #(59)!
  chat-message-signature: true #(60)!

##########
#  MISC  #
##########
misc: #(61)!
  message:
    unknown-command: <red><lang:command.unknown.command><newline><detail> #(62)!
  rebrand:
    server-mod-name: Leaf #(63)!
    server-gui-name: Leaf Console #(64)!
  sentry:
    # Obtain from https://sentry.io/
    dsn: '' #(65)!
    log-level: WARN #(66)!
    only-log-thrown: true #(67)!
  # WARNING! You need to backup your server and prepare a new world if you want to enable it,
  # at least for now.
  secure-seed: #(68)!
    enabled: false
  remove-vanilla-username-check: true #(69)!
  remove-spigot-check-bungee-config: true #(70)!
  remove-change-non-editable-sign-warning: false #(71)!
  region-format-settings: #(72)!
    region-format: MCA #(73)!
    linear-compress-level: 1 #(74)!
    throw-on-unknown-extension-detected: false #(75)!
    flush-interval-seconds: 5 #(76)!
  including-5s-in-get-tps: true #(77)!
  # NOTICE: You must know what you're filling in and how it works! It will handle all itemStacks!
  hidden-item-components: [] #(78)!
  connection-message: #(79)!
    join:
      enabled: true
      message: default #(80)!
    quit:
      enabled: true
      message: default #(81)!
  cache:
    cache-player-profile-result: true #(82)!
    # The timeout of the cache. Unit: Minutes.
    cache-player-profile-result-timeout: 1440 #(83)!
```

1. Asynchronous features below are aiming to reduce the load on server threads by processing tasks asynchronously.
2. Make entity tracking saving asynchronously, can improve performance significantly, especially in some massive entities in small area situations.
3. Enable compat mode ONLY if Citizens or NPC plugins using real entity has installed. Compat mode fixed visibility issue with player type NPCs of Citizens, but still recommend to use packet based / virtual entity NPC plugin, e.g. ZNPC Plus, Adyeshach, Fancy NPC or else.
4. Maximum number of threads to use, 0 for auto. __(Recommended value: 1/2 of CPU cores)__
5. Thread keepalive time in seconds, threads with no tasks will be terminated if they exceed the time. 
6. Make PlayerData saving asynchronously.
7. Make mob pathfinding calculation asynchronously.
8. Maximum number of threads to use, 0 for auto. __(Recommended value: 1/4 of CPU cores)__
9. Thread keepalive time in seconds, threads with no tasks will be terminated if they exceed the time. 
10. Whether asynchronous mob spawning should be enabled. On servers with many entities, this can improve performance by up to 15%. You must have Paper's `per-player-mob-spawns` config set to true for this to work. One quick note - this does not actually spawn mobs async (that would be very unsafe). This just offloads some expensive calculations that are required for mob spawning.
11. ___Experimental feature, report any bugs you encounter!___  Whether asynchronous locator should be enabled. This offloads structure locating to other threads. Only for locate command, dolphin treasure finding and eye of ender currently.
12. Maximum number of threads to use, 0 for auto. __(Recommended value: 1)__

13. The features below are aiming to reduce unnecessary calculations & use more efficient methods to optimize the server.
14. Use the new Virtual Thread introduced in JDK 21 for Async Chat Executor.
15. Use the new Virtual Thread introduced in JDK 21 for CraftAsyncScheduler, which could improve performance of plugin that uses async scheduler.
16. Throttles the AI goal selector in entity inactive ticks. This can improve performance by a few percent, but has minor gameplay implications.
17. Skip map item data update if the map doesn't have a renderer.
18. Skip AI ticks if the mob is inactive and not being aware(e.g. being attacked)
19. This section is for the useless packet reducing features.
20. Enable this feature to reduce the useless entity movement packets sent to players.
21. Whether to use optimized powered rails. 
22. Enable this feature to handle a large amount of stacked minecarts better. By skipping tick collisions to reduce expensive getEntities and bukkit event calls, useful for anarchy servers. __(Recommended value: true)__
23. How many ticks to skip before checking for collisions.
24. __May cause the inconsistent order of future compose tasks.__
25. Use faster random generator? (Up to 100X faster) Requires a JVM that supports RandomGenerator and the LXM generators. __Some JREs don't support this and will cause a crash.__
26. Warn if you are not using legacy random source for slime chunk generation.
27. Use legacy random source for slime chunk generation to follow the vanilla behavior. 
28. These values define an entity's maximum lifespan. If an entity is in this list, and it has survived for longer than that number of ticks, then it will be removed. Setting a value to -1 will disable the check. 
29. Enable this to cache the expensive Minecraft EntityType to Bukkit EntityType conversion.
30. Optimizes entity brains when they're far away from players.
31. This value determines how far away an entity has to be from the player to start being affected by DEAR.
32. This value defines how often in ticks, the furthest entity will get their pathfinders and behaviors ticked. 20 = 1s
33. This value defines how much distance modifies an entity's tick frequency. freq = (distanceToPlayer^2) / (2^value). If you want further away entities to tick less often, use 7. If you want further away entities to tick more often, try 9.
34. A list of entities to ignore for activation. Example: [VILLAGER]
35. Disable save primed tnt on chunk unloads. Useful for redstone/technical servers, can prevent machines from being exploded by TNT when players disconnected.
36. Disable save falling block on chunk unloads.

37. This section contains bugfixes for specific issues.
38. Don't let player join server if the server is full. If enable this, you should use 'purpur.joinfullserver' permission instead of PlayerLoginEvent#allow to let player join full server.

39. This section contains the features that modify the game mechanics.
40. Whether to use Spigot's dropped item merging mechanism.
41. Don't touch this unless you know what you are doing!
42. Maximum amount of dropped items to stack.
43. Maximum count of ItemStack to drop when container is destroyed.
44. Make snowball can knockback players.
45. Make egg can knockback players.
46. Players can knockback zombie.
47. Disable moved too quickly/wrongly checks. __(Recommended value: true)__
48. The max distance of UseItem for players. Set to -1 to disable max-distance-check. NOTE: if set to -1 to disable the check, players are able to use some packet modules of hack clients, and NoCom exploit!!

49. Features below are server networking related.
50. This section contains protocol support for some QoL/Utility mods. (All protocols require client-side mod to be installed)
51. Whether to enable [Jade](https://modrinth.com/mod/jade) protocol support. 
52. Whether to enable [AppleSkin](https://modrinth.com/mod/appleskin) protocol support. 
53. Whether to enable [AsteorBar](https://modrinth.com/mod/asteorbar) protocol support. 
54. Whether to enable [ChatImage](https://modrinth.com/mod/chatimage) protocol support. 
55. Whether to enable [XaeroMap](https://modrinth.com/mod/xaeros-minimap) protocol support.
56. Numeric id for XaeroMap to indentify the server. This will generate randomly on first start.
57. Whether to enable [Syncmatica](https://modrinth.com/mod/syncmatica) protocol support.
58. Enable quota for Syncmatica.
59. Maximum file size per syncmatica in bytes.
60. Whether or not enable chat message signature, disable will prevent players to report chat messages. And also disables the popup when joining a server without 'secure chat', such as offline-mode servers.

61. Miscellaneous features
62. Unknown command message, using [MiniMessage](https://docs.advntr.dev/minimessage/format) format, set to "default" to use vanilla message, placeholder: <detail>, shows detail of the unknown command information.
63. Server brand name that will show in F3 menu.
64. Server GUI window name if you launched server without --nogui option.
65. Sentry DSN for improved error logging, leave blank to disable, obtain from [sentry.io](https://sentry.io)
66. Logs with a level higher than or equal to this level will be recorded.
67. Only log with a Throwable will be recorded after enabling this. 
68. Once you enable secure seed, all ores and structures are generated with 1024-bit seed instead of using 64-bit seed in vanilla, made seed cracker become impossible. __WARNING! You need to backup your server and prepare a new world if you want to enable it, at least for now.__
69. Remove Vanilla username check allowing all characters as username.
70. Enable player enter backend server through proxy without enabling bungeecord mode in spigot.yml.
71. Enable to prevent console spam. __(Recommended value: true)__
72. Linear is a region file format that uses ZSTD compression instead of ZLIB. This format saves about 50% of disk space. Read Documentation before using: https://github.com/xymb-endcrystalme/LinearRegionFileFormatTools __Disclaimer: This is an experimental feature, there is potential risk to lose chunk data. Backup your server before switching to Linear.__
73. Available region formats: MCA, LINEAR
74. Linear region file format compression level.
75. Whether to throw error when unknown region format extension is detected.
76. Linear region file format data flush interval in seconds.
77. Whether to include 5s in get TPS.
78. Controls whether specified component information is sent to clients. This may break resource packs and mods that rely on this information. It needs a component type list, incorrect things will not work. You can fill it with ["custom_data"] to hide components of CUSTOM_DATA. Also, it can avoid some frequent client animations. __NOTICE: You must know what you're filling in and how it works! It will handle all itemStacks!__
79. Connection message, using MiniMessage format, set to "default" to use vanilla join message. Available placeholders: __%player_name%__ - player name   __%player_displayname%__ - player display name
80. Join message of player.
81. Quit message of player.
82. Cache the player profile result on they first join. It's useful if Mojang's verification server is down. 
83. The timeout of the cache. Unit: Minutes.
