# Globale Leaf Konfiguration

!!! info "Info"

    Diese YAML Konfiguration zeigt die standardmäßige Struktur der Konfigurationswerte der globalen Konfiguration von Leaf (==config/leaf-global.yml==)

    Diese Konfiguration basiert auf der neusten 1.21.1 Version von Leaf

    Klicke auf die Pfeile hinter den Konfigurationswerten um die entsprechende Beschreibung anzusehen

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
  # **Experimentelle Funktionen, die unter Umständen zu Datenverlust führen können!**
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
  # Dies könnte zu einer inkonsistenten Reihenfolge zukünftiger Kompositionsaufgaben führen.
  faster-structure-gen-future-sequencing: true #(28)!
  # Erfordert eine JVM, die RandomGenerator und LXM Generatoren unterstützt.
  # Manche JREs unterstützten dies nicht und werden abstürzen.
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
  # **Experimentelle Funktion, bitte melde jegliche Fehler!**
  smooth-teleport: false #(48)!
  # Dies sollte nur mit äußerster Vorsicht geändert werden!
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
    # Erhalte einen DSN Schlüssel bei https://sentry.io/
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
  # INFO: Bei dieser Option ist Kenntnis darüber erforderlich, was eingegeben werden soll und wie es funktioniert! Dies betrifft alle ItemStacks!
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

1. Dieser Abschnitt beinhaltet asynchrone Funktionen, die die Last auf dem Hauptthread (Server Thread) reduzieren sollen, indem Aufgaben asynchron bearbeitet werden.
2. Macht Entity-Tracking asynchron. Kann die Leistung deutlich verbessern, vor allem wenn viele Entities in kleinen Bereichen sind.<br>
  <br>
  __Empfohlener Wert: `true` (Setze `enabled` unten auf true)__

    !!! note "Achtung"

        Wenn Plugins wie Citizens vorhanden sind, die echte, NPCs vom Typ Spieler nutzen, muss `async-entity-tracker.compat-mode` unten für weitere Informationen beachtet werden.

3. Aktiviere den Kompatibilitätsmodus um mit Plugins wie Citizens oder anderen Plugins, die reale NPCs vom Typ Spieler nutzen, kompatibel zu sein.<br>
  Bei `true`, können Sichtbarkeitsprobleme von NPCs des Typ Spieler manchmal behoben werden.<br>
  <br>
  `compat-mode` sollte nur aktiviert werden, wenn tatsächlich Citizens oder andere Plugins, die reale NPCs vom Typ Spieler nutzen, vorhanden sind.<br>
  <br>
  Wie empfehlen trotzdem die Nutzung von Paket-basierten oder virtuellen Entity NPC Plugins für eine bessere Leistung, z.B. [ZNPC Plus](https://github.com/Pyrbu/ZNPCsPlus), [Adyeshach](https://github.com/TabooLib/Adyeshach), [Fancy NPC](https://modrinth.com/plugin/fancynpcs), oder andere. Dann kann `compat-mode` deaktiviert bleiben.
4. Die maximale Anzahl an Threads, die für das asynchrone Entity-Tracking genutzt werden.<br>
   Wenn dieser Wert `0` ist, werden automatisch 1/4 der Anzahl an CPU Kernen genutzt, allerdings niemals weniger als 1.<br>
  <br>
  __Empfohlener Wert: 1/2 der CPU Kerne__
5. Thread Keepalive Zeit. Threads ohne Aufgabe werden nach dieser Zeit beendet.<br>
  (Einheit: Sekunden)
6. Macht das Speichern von Spielerdaten asynchron.

    !!! warning "Warnung"

        Experimentelle Funktion, die in manchen Fällen zu Datenverlust führen kann!

7. Macht Mob-Pathfinding Berechnungen asynchron.<br>
  <br>
  __Empfohlener Wert: `true` (Setze `enabled` unten auf true)__
8. Die maximale Anzahl an Threads, die für das asynchrone Entity-Pathfinding genutzt werden.<br>
   Wenn dieser Wert `0` ist, werden automatisch 1/4 der Anzahl an CPU Kernen genutzt, allerdings niemals weniger als 1.<br>
  <br>
  __Empfohlener Wert: 1/3 der CPU Kerne__
9. Thread Keepalive Zeit. Threads ohne Aufgabe werden nach dieser Zeit beendet.<br>
  (Einheit: Sekunden)
10. Gibt an, ob asynchrones Mob-Spawning aktiviert sein soll.<br>
  Auf Servern mit vielen Entities, kann dies die Leistung um bis zu 15% steigern. Hierfür muss `per-player-mob-spawns` der Paper Konfiguration auf `true` gestellt sein.<br>
  Anmerkung: Hierdurch werden Mobs nicht wirklich asynchron gespawnt (Das wäre sehr unsicher). Hierdurch werden nur einige aufwändige Berechnungen ausgelagert, die für das Mob-Spawning erforderlich sind.<br>
  <br>
  __Empfohlener Wert: `true`__
11. Gibt an, ob der asynchrone Locator aktiviert sein soll.<br>
  Hierdurch wird das Lokalisieren von Strukturen auf andere Threads ausgelagert.<br>
  Aktuell verfügbar für:
    * `/locate` Befehl
    * Delfin Schatzsuche
    * Enderauge Festung Suche
  <br><br>
  __Empfohlener Wert: `true` (Setze `enabled` unten auf true)__
12. Die maximale Anzahl an Threads, die für den asynchronen Locator genutzt werden.<br>
   Wenn dieser Wert &leq; `0` ist, wird immer 1 Thread genutzt.<br>
  <br>
  __Empfohlener Wert: `1` oder `2`__
13. Thread Keepalive Zeit. Threads ohne Aufgabe werden nach dieser Zeit beendet.<br>
  (Einheit: Sekunden)



14. Dieser Abschnitt beinhaltet Performance-Einstellungen um unnötige Berechnungen zu reduzieren oder effizientere Methoden zu nutzen um den Server zu optimieren.
15. Gibt an, ob [virtuelle Threads](https://docs.oracle.com/en/java/javase/21/core/virtual-threads.html) ab JDK 21 für den Aync Chat Executer genutzt werden sollen.<br>
  <br>
  __Empfohlener Wert: `true`__
16. Gibt an, ob [virtuelle Threads](https://docs.oracle.com/en/java/javase/21/core/virtual-threads.html) ab JDK 21 für den CraftAsyncScheduler genutzt werden sollen. Dies kann die Leistung von Plugins verbessern, die den asynchronen Scheduler nutzen.<br>
  <br>
  __Empfohlener Wert: `true`__
17. Gibt an, ob ein Snapshot von TileEntity / BlockState erstellt werden soll, wenn diese empfangen werden.<br>
  <br>
  Manche Plugins könnten `getHolder` nutzen, um den Halter eines Inventars zu erhalten, der das holen des BlockStates involvierte.<br>
  Wenn es zum Beispiel sehr viele Trichter gibt und Plugins diese Methode aufrufen während sie auf manche Events hören (z.B. Trichter Events), ist es sehr aufwändig den BlockState neu zu erstellen und den ItemStack in häufigen Aufrufen zu parsen.<br>
  Siehe [API-to-get-a-BlockState-without-a-snapshot.patch#L6](https://github.com/PaperMC/Paper-archive/blob/b48403bd69f534ffd43fe2afb4e8e1f1ffa95fe1/patches/server/0160-API-to-get-a-BlockState-without-a-snapshot.patch#L6) von Paper für weitere Informationen.
    * Bei `true`, wird ein Snapshot (Kopie) des BlockStates jedes Mal erstellt, wenn ein Plugin die Methoden aufruft.
    * Bei `false`, wird der echte BlockState geholt beim Aufruf er Methoden, außer das Plugin gibt an, den Snapshot zu nutzen.
  <br><br>
  __Empfohlener Wert: `false` (Nur wenn der oben beschriebene Lag auftritt)__
18. Verlangsamt die *AI Zielauswahl* Berechnung, die jeden *inaktiven Tick* durchgeführt wird. Dies kann die Performance um ein paar Prozent verbessern, hat aber leichte Einflüsse auf das Gameplay.<br>
  <br>
  __Empfohlener Wert: `true`__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

19. Gibt an, ob Versuche eines Trichters, Items in einen vollen Container zu bewegen, verlangsamt werden sollen.<br>
  <br>
  __Empfohlener Wert: `true` (Setze `enabled` unten auf true)__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

20. Wie viele Ticks gewartet wird, bevor das nächste Mal versucht wird Items zu bewegen, wenn der Trichter verlangsamt ist.<br>
  Wenn der Wert &leq; `0` ist, ist dieses Feature deaktiviert.<br>
  <br>
  __Empfohlener Wert: `8`__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>8</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>0</code></td></tr>
    </table>

21. Gibt an, ob Updates für Itemdaten von Karten übersprungen werden sollen, wenn die Karte keinen Renderer hat.<br>
  Dies kann die Leistung verbessern, wenn Plugins genutzt werden, die mit Karten zu tun haben.<>br
  <br>
  __Empfohlener Wert: `true`__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

    !!! note "Achtung"

        Hierdurch könnten Vanilla Karten sich nicht mehr richtig aktuallisieren.

22. Gibt an, ob AI Ticks übersprungen werden sollen, falls das Entity *inaktiv* und *unaufmerksam*. Unaufmerksame Entities führen keine Aktionen bei sich selbst aus oder wenn mit ihnen interagiert wird.<br>
  <br>
  __Empfohlener Wert: `true`__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

23. Dieser Abschnitt ist für die Reduktion von unnötigen Paketen.
24. Gibt an, ob das unnötige Entity Bewegungspaket reduziert werden soll, welches an Spieler gesendet wird.<br>
  <br>
  __Empfohlener Wert: `true`__
25. Gibt an, ob optimierte Aktivierungsschienen genutzt werden sollen. Nutzt eine vollständig neu geschriebene Iterationslogik für Aktivierungsschienen, die bis zu 4x schneller sein kann.<br>
  <br>
  __Empfohlener Wert: `true`__
26. Gibt an, ob Minecart Ticking optimiert werden soll. Durch das Überspringen von Tick Kollisionen, werden aufwändige `getEntities()` Aufrufe und Bukkit Eventaufrufe reduziert.<br>
  Dadurch können große Mengen an gestapelten Minecarts besser gehandhabt werden, was nützlich für [Anarchy Server](https://minecraftservers.org/type/anarchy) ist.<br>
  <br>
  __Empfohlener Wert: `true`__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

27. WIe viele Ticks übersprungen werden sollen, bevor die nächste Minecart Kollision überprüft wird.<br>
  <br>
  __Empfohlener Wert: `30`__

28. Gibt an, ob eine schnellere Aufgabensequenzierung für das Generieren von Strukturen genutzt werden soll.

    !!! note "Achtung"

        Dadurch kann die Reihenfolge von zukünftigen Compose-Aufgaben inkonsistent werden.

29. Gibt an, ob der schnellere Zufallsgenerator genutzt werden soll.<br>
  Zufalls wird fast überall in Minecraft genutzt. Diese Einstellung kann eine gute Performanceverbesserung zur Folge haben.<br>
  <br>
  __Empfohlener Wert: `true` (Setze `enabled` unten auf true)__

    !!! note "Achtung"

        Erfordert eine JVM, die `RandomGenerator` und die LXM Generatoren unterstützt. Manche JREs unterstützen dies nicht und werden abstürzen.

30. Welcher Zufallsgenerator soll genutzt werden?<br>
  Verfügbare Zufallsgeneratoren können hier gefunden werden [Zufallsgeneratoren in Java](https://www.baeldung.com/java-17-random-number-generators#1-api-design-1).<br>
  <br>
  __Empfohlener Wert: `Xoroshiro128PlusPlus`__
31. Gibt an, ob der schnellere Zufallsgenerator für Weltgenerierung genutzt werden soll.<br>
    * Bei `true` werden `Random` Aufrufe, die mit Weltgenerierung zu tun haben, den schnelleren Zufallsgenerator nutzen, der oben in `random-generator` angegeben ist. Die Weltgenerierung wird sich leicht von Vanilla unterscheiden.
    * Bei `false` werden `Random` Aufrufe, die mit Weltgenerierung zu tun haben, den normalen Vanilla Generator nutzen.
  <br><br>
  __Empfohlener Wert: `true`__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

32. Gibt an, ob der Server eine Warnung beim Start ausgibt, wenn der schnellere Zufallsgenerator für Schleimchunk Generierung genutzt wird.
33. Gibt an, ob der Vanilla Generator für die Schleimchunk Generierung genutzt werden soll.<br>
  Wenn es bereits Schleimfarms oder andere Bauwerke, die Schleimchunks benötigen auf dem Server gibt, sollte dies aktiviert werden, da sonst der Standort der Schleimchunks verändert wird.<br>
  <br>
  __Empfohlener Wert:__ (Hängt vom Server ab, siehe `Werte für Ziele` unten.)

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>false</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>true</code></td></tr>
    </table>

34. Diese Werte geben in Ticks die maximale Lebensspanne eines Entites an (Wie eine Art TTL).<br>
  Wenn ein Entity in dieser Liste ist und länger als diese Zeit überlebt hat, wird es entfernt. 🛈<br>
  Wenn ein Wert `-1` ist, wird die Überprüfung für dieses Entity deaktiviert.<br>
  <br>
  __Empfohlene Werte:__

    | Entity             | Value |
    |--------------------|-------|
    | SNOWBALL           | 200   |
    | LLAMA_SPIT         | 150   |
    | DRAGON_FIREBALL    | 150   |
    | EGG                | 300   |
    | FIREBALL           | 600   |
    | SMALL_FIREBALL     | 400   |
    | WIND_CHARGE        | 200   |
    | BREEZE_WIND_CHARGE | 200   |
    | WITHER_SKULL       | 200   |

    > 🛈 = Die Zeit, die ein Entity lebt, wird nicht durch das Laden und Entladen eines Chunks zurückgesetzt.

35. Gibt an, ob das Ergebnis von Konversionen von *Minecraft EntityType* zu *Bukkit EntityType* zwischengespeichert werden soll. Dies gibt eine winzige Verbesserung.<br>
  <br>
  __Empfohlener Wert: `true`__
36. Dynamische Aktivierung von Mob AIs. Optimiert die AI von Entites um die Tick-Frequenz zu reduzieren, wenn sie weit von Spielern entfernt sind.<br>
  <br>
  __Empfohlener Wert: `true` (Setze `enabled` unten auf true)__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code> (oder siehe <code>dab.blacklisted-entities</code> unten für mehr)</td></tr>
    </table>

37. Gibt an, ob Entites im Wasser, die dort eigentlich nicht hingehören, von DAB beeinflusst werden sollen.<br>
  Falls `true`, könnte dies beheben, dass Entites im Wasser ertrinken, die weit vom Spieler entfernt sind. Dies behebt [Issue#58 von Pufferfish](https://github.com/pufferfish-gg/Pufferfish/issues/58).<br>
  <br>
  __Empfohlener Wert: `true`__
38. Dieser Wert gibt an, wie weit Entites vom Spieler entfernt sein müssen, um von DAB beeinflusst zu werden.<br>
  <br>
  __Empfohlener Wert: `8`__
39. Dieser Wert gibt an, wie oft in Ticks das Pathfinding und Verhalten von dem am weitesten entfernten Entity getickt wird. (Beachte: 20 Ticks = 1s).
40. Dieser Wert gibt an, wie stark die Entfernt die Tickfrequenz des Entites beeinflusst. `freq = (distanceToPlayer^2) / (2^value)`.
    * Wenn weit entfernte Entites __weniger__ häufig getickt werden sollen, nutze `7`.
    * Wenn weit entfernte Entites __häufiger__ getickt werden sollen, nutze `9`.
  <br><br>
  __Empfohlener Wert: `7`__
41. Eine Liste an Entites, die nicht von DAB beeinflusst werden.<br>
  <br>
  Mache Survival-Server haben Mobfarms, wie erfordern, dass Mobs ein Ziel haben. Diese Arten von "Pathfinding" Mobfarmen könnten durch DAB kaputt gehen. Dies kann behoben werden, indem entsprechende Mobs in diese DAB Blackliste eingetragen werden.<br>
  Wenn einige, bestimmte Mobfarms nicht funktionieren, die Mobs sich nicht bewegen und du nicht sicher bist, ob DAB der Grund ist, kannst du versuchen sie zu dieser Blackliste hinzuzufügen.<br>
  <br>
  Format: `[VILLAGER]` oder `[VILLAGER, ZOMBIFIED_PIGLIN]` (Alle Entity Typen finden sich hier: [Paper Javadoc](https://jd.papermc.io/paper/1.21.1/org/bukkit/entity/EntityType.html)).

    ??? note "Tiefgehendere Informationen gefällig?"

        Das Format von `dab.blacklisted-entities` akzeptiert alles, das eine gültige YAML Liste ist.<br>
        <br>
        Wenn nur ein Entity zur Blackliste hinzugefügt werden soll, sind diese Formate erlaubt:
        ```yaml
        dab:
          blacklisted-entities: [VILLAGER]
        ```
        oder
        ```yaml
        dab:
          blacklisted-entities:
            - VILLAGER
        ```
        Wenn mehrere Entites zur Blackliste hinzugefügt werden sollen, sind diese Formate erlaubt:
        ```yaml
        dab:
          blacklisted-entities: [VILLAGER, ZOMBIFIED_PIGLIN]
        ```
        oder
        ```yaml
        dab:
          blacklisted-entities:
            - VILLAGER
            - ZOMBIFIED_PIGLIN
        ```
        Der [YAML Checker](https://yamlchecker.org/) kann helfen, den Syntax oder die Konfiguration zu überprüfen.

42. Deaktiviert das Speichern von gezündetem TNT, wenn Chunks entladen werden.<br>
  Dies kann verhindern, dass Maschinen durch TNT explodieren, wenn der Spieler aus Versehen den Server verlässt oder der Chunk entladen wird denn der Spieler weit entfernt ist. Nützlich für Survival Server, die Maschinen mit TNT haben.<br>
  <br>
  __Empfohlener Wert: `true`__
43. Deaktiviert das Speichern von fallenden Blöcken (falling_sand), wenn Chunks entladen werden.<br>
  <br>
  __Empfohlener Wert: `true`__



44. Dieser Abschnitt beinhaltet Fehlerbehebungen für spezifische Probleme.
45. Gibt an, ob das Joinen auf den Server verboten werden soll, wenn der Server voll ist.<br>
  Bei `true`, sollten die Spieler die Permission `purpur.joinfullserver` erhalten, anstatt `PlayerLoginEvent#allow` zu nutzen, um Spielern das Joinen auf einen vollen Server zu erlauben.



46. Dieser Abschnitt beinhaltet Funktionen, die das Spielverhalten beeinflussen.
47. Gibt an, ob der Zusammenfügungsmechanismus von gedroppten Items von Spigot genutzt werden soll.
48. Gibt an, ob ein "smooth teleport" durchgeführt werden soll, wenn ein Spieler die Dimension wechselt.<br>
  Dies erfordert, dass die Ursprungs- und Zielwelt die gleiche logische Höhe haben.

    !!! warning "Warnung"

        Experimentelle Funktion, bitte melde jegliche Bugs!

49. Konfigurierbare maximale Stapelgröße von gedroppten Items.

    !!! warning "Warnung"

        Wir empfehlen diese Funktion __nicht__. Es wird daran gearbeitet und gibt bekannte Probleme<br>
        Möglicherweise wird die Funktion auf in Zukunft entfernt. Diese Option sollte mit __höchster Vorsicht__ benutzt werden!

50. Maximale Anzahl an gedroppten Items, die gestapelt werden sollen.
51. Maximale Anzahl an Items, die gedroppt werden sollen, wenn ein Container zerstört wird.
52. Dieser Abschnitt beinhaltet Optionen, um Verhalten bezüglich Rückstoß anzupassen.
53. Gibt an, ob Schneebälle Spieler zurückstoßen können.
54. Gibt an, ob Eier Spieler zurückstoßen können.
55. Gibt an, ob Spieler Zombies zurückstoßen können.
56. Gibt an, ob die "moved too quickly" / "moved wrongly" Überprüfungen von Spigot für Spieler und Fahrzeuge deaktiviert werden sollen.<br>
  Bei `true`, können sich Spieler oder ihre Fahrzeuge mit extremen Geschwindigkeiten bewegen.<br>
  <br>
  __Empfohlener Wert: `true`__
57. Die maximale Distanz über die ein Spieler mit einem Item interagieren darf.<br>
  <br>
  Manche [Anarchy Server](https://minecraftservers.org/type/anarchy) oder ähnliche Server könnten Spielern das Hacken / Cheaten erlauben. Wenn Spieler Endkristall-Cheats nutzen können sollen, die Paket-basiert sind (z.B. CEV Breaker, BedAura), sollte dieser Wert eventuell angepasst werden.<br>
  Es ist besser diesen Wert auf `10.0000001` zu setzen, damit die Hack-Module genutzt werden können.
  <br>
  Wenn der Wert `-1` ist, wird die Überprüfung der maximal erlaubten Distanz ein Item zu nutzen deaktiviert.<br>
  <br>
  __Empfohlener Wert: `10.0000001` (Für Anarchy Server)__

    !!! note "Achtung"

        Wenn der Wert `-1` ist, können Spieler manche Paket-basierte Cheats nutzen und außerdem den [Nocom Exploit](https://github.com/nerdsinspace/nocom-explanation)!



58. Dieser Abschnitt beinhaltet Funktionen, die mit dem Server Netzwerk zu tun haben.
59. This section contains features that provide extra protocol support for some QoL / Utility mods.<br>
  <br>
  The extra protocol support is only functional if there is corresponding client-side mod installed. It means if a specific protocol support is enabled, and a player installed that mod on client, they can get the additional features described in each config below. But for players who have no corresponding mod installed, then everything is the same as before.

    !!! note "Achtung"

        The protocol support may cause incompatibility with the [ViaVersion](https://modrinth.com/plugin/viaversion).<br>
        We recommend players to use client that has same version with the server core and install latest corresponding mod, otherwise they may unable to join the server.

60. Whether to enable [Jade](https://modrinth.com/mod/jade) protocol support.<br>
  If `true`, player who has Jade mod installed, can display item information inside the storage container, progress of furnace, brewing stand, foods on the campfire, bee data in beehive, and more vanilla-friendly features.
61. Whether to enable [AppleSkin](https://modrinth.com/mod/appleskin) protocol support.<br>
  If `true`, player who has AppleSkin mod installed, can display the accurate saturation / exhaustion values on the client.
62. Whether to enable [AsteorBar](https://modrinth.com/mod/asteorbar) protocol support.<br>
  If `true`, player who has AsteorBar mod installed, can display the accurate saturation / exhaustion values on the client.
63. Whether to enable [ChatImage](https://modrinth.com/mod/chatimage) protocol support.<br>
  If `true`, player who has ChatImage mod installed, can see the image sent by others using CICode format.
64. Whether to enable [XaeroMap](https://modrinth.com/mod/xaeros-minimap) protocol support.<br>
  If `true`, player who has Xaero's MiniMap mod or Xaero's WorldMap mod installed, can store players' coordinate points and death points based on server's `protocol-support.xaero-map-server-id` below, to prevent points from been deleted / refreshed if server name or IP address changed.
65. Numeric id for XaeroMap to identify the server. This will generate randomly on first start.
66. Whether to enable [Syncmatica](https://modrinth.com/mod/syncmatica) protocol support.<br>
  If `true`, player who has Syncmatica mod installed, can upload their [Litematica](https://modrinth.com/mod/litematica) schematics files or download shared schematics files from the server. Every player with Syncmatica mod installed can access shared schematics uploaded by others.
67. Whether to enable maximum file size limit for each shared schematics file of Litematica mod.
68. Maximum file size, in bytes, for each shared schematics file uploading to server. (40,000,000 bytes ≈ 38 MB)
69. Whether to enable chat message signature which introduced since Minecraft 1.19.1.<br>
  If `false`, players' chat messages become unable to report, and the insecure warning popup when player joined the server will be disabled.<br>
  <br>
  __Empfohlener Wert: `false`__



70. This section contains some miscellaneous features.
71. Unknown command message, will send to player if they execute an unknown command.<br>
  The message needs to use [MiniMessage](https://docs.advntr.dev/minimessage/format) format.<br>
  If set message to `default`or leave the default value, the vanilla unknown command message will be used.<br>
  <br>
  Available placeholders:
    * __`<detail>`__ - the detailed information of the unknown command.

    !!! note "API / Plugin Friendly"

        This feature is API / plugin friendly.
        It means that this message can be overrided by plugins using `UnknownCommandEvent#message` or `UnknownCommandEvent#setMessage`.

72. Server brand name that shows in F3 menu and server MOTD.
73. Server GUI window name, if you launched server without adding `--nogui` option in the startup flag.
74. [Sentry](https://sentry.io/welcome/) is an application monitor service for improved error logging, tracing. Helping the server dev team to maintain better.<br>
  <br>
  After enabled Sentry integration for your server, you don't need to audit long logs to find errors manually. Sentry can collect errors happened in your server, enable you to track errors on Sentry's web panel and help you to locate and fix them easier and faster.<br>
  <br>
  See __[How to Setup Sentry](../../how-to/setup-sentry.md)__ to know how to set up and get the DSN key for `sentry.dsn` below.<br>
75. The DSN key of your Sentry.<br>
  If an empty value `''` is given, the Sentry will be disabled.
76. Logs with a level higher than or equal to this level will be recorded.
77. Only to log with a Throwable will be recorded after enabling this. 
78. Whether to use secure seed.<br>
  All ores and structures are generated with 1024-bit seed instead of using 64-bit seed in vanilla, made seed cracker become impossible.<br>
  If used in the existing world, then the secure seed will only apply to new generating chunks.<br>
  <br>
  __Empfohlener Wert: `true` (set `enabled` below to true)__

    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

79. Whether to remove vanilla's username check to allow __all characters__ as username, including Chinese, etc. (It's only useful for offline servers).<br>
  If `true`, players are allowed to use non-English name to join the server.
80. Whether player can enter backend server via proxy, without the backend server to enable bungeecord mode in `spigot.yml`.
81. Whether the server prints warning when players tried to edit the sign that they are not allowed to edit.<br>
  Enable this to prevent console spam in some cases.<br>
  <br>
  __Empfohlener Wert: `true`__

82. Linear is a region file format that uses [ZSTD compression](https://facebook.github.io/zstd/) instead of ZLIB in vanilla Minecraft. This format saves about ~50% of disk space.<br>
  To use Linear region format, make sure you __Read [Linear Documentation](https://github.com/xymb-endcrystalme/LinearRegionFileFormatTools)__, and have done all steps required, then change `region-format-settings.region-format` below to `LINEAR`.

    !!! warning "Warnung"

        Experimental feature, there is potential risk to lose chunk data. Backup your server before switching to Linear.<br>
        Also, we do not recommend using Linear, since vanilla's ANVIL format (.mca) is enough. Leaf uses the refactored version of the Linear flush system, which is safer but slower to save chunks to make data lost less possible. However this change is worth it, data is invaluable.

83. Available region formats: `"MCA"`, `"LINEAR"`.
84. The compression level for Linear region format file.
85. Whether to throw error to crash the server when unknown region format extension is detected.
86. The flush interval in seconds for Linear region format file data.
87. Lag compensation, which could ensure the basic game experience for players when server is lagging or low TPS situation.<br>
  <br>
  __Empfohlener Wert: `true` (set `enabled` below to true)__
88. Whether to enable lag compensation for water flowing.<br>
  <br>
  __Empfohlener Wert: `true`__
89. Whether to enable lag compensation for lava flowing.<br>
  <br>
  __Empfohlener Wert: `true`__
90. Whether to include 5-second TPS in the result of API `Bukkit#getTPS` and `Server#getTPS`.<br>
    * If `true`, you can use `getTPS` method to get a TPS long array with 4 elements (`5s, 1m, 5m, 15m`).
    * If `false`, you can use `getTPS` method to get a TPS long array with 3 elements (`1m, 5m, 15m`).

    ??? note "Want to Go Deeper?"

        If you are using Gale API or Leaf API for your plugins. Or runinng on Leaf and use reflection to get TPS, you can use `Bukkit#getTPSIncluding5SecondAverage`, to get the TPS array including 5-seconds TPS (`5s, 1m, 5m, 15m`).<br>
        Also, you can use `Bukkit#get5SecondTPSAverage` to get the average value of 5-seconds TPS in `double`.

91. Controls whether specified component information is sent to clients. This may break resource packs and client mods that rely on this information. It needs a component type list, incorrect things will not work.<br>
  For example, you can fill it with `["custom_data"]` to hide components of *CUSTOM_DATA*. Also, it can avoid some frequent client animations.

    !!! note "Achtung"

        You must know what you're filling in and how it works! It handles all item stacks!

92. Connection message, broadcasts to all online players, when they join or quit the server.<br>
  The message needs to use [MiniMessage](https://docs.advntr.dev/minimessage/format) format.<br>
  If set message to `default` or leave the default value, the vanilla join / quit message will be used.<br>
  <br>
  Available placeholders:
    * __`%player_name%`__ - player name.
    * __`%player_displayname%`__ - player display name.

    !!! note "API / Plugin Friendly"

        This feature is API / plugin friendly.
        It means that the connection message can be overrided by plugins using `PlayerJoinEvent` or `PlayerQuitEvent`.

93. The join message of the player.
94. The quit message of the player.
95. Whether to cache the player profile result when they joined server.<br>
  It's useful if Mojang's authentication server is down.
96. The timeout of the player profile cache.<br>
  (Unit: minutes)<br>
  If the given timeout is exceeded, it will send another request to Mojang's authentication server to get profile data on player's next join.<br>
