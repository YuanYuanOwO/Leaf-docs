# Globale Gale Konfiguration

!!! info "Info"

    Diese YAML Konfiguration zeigt die standardmäßige Struktur der Konfigurationswerte der globalen Konfiguration von Gale (==config/gale-global.yml==)

    Diese Konfiguration basiert auf der neusten 1.21.1 Version von Leaf

    Klicke auf die Pfeile hinter den Konfigurationswerten um die entsprechende Beschreibung anzusehen

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

1. Gibt an, ob Bücher beschreibbar sein sollen.<br>
  Wenn diese Option auf `false` gesetzt wird, können Spieler mit der Permission `gale.writebooks` (Standard: `op`) trotzdem Bücher nutzen.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>true</code></td></tr>
    </table>

2. Gibt an, ob bestimmte Texte und Ereignisse in der Konsole und in den Logdateien geloggt werden sollen.
3. Wenn ein Spieler ein leeres Nachrichtenpaket sendet.<br>
  (Dies ist harmlos und passiert meistens, wenn der Client des Spielers veraltet ist)

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>true</code></td></tr>
    </table>

4. Wenn das Nachrichtenpaket eines Spielers abgelaufen ist.<br>
  (Dies ist harmlos und passiert meistens, wenn ein Bit des Clients des Spielers nicht mehr synchron ist)

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>true</code></td></tr>
    </table>

5. Gibt an, ob ein [NOT SECURE] Marker vor unsignierte Chatpakete angefügt werden soll.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

6. Wenn Spielerdaten geladen werden und Advancements beinhalten, die nicht mehr existieren.<br>
  (Dies ist harmlos und passiert meistens, wenn der Server auf eine neue Minecraft Version aktualisiert wurde)

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

7. Das Logging-Level für Fehler, wenn *ungültige Pool-Elemente* in den Weltdaten auftreten.<br>
  <br>
  *Ungültige Pool-Elemente* sind Teil von generierten Strukturen (wie Minenschachte), die korrupt sind oder nicht richtig von älteren Versionen übernommen wurden.<br>
  <br>
  Diese Fehler sind sehr groß und treten häufig auf alten Servern auf, die zwischen Minecraft versionen wechseln.<br>
  <br>
  Die Fehler sind meistens nutzlos: Man kann nichts dagegen tun.<br>
  <br>
  Gültige Werte sind: `"none"`, `"info"`, `"warn"` und `"error"`.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>"none"</code> 🛈</td><td><code>"info"</code></td><td><code>"error"</code></td><td><code>"error"</code></td></tr>
    </table>

    > 🛈 = Der Standardwert ist `"info"` um zu verhindern, dass Fehler nicht gesehen werden, aber der empfohlene Wert ist `"none"` weil die Fehler meistens nutzlos und sowieso nicht lösbar sind.

8. Wenn Spielerdaten geladen werden und Statistiken beinhalten, die nicht mehr existieren.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

9. Wenn ein sehr altes Bukkit Plugin geladen wird

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>true</code></td></tr>
    </table>


10. Wenn ein Spieler kein gültiges Profil während dem Login gesendet hat.<br>
  (Dies bedeutet meistens, dass ein Hacker versucht die Join-Kapazität des Servers zu überlasten)

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

11. Gibt an, ob die Koordinaten eines Spielers in der Join-Nachricht in der Konsole enthalten sein soll.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

12. Wenn der Plugin Library-Loader mit dem Download der Libraries beginnt.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

13. Wenn der Plugin Library-Loader mit dem Download einer Library fertig ist.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

14. Wenn der Plugin Library-Loader mit dem Laden der Libraries für ein Plugin beginnt.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

15. Wenn ein Spieler versucht, einen Block zu platzieren, der *sehr* weit entfernt ist.<br>
  (Dies bedeutet meistens, dass ein Hacker versucht, Informationen über die Standorte anderer Spieler zu erhalten oder einen Hack Client nutzt)

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>

16. Wenn Spielerdaten geladen werden und Rezeptbuch-Rezepte beinhaltet, die nicht mehr existieren.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>true</code></td></tr>
    </table>

17. Gibt an, ob veraltete Strukturdaten ignoriert werden sollen, für die der NBT Tag Parser aus irgendeinem Grund null zurückgegeben hat.
    * Bei `true` wird in diesem Fall keine Warnung ausgegeben.
    * Bei `false` wird in diesem Fall eine Exception geworfen und in der Konsole geworfen.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code> 🛈</td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>false</code></td></tr>
    </table>

    > 🛈 = Der Standardwert ist `"info"` um zu verhindern, dass Fehler nicht gesehen werden, aber der empfohlene Wert ist `"none"` weil die Fehler meistens nutzlos und sowieso nicht lösbar sind.

18. Gibt an, ob Keepalive-Pakete häufiger als in Vanilla gesendet werden sollen
    * Bei `true` wird ein Keepalive-Paket jedem Client jede Sekunde gesendet und diese werden nicht gekickt, solange sie innerhalb von 30 Sekunden mindestens einmal antworten.
    * Bei `false` wird ein Keepalive-Paket jedem Client alle 15 Sekunden gesendet und werden gekickt, falls diese nicht innerhalb von 30 Sekunden antworten.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td>- (Dies hat keinen Einfluss auf das Gameplay)</td></tr>
    </table>

19. Gibt an, ob der Oversleep-Anteil der letzten Tickzeit im `/tps` Command enthalten sein soll.<br>
  Diese Option wird ignoriert, wenn `enabled` auf `false` gestellt ist.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-</td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Paper Verhalten</i></td><td>-</td></tr>
    </table>

20. Gibt an, ob die Zeit, die der letzte Tick gedauert hat, im `/tps` Command enthalten sein soll.<br>
  Die Zeit des letzten Ticks ist meistens nicht sehr nützlich, das es sich nur um einen einzelnen Tick handelt.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td><td><code>false</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Paper Verhalten</i></td><td><code>false</code></td></tr>
    </table>

21. Die maximale Zeit in Ticks, die ein Login Vorgang eines Premium-Accounts dauern kann.
    * Wenn die Zeit abläuft, wird die Verbindung geschlossen.
    * Wenn ein Wert &leq; `0` gesetzt wird, wird der Vanilla-Wert genutzt, der aktuell bei `600` Ticks (30 Sekunden) liegt.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-</td><td><code>-1</code></td><td><code>-1</code></td><td><code>-1</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>-1</code></td></tr>
    </table>

22. Gibt an, ob die Reihenfolge der Chatnachrichten verifiziert werden soll.
    * Bei `true` wird ein Spieler gekickt, wenn er ein Chat-Paket senden sollte, das nicht in der korrekten Reihenfolge entspricht.
    * Bei `false` findet keine Überprüfung statt und Spieler werden nicht gekickt.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td>-</td><td><code>true</code></td><td><code>true</code></td><td><code>true</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td>-</td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>true</code></td></tr>
    </table>

23. Das Interval in Ticks, in welchem die zeitbasierten Statistiken, wie Spielzeit oder Zeit seit dem letzten Tod erhöht werden sollen.<br>
  Das Ändern dieses Werten ändert nicht die Geschwindigkeit, mit der Statistiken von Vanilla erhöht werden.<br>
  <br>
  Zum Beispiel:
    * Wenn dieser Wert `20` beträgt, wird die Spielzeit in Ticks jede Sekunde um 20 erhöht.
    * Wenn dieser Wert `100` beträgt, wird die Spielzeit in Ticks alle 5 Sekunden um 100 erhöht.
    * Wenn ein Wert &leq; `0` gesetzt ist, ist der Wert gleich wie bei Paper.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>100</code></td><td><code>20</code></td><td><code>1</code></td><td><code>1</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>100</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td>Geringere Werte sind mehr wie Vanilla<br>(<code>20</code> ist aber auch in Ordnung, <code>1</code> ist meistens unnötig)</td></tr>
    </table>

24. Das Interval in Ticks, in welchem aktualisiert wird, ob ein Entity in der Sicht eines anderen Entity ist.<br>
  Wenn ein Wert &leq; `0` gesetzt ist, ist der Wert gleich wie bei Paper.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>4</code></td><td><code>4</code></td><td><code>1</code></td><td><code>1</code></td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>10</code></td></tr>
    <tr><td><i>Vanilla Verhalten</i></td><td><code>1</code></td></tr>
    </table>

25. Gibt an, ob ein [XOR-Shift](https://www.codeproject.com/Articles/9187/A-fast-equivalent-for-System-Random) Zufallsgenerator anstelle des Standardgenerators von Java genutzt werden soll.
26. Gibt an, ob der XOR-Shift Generator für das Auffüllen von Lootables des Paper `auto-replenish` Features genutzt werden soll.<br>
  Dies hat keine Auswirkung auf normale Minecraft Lootable Truhen.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Paper Verhalten</i></td><td>- (Spieler merken sowieso keinen Unterschied)</td></tr>
    </table>

27. Gibt an, ob der XOR-Shift Generator für den Speed-Boost einer Rakete beim Gleiten genutzt werden soll.

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

28. Gibt an, ob der XOR-Shift Generator für Variationen in Entity-Aktivierung-Zeiten genutzt werden soll.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td>-</td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    </table>

29. Gibt an, ob der XOR-Shift Generator für die Generierung von Bäumen mit der Bukkit API (`World#generateTree`) genutzt werden soll.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Paper Verhalten</i></td><td><code>false</code></td></tr>
    </table>

30. Gibt an, ob der XOR-Shift Generator für die Chance eines Blitzes genutzt werden soll.

    <table>
    <tr><td></td><td><b>Standard</b></td><td></td><td></td></tr>
    <tr><td><b>Empfohlen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td><td><i>Gale</i></td><td><i>Paper</i></td><td><i>Vanilla</i></td></tr>
    <tr><td><code>true</code></td><td><code>true</code></td><td><code>false</code></td><td>-</td></tr>
    </table>
    <table>
    <tr><td><b>Werte für Ziele</b></td><td></td></tr>
    <tr><td><i>Optimierung</i></td><td><code>true</code></td></tr>
    <tr><td><i>Paper Verhalten</i></td><td><code>false</code></td></tr>
    </table>
