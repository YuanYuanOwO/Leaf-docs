# Gale 全局配置

!!! info "信息"

    以下 YAML 配置展示了 Gale 全局配置（==config/gale-global.yml==）的结构及其默认的值

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
