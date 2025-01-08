# Weltspezifische Gale Konfiguration

!!! info "Info"

    Diese YAML Konfiguration zeigt die standardmäßige Struktur der Konfigurationswerte der weltspezifischen Konfiguration von Gale (==config/gale-world-defaults.yml==)

    Diese Konfiguration basiert auf der neusten 1.21.1 Version von Leaf

    Klicke auf die Pfeile hinter den Konfigurationswerten um die entsprechende Beschreibung anzusehen

```yaml title="gale-world-defaults.yml"
# This is the world defaults configuration file for Gale.
# As you can see, there's a lot to configure. Some options may impact gameplay, so use
# with caution, and make sure you know what each option does before configuring.
# 
# If you need help with the configuration or have any questions related to Gale,
# join us in our Discord, or check the GitHub Wiki pages.
# 
# Configuration options here apply to all worlds, unless you specify overrides inside
# the world-specific config file inside each world folder.
# 
# Wiki: https://github.com/GaleMC/Gale/wiki
# Discord: https://discord.gg/gwezNT8c24

_version: 1
gameplay-mechanics:
  arrow-movement-resets-despawn-counter: false #(1)!
  entities-can-random-stroll-into-non-ticking-chunks: true #(2)!
  entity-wake-up-duration-ratio-standard-deviation: 0.2 #(3)!
  fixes:
    broadcast-crit-animations-as-the-entity-being-critted: false #(4)!
    keep-mooshroom-rotation-after-shearing: true #(5)!
    mc-110386: true #(6)!
    mc-121706: false #(7)!
    mc-238526: false #(8)!
    mc-31819: true #(9)!
  hide-flames-on-entities-with-fire-resistance: false #(10)!
  technical:
    load-portal-destination-chunk-before-entity-teleport: false #(11)!
  try-respawn-ender-dragon-after-end-crystal-place: true #(12)!
small-optimizations:
  load-chunks: #(13)!
    to-activate-climbing-entities: false #(14)!
    to-spawn-phantoms: false #(15)!
  max-projectile-chunk-loads: #(16)!
    per-projectile:
      max: 10 #(17)!
      remove-from-world-after-reach-limit: false #(18)!
      reset-movement-after-reach-limit: false #(19)!
    per-tick: 10 #(20)!
  reduced-intervals:
    acquire-poi-for-stuck-entity: 60 #(21)!
    check-nearby-item:
      hopper: #(22)!
        interval: 1 #(23)!
        minecart:
          interval: 1 #(24)!
          temporary-immunity: #(25)!
            check-for-minecart-near-item-interval: 20 #(26)!
            check-for-minecart-near-item-while-active: false #(27)!
            check-for-minecart-near-item-while-inactive: true #(28)!
            duration: 100 #(29)!
            max-item-horizontal-distance: 24.0 #(30)!
            max-item-vertical-distance: 4.0 #(31)!
            nearby-item-max-age: 1200 #(32)!
    check-stuck-in-wall: 10 #(33)!
    villager-item-repickup: 100 #(34)!
  save-fireworks: true #(35)!
  use-optimized-sheep-offspring-color: true #(36)!
```

1. Gibt an, ob der [Despawn Zähler](https://minecraft.wiki/w/Mob_spawning#Despawning) von Pfeilen neu startet, wenn der Pfeil zu fallen beginnt (z.B. Wenn der Block zerstört wird, in dem der Pfeil steckt).

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-<br></td><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>false</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>true</code></td></tr>
    </table>

2. Gibt an, ob Entities, die zufällig umherlaufen auch in nicht-getickte Chunks laufen können.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-<br></td><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>true</code></td></tr>
    </table>

3. Wenn dieser Wert > `0` ist, wird das Aufwecken inaktiver Entities zeitlich verteilt, anstatt alle auf einmal aufzuwecken.<br>
  Dadurch verhalten sich Entities natürlicher.<br>
  <br>
  Dieser Wert ist der [Variationskoeffizient](https://de.wikipedia.org/wiki/Variationskoeffizient) bzw. `σ / μ` (Das Verhältnis der Standardabweichung und dem Mittelwert) der Inaktivitätsdauer.<br>
  <br>
  In anderen Worten ist diese Option der Wert `σ`, sodass the reguläre Inaktivitätsdauer mit dem Faktor `normal_distribution(μ = 1, σ)` multipliziert wird.<br>
  <br>
  Wenn der Wert &leq; `0` ist, ist die Variation deaktiviert.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>0.2</code><br></td><td><code>0.2</code></td><td><code>0.0</code></td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Paper Verhalten</i></td><td><code>0.0</code></td></tr>
    </table>

4. Gibt an, ob die Animation von kritischen Treffern durch das Entity gezeigt werden soll, das den kritischen Treffer erleidet.<br>
  <br>
  Dies beeinflusst nicht, wo die Animation gezeigt wird: Sie wird immer bei dem Entity gezeigt, das den kritischen Treffer erleidet.<br>
  Allerdings wird normalerweise (Wenn die Einstellung auf `false` gestellt ist) die Animation durch den Spieler gezeigt, der den kritischen Treffer landet. Dadurch kann jemand, der den Spieler nicht sehen kann, auch nicht die Animation sehen.<br>
  <br>
  Wenn die Einstellung auf `true` ist, wird die Animation durch das Entity gezeigt, das den kritischen Treffer erleidet. Dadurch kann jeder die Animation sehen, der auch das Entity sehen kann. 

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-<br></td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

5. Gibt an, ob Pilzkühe ihre Rotation behalten sollen, nachdem die geschoren werden. (Behebt einen Teil von [MC-88967](https://bugs.mojang.com/browse/MC-88967)).

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-<br></td><td><code>true</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

6. Gibt an, ob [MC-110386](https://bugs.mojang.com/browse/MC-110386) gefixt werden soll.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>

7. Gibt an, ob [MC-121706](https://bugs.mojang.com/browse/MC-121706) gefixt werden soll.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>

8. Gibt an, ob [MC-238526](https://bugs.mojang.com/browse/MC-238526) gefixt werden soll.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-</td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>

9. Gibt an, ob [MC-31819](https://bugs.mojang.com/browse/MC-31819) gefixt werden soll.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>

10. Gibt an, ob Flammen von Entities versteckt werden sollen, die Brennen und gleichzeitig Feuerresistenz haben.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-<br></td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

11. Gibt an, ob Chunks vollständig geraden werden sollen, bevor ein Entity teleportiert wird, wenn es ein Portal betritt.<br>
  Dies zwingt den ganzen Server zu warten, bis der Chunk geladen ist.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>false</code><br></td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>false</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

12. Gibt an, ob versucht werden soll den Enderdrache zu respawnen, nachdem ein Endkristall an der richtigen Position am Portal platziert wurde.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-<br></td><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>true</code></td></tr>
    </table>

13. Gibt an, ob chunks in bestimmten Fällen geladen werden sollen.
14. Gibt an, ob chunks geladen werden sollen, um kletternde Entities zu laden.<br>
  <br>
  In Paper erhalten Entites wie Zombies die klettern (z.B. eine Leiter heruntergehen) eine Priorität um aktiviert zu werden.<br>
  Um zu überprüfen, ob ein Entity klettert, muss der Block, in dem es sich befindet, überprüft werden.<br>
  Dadurch kann der ganze Server kurzzeitig stehenbleiben, um dem Chunk zu laden, wenn ein Entity genau an einer Chunkgrenze mit klettern beginnt.<br>
  <br>
  Wenn dieser Wert `false` ist, wird dies verhindert: Der Server wird nicht überprüfen ob Entities klettern, die in ungeladenen Chunks sind. Dies verhindert unnötige Server Hänger.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>true</code></td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>false</code></td></tr>
    <tr><td><i>Paper Verhalten</i></td><td><code>true</code></td></tr>
    </table>

15. Gibt an, ob chunks geladen werden sollen um Phantome zu spawnen.<br>
  Wenn dieser Wert `false` ist, wird nichts passieren, wenn der Server versucht ein Phantom in einem ungeladenen Chunk zu spawnen.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>false</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>true</code></td></tr>
    </table>

16. Einstellungen für das Laden von Chunks für Projektile (z.B. wenn ein Pfeil, Dreizack oder eine Enderperle einen ungeladenen Chunk betritt).
17. Die maximale Anzahl an Chunks, die synchron von einem Projektil während seiner Lebenszeit geladen werden können.<br>
  Wenn ein Wert < `0` angegeben ist, wird dies deaktiviert: Die Anzahl an Chunks, die ein Projektil laden kann, ist unbegrenzt.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>10</code></td><td><code>10</code></td><td><code>-1</code></td><td><code>-1</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>10</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>-1</code></td></tr>
    </table>

18. Gibt an ob Projektile komplett entfernt werden sollen, die den `max` Schwellenwert (siehe oben) überschreiben.<br>
  <br>
  Projektile aus der Welt zu entfernen ist riskant, da hierdurch auch wertvolle Projektile wie Dreizäcke entfernt werden können. Daher wird ein Wert von `true` nicht empfohlen.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code> In extremen Fällen, dies ist riskant</td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

19. Gibt an, ob die planare Geschwindigkeit von Projektilen, die den `max` Schwellenwert (siehe oben) überschreiben, auf `0` gesetzte werden soll, damit diese keine weiteren Chunkgrenzen erreichen.<br>
  <br>
  Dies hat keine Auswirkung wenn `remove-from-world-after-reach-limit` (siehe oben) `true` ist.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-</td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

20. Die maximale Anzahl an Chunks, die in einer Welt in einem Tick von allen Projektilen synchron geladen werden können.<br>
  <br>
    Wenn ein Wert < `0` gesetzt ist, wird dies deaktiviert: Die Anzahl an Chunks, die Projektile pro Tick laden können ist unbegrenzt.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>10</code></td><td><code>10</code></td><td><code>-1</code></td><td><code>-1</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>2</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>-1</code></td></tr>
    </table>

21. Das zusätzliche Intervall (zusätzlich zum regulären Intervall), angegeben in Ticks, das für Entitäten gilt, die feststecken (z. B. in einem Fahrzeug), um zu versuchen, einen POI (wie einen Dorfbewohner-Arbeitsblock) zu erwerben.<br>
  Wenn sie sich während dieser Zeit befreien, können sie sofort einen neuen POI erwerben.<br>
  Wenn dieser Wert z.B. auf `100` gesetzt ist, versuchen Entities, die feststecken, alle 5 Sekunden einen POI zu finden.<br>
  <br>
  Wenn ein Wert < `0` angegeben wird, ist das Verhalten gleich wie bei Paper.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>60</code></td><td><code>60</code></td><td><code>200</code></td><td><code>0</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>200</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>0</code></td></tr>
    </table>

22. Frequenz, mit der Trichter nach Items zum Aufheben suchen.<br>
  Dies beeinflusst nur das Aufheben von Items in der Welt (z.B. gedroppte Items). Dies beeinflusst nicht das Extrahieren von Items aus einer Truhe oder anderen Blöcken mit Items darin.

23. Frequenz in Ticks, mit der Trichter nach Items zum Aufheben suchen.<br>
  Wenn dieser Wert zum Beispiel `20` ist, suchen Trichter jede Sekunde nach Items über ihnen..<br>
  <br>
  If a value &leq; `0` is given, it will default to the same as Paper.
  Wenn der Wert &leq; `0` ist, ist das Verhalten wie bei Paper.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>20</code></td><td><code>1</code></td><td><code>1</code></td><td><code>1</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>50</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>1</code></td></tr>
    </table>

24. Gleich wie die obige `interval` Einstellung, aber für Loren mit Trichtern.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>20</code></td><td><code>1</code></td><td><code>1</code></td><td><code>1</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>20</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>1</code></td></tr>
    </table>

25. Loren mit Trichtern können durch die obige `interval` Einstellung kurzzeitig immun werden.<br>
  Während eine Lore immun ist, kann sie jeden Tick nach Items suchen.
26. Gibt an, wie oft in Ticks nach Loren mit Trichtern in der Nähe von Items gesucht werden soll, um den Loren kurzzeitige Immunität von der `interval` Einstellung zu geben.<br>
  If a value &leq; `0` is given, it behaves like `1`.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>20</code></td><td><code>20</code></td><td>-</td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>20</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td>- (Für Vanilla Verhalten muss <code>interval</code> auf 1 gestellt sein)</td></tr>
    </table>

27. Gibt an, ob nach __aktiven__ Loren mit Trichtern in der Nähe von Items gesucht werden soll, um den Loren kurzzeitige Immunität von der `interval` Einstellung zu geben.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code><br>(Es wird stark davon abgeraten, diesen Wert auf <code>false</code> zu stellen)</td><td><code>false</code></td><td>-</td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>false</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td>- (Für Vanilla Verhalten muss <code>interval</code> auf 1 gestellt sein)</td></tr>
    </table>

27. Gibt an, ob nach __inaktiven__ Loren mit Trichtern in der Nähe von Items gesucht werden soll, um den Loren kurzzeitige Immunität von der `interval` Einstellung zu geben.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code><br>(Es wird stark davon abgeraten, diesen Wert auf <code>false</code> zu stellen)</td><td><code>true</code></td><td>-</td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td>- (Für Vanilla Verhalten muss <code>interval</code> auf 1 gestellt sein)</td></tr>
    </table>

29. Die Dauer in Ticks, für die Loren mit Trichtern temporär von der `interval` Einstellung immun werden.<br>
  Wenn ein Wert &leq; `0` gesetzt ist, werden Loren mit Trichtern niemals immun von der `interval` Einstellung.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>100</code></td><td><code>100</code></td><td>-</td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>75</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td>- (Für Vanilla Verhalten muss <code>interval</code> auf 1 gestellt sein)</td></tr>
    </table>

30. Die maximale horizontale Distanz, die ein gedropptes Item von einer Lore mit Trichter entfernt sein kann, um der Lore temporäre Immunität zu der `interval` zu geben.<br>
  Wenn ein Wert < `0` gesetzt ist, werden Loren mit Trichtern niemals immun von der `interval` Einstellung.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>24.0</code><br></td><td><code>24.0</code></td><td>-</td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>24.0</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td>- (Für Vanilla Verhalten muss <code>interval</code> auf 1 gestellt sein)</td></tr>
    </table>

31. Genau wie `max-item-horizontal-distance`, aber für die maximale vertikale Distanz.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>4.0</code><br></td><td><code>4.0</code></td><td>-</td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>4.0</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td>- (Für Vanilla Verhalten muss <code>interval</code> auf 1 gestellt sein)</td></tr>
    </table>

32. Items mit einem Alter (in Ticks) höher als dieser Wert sorgen nicht dafür, dass Loren mit Trichtern temporär immun von der `interval` Einstellung werden können.<br>
  Wenn der Wert &leq; `0` ist, gibt es kein minimales Alter: Alle Items können Loren mit Trichtern temporär immun von der `interval` Einstellung machen.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>1200</code></td><td><code>1200</code></td><td>-</td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>600</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td>- (Für Vanilla Verhalten muss <code>interval</code> auf 1 gestellt sein)</td></tr>
    </table>

33. Das Interval in Ticks mit wem überprüft wird, ob ein Entity in einer Wand feststeckt, um Erstickungsschaden zu erteilen.<br>
  <br>
  Da es nach dem Erteilen von Schaden ein kurzes Zeitfenster (Aktuell etwa 1 Sekunde) gibt, in dem die Entites immun sind, bleibt es beinnahe unbemerkt, diese Überprüfung zur jede Sekunde durchzuführen.<br>
  <br>
  Zum Beispiel:
    * Wenn dieser Wert `10` ist, überprüfen Entites alle ½ Sekunden, ob sie feststecken.
    * Wenn dieser Wert &leq; `0` ist, ist das Verhalten wie bei Paper.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>10</code></td><td><code>10</code></td><td><code>1</code></td><td><code>1</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>10</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>1</code></td></tr>
    </table>

34. Die Mindestverzögerung in Ticks, bis von Dorfbewohnern fallengelassene Items von (anderen) Entites aufgesammelt werden können.
    * Verhindert, dass Dorfbewohner gefarmte Items wieder aufsammeln, bevor Trichter das können. Ansonsten könnte es Probleme durch die `check-nearby-item.hopper` Einstellung geben.
    * Reduziert Lag von Dorfbewohner, die ständig Items werfen, wenn deren Inventare voll sind.
  <br><br>
  Zum Beispiel:
    * Wenn dieser Wert `100` ist, können Entites die Items von Dorfbewohnern nach 5 Sekunden aufsammeln.
    * Wenn der Wert < `0` ist, wird der Vanilla Standardwert genutzt (Aktuell `10` ticks oder ½ Sekunden).

      <table>
      <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
      <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
      <tr><td><code>100</code></td><td><code>100</code></td><td><code>-1</code></td><td><code>-1</code></td></tr>
      </table>
      <table>
      <tr><td><b>Werte für Ziele</b></td><td></td></tr>
      <tr><td><i>Optimierung</i></td><td><code>100</code></td></tr>
      <tr><td><i>Vanilla Verhalten</i></td><td><code>-1</code></td></tr>
      </table>

35. Gibt an, ob Feuerwerk gespeichert wird, wenn ein Chunk gespeichert wird.<br>
  Feuerwerk kann verbuggt werden und nicht zünden und eine automatische Redstone-Schaltung kann leicht einen ganzen Chunk damit füllen.<br>
  Wenn dieser Wert `true` ist, wird jegliches Feuerwerk beim Entladen des Chunks entfernt, um dieses Problem zu verhindern.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-<br>(See <i>Optimierung</i> below)</td><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><ul><li>Normalerweise: - (Ist egal)<li>Wenn Spieler vorhaben den Server zu ärgern: <code>false</code></li></ul></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>true</code></td></tr>
    </table>

36. Gibt an. ob eine (viel) schnellere Methode genutzt werden soll, um die Farbe eines neuen Babyschafs zu bestimmen.<br>
  Die Farbe wird auf die gleiche Weise wie in Vanilla bestimmt.<br>
  <br>
  Allerdings ist es in Vanilla möglich, die neue Farbe durch Datapacks zu ändern, die das Crafting-Rezept für das Kombinieren von Farbstoffen ändern.<br>
  Wenn dieser Wert `true` ist, werden solche Änderungen an Crafting-Rezepten ignoriert.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>
