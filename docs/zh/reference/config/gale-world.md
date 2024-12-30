# Gale 默认世界配置

!!! info "信息"

    以下 YAML 配置展示了 Gale 默认世界配置（==config/gale-world-defaults.yml==）的结构及其默认的值

    此配置文件基于最新的 Leaf 1.21.1 分支

    点击配置项后面的箭头按钮以显示其描述

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
