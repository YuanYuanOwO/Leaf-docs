# Gale global config

!!! info "Info"

    The YAML config below shows the structure and default config values of Gale's global config (==config/gale-global.yml==)

    The config bases on the latest 1.21.1 branch of Leaf

    Click arrow button behind the config node to show description of it

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

1. Whether books should be writeable.<br>
  If set to `false`, players with the permission `gale.writebooks` (default: `op`) can still use books.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>
    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td>-</td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>true</code></td></tr>
    </table>

2. Whether to log specific text and events to the console and the log files.
3. When a player sends a message packet that is empty.<br>
  (this is harmless, it usually happens when the player's client is outdated)

    <table>
    <tr><td></td><td><b>Default</b></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>true</code></td></tr>
    </table>

4. When a player's message packet has expired.<br>
  (this is harmless, it usually happens when the player's client's chat is a bit out-of-sync)

    <table>
    <tr><td></td><td><b>Default</b></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>true</code></td></tr>
    </table>

5. Whether to add a [NOT SECURE] marker in front of unsigned chat packets.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

6. When a player's data is loaded, and they have advancements that don't exist anymore.
  (this is harmless, it usually happens when the server upgraded to the newer Minecraft version)

    <table>
    <tr><td></td><td><b>Default</b></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

7. The logging level for errors when the server encounters invalid pool elements in world data.<br>
  <br>
  Invalid pool elements are parts of generated structures (such as Mineshafts) that are corrupted or not updated from old versions properly.<br>
  <br>
  The errors generated by this are huge, and happen often on old servers that have updated across many Minecraft versions.<br>
  <br>
  The error logs are usually pointless: there is nothing you can do about it.<br>
  <br>
  The valid values for this setting are: `"none"`, `"info"`, `"warn"` and `"error"`.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>"none"</code> 🛈</td><td><code>"info"</code></td><td><code>"error"</code></td><td><code>"error"</code></td></tr>
    </table>

    > 🛈 = The default value is `"info"` to prevent any errors going unnoticed by default, but the recommended value is `"none"` because these errors are usually meaningless and unsolvable anyway.

8. When a player's data is loaded, and they have statistics that don't exist anymore.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

9. When a very old Bukkit plugin is loaded.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>true</code></td></tr>
    </table>

10. When a player did not send a valid profile during login.<br>
  (this usually indicates a hacker is trying to flood your server's joining capacity)

    <table>
    <tr><td></td><td><b>Default</b></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

11. Whether to include a player's coordinates in the join message logged to the console.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

12. When the plugin library loader starts downloading libraries.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

13. When the plugin library loader finished loading a library.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

14. When the plugin library loader starts loading libraries for a plugin.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

15. When a player attempts to set a block that is *very* far away.<br>
  (this usually indicates a hacker is trying to get information about other players' locations, or is using hack client)

    <table>
    <tr><td></td><td><b>Default</b></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

16. When a player's data is loaded, and they have recipe book recipes that don't exist anymore.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>true</code></td></tr>
    </table>

17. Whether to ignore any legacy structure data, for which the NBT tag parser returns null for some reason.
    * If `true`, no warning will be given when this happens.
    * If `false`, an exception will be thrown in the console when this happens.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code> 🛈</td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td>-</td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code></td></tr>
    </table>

    > 🛈 = The default value is `false` to prevent any errors going unnoticed by default, but the recommended value is `true` because these errors are usually meaningless and unsolvable anyway.

18. Whether to send more frequent keepalive packets than vanilla.
    * If `true`, a keepalive packet is sent to every client every second, and they are not kicked if they respond to at least one of them within 30 seconds.
    * If `false`, a keepalive packet is sent to every client every 15 seconds, and they are kicked if they do not respond to it within 30 seconds.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td>-</td></tr>
    <tr><td><i>Vanilla behavior</i></td><td>- (this doesn't affect gameplay)</td></tr>
    </table>

19. Whether to add the oversleep portion of the last tick's time to the `/tps` command.<br>
  This only has any effect if `enabled` above is `true`.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-</td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td>-</td></tr>
    <tr><td><i>Paper behavior</i></td><td>-</td></tr>
    </table>

20. Whether to include the time that the last tick took in the `/tps` command.<br>
  The time that the last tick took only represents that one tick, so it is normally not very useful.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td>-</td></tr>
    <tr><td><i>Paper behavior</i></td><td><code>false</code></td></tr>
    </table>

21. The maximum time, given in ticks, that a premium account login can take.
    * If this time is exceeded, the connection is closed.
    * If a value &leq; `0` is given, it will default to the same as vanilla, which is currently `600` ticks (30 seconds).

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-</td><td><code>-1</code></td><td><code>-1</code></td><td><code>-1</code></td></tr>
    </table>
    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td>-</td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>-1</code></td></tr>
    </table>

22. Whether to verify the order of chat messages.
    * If this option is set to `true`, and a player sends an out-of-order chat packet for some reason, they will be kicked.
    * If this option is set to `false`, no verification will occur, and players will not be kicked.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>
    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td>-</td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>true</code></td></tr>
    </table>

23. The interval, given in ticks, at which to increase the time-related statistics such as total playtime, time since the last death, etc.<br>
  Changing this value does not change the speed with which statistics increase from vanilla.<br>
  <br>
  For example:
    * If this value is set to `20`, the total playtime in ticks will be increased by 20 every second.
    * If this value is set to `100`, the total playtime in ticks will be increased by 100 every 5 seconds.
    * If a value &leq; `0` is given, it will default to the same as Paper.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>100</code></td><td><code>20</code></td><td><code>1</code></td><td><code>1</code></td></tr>
    </table>
    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>100</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td>Lower is more like vanilla<br>(<code>20</code> is fine though, <code>1</code> is normally unnecessary)</td></tr>
    </table>

24. The interval, given in ticks, at which to update whether one entity is within another entity's line of sight.<br>
  If a value &leq; `0` is given, it will default to the same as Paper.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>4</code></td><td><code>4</code></td><td><code>1</code></td><td><code>1</code></td></tr>
    </table>
    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>10</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>1</code></td></tr>
    </table>

25. Whether to use a [xor-shift](https://www.codeproject.com/Articles/9187/A-fast-equivalent-for-System-Random) random number generator instead of the Java's default.
26. Whether to use a xor-shift random generator for refilling lootables for the Paper `auto-replenish` feature.<br>
  This does not affect normal Minecraft lootable chests.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Paper behavior</i></td><td>- (players can't notice the difference anyway)</td></tr>
    </table>

27. Whether to use a xor-shift random generator for the speed boost of using a rocket while gliding.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla behavior</i></td><td><code>false</code></td></tr>
    </table>

28. Whether to use a xor-shift random generator for variation in entity activation durations.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td>-</td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    </table>

29. Whether to use a xor-shift random generator to generate trees with the Bukkit API (`World#generateTree`).

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Paper behavior</i></td><td><code>false</code></td></tr>
    </table>

30. Whether to use a xor-shift random generator for the chance of lightning strike.

    <table>
    <tr><td></td><td><b>Default</b></td><td></td><td></td></tr>
    <tr><td><b>Recommended&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Values for goals</b></td><td></td></tr>
    <tr><td><i>Optimization</i></td><td><code>true</code></td></tr>
    <tr><td><i>Paper behavior</i></td><td><code>false</code></td></tr>
    </table>
