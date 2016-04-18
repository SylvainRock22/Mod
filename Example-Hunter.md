== Hunter.yml ==
{{{
Hunter:
  name: 'Hunter'
  prefix: '&2Hunter'
  group: 'class'
  mana: '&2Mana'
  max-level: 40
  parent: ''
  needs-permission: 'False'
  mana-regen: 1
  tree: 'Requirement'
  combo: 0
  skills:
  - 'Blinding Dart'
  - 'Bolas'
  - 'Grapple'
  - 'Venomous Strike'
  - 'Whistle'
  - 'Wild Hunt'
  icon: 'Bone'
  icon-data: 0
  icon-lore:
  - '&2Hunter'
  attributes:
    health-base: 25.375
    health-scale: 0.375
    mana-base: 100
    mana-scale: 0
}}}
== Blinding Dart.yml ==
{{{
Blinding Dart:
  name: 'Blinding Dart'
  type: 'Projectile'
  max-level: 5
  skill-req: ''
  skill-req-level: 1
  needs-permission: 'False'
  msg: '&6{player} &2has cast &6{skill}'
  icon: 'Coal'
  icon-data: 0
  icon-lore:
  - '&d{name} &7({level}/{max})'
  - '&2Type: &6{type}'
  - ''
  - '{req:level}Level: {attr:level}'
  - '{req:cost}Cost: {attr:cost}'
  - ''
  - '&2Mana: {attr:mana}'
  - '&2Cooldown: {attr:cooldown}'
  - '&2Damage: {attr:dmg.value}'
  - '&2Blind: {attr:blind.seconds}'
  - ''
  - '&7Throws a dart that'
  - '&7blinds the first enemy'
  - '&7hit for a short time,'
  - '&7impairing their vision.'
  attributes:
    level-base: 1
    level-scale: 1
    cost-base: 1
    cost-scale: 0
    cooldown-base: 0
    cooldown-scale: 0
    mana-base: 0
    mana-scale: 0
  components:
    Cast-a:
      type: 'trigger'
      data:
        icon-key: ''
      children:
        Projectile-b:
          type: 'mechanic'
          data:
            icon-key: ''
            counts: 'True'
            spread: 'Cone'
            projectile: 'Arrow'
            cost: ''
            speed-base: 3
            speed-scale: 0
            angle-base: 0
            angle-scale: 0
            amount-base: 1
            amount-scale: 0
            angle-base: 0
            angle-scale: 0
            height-base: 8
            height-scale: 0
            radius-base: 2
            radius-scale: 0
          children:
            Damage-c:
              type: 'mechanic'
              data:
                icon-key: 'dmg'
                counts: 'True'
                type: 'Damage'
                value-base: 7
                value-scale: 1
            Potion-d:
              type: 'mechanic'
              data:
                icon-key: 'blind'
                counts: 'True'
                potion: 'Blindness'
                ambient: 'True'
                tier-base: 2
                tier-scale: 0
                seconds-base: 2
                seconds-scale: 0.5
}}}
== Bolas.yml ==
{{{
Bolas:
  name: 'Bolas'
  type: 'Projectile'
  max-level: 5
  skill-req: ''
  skill-req-level: 1
  needs-permission: 'False'
  msg: '&6{player} &2has cast &6{skill}'
  icon: 'Tripwire'
  icon-data: 0
  icon-lore:
  - '&d{name} &7({level}/{max})'
  - '&2Type: &6{type}'
  - ''
  - '{req:level}Level: {attr:level}'
  - '{req:cost}Cost: {attr:cost}'
  - ''
  - '&2Mana: {attr:mana}'
  - '&2Cooldown: {attr:cooldown}'
  - '&2Root: {attr:root.duration}'
  - ''
  - '&7Launches a bola that'
  - '&7roots the first enemy'
  - '&7hit in place for a short'
  - '&7time, stopping movement'
  attributes:
    level-base: 1
    level-scale: 1
    cost-base: 1
    cost-scale: 0
    cooldown-base: 0
    cooldown-scale: 0
    mana-base: 0
    mana-scale: 0
  components:
    Cast-a:
      type: 'trigger'
      data:
        icon-key: ''
      children:
        Item Projectile-b:
          type: 'mechanic'
          data:
            icon-key: ''
            counts: 'True'
            spread: 'Cone'
            item: 'String'
            item-data: 0
            velocity-base: 3
            velocity-scale: 0
            amount-base: 1
            amount-scale: 0
            angle-base: 0
            angle-scale: 0
            height-base: 8
            height-scale: 0
            radius-base: 2
            radius-scale: 0
          children:
            Status-c:
              type: 'mechanic'
              data:
                icon-key: 'root'
                counts: 'True'
                status: 'Root'
                duration-base: 1
                duration-scale: 0.25
}}}
== Grapple.yml ==
{{{
Grapple:
  name: 'Grapple'
  type: 'Target'
  max-level: 5
  skill-req: ''
  skill-req-level: 1
  needs-permission: 'False'
  msg: '&6{player} &2has cast &6{skill}'
  icon: 'String'
  icon-data: 0
  icon-lore:
  - '&d{name} &7({level}/{max})'
  - '&2Type: &6{type}'
  - ''
  - '{req:level}Level: {attr:level}'
  - '{req:cost}Cost: {attr:cost}'
  - ''
  - '&2Mana: {attr:mana}'
  - '&2Cooldown: {attr:cooldown}'
  - '&2Range: {attr:target.range}'
  - ''
  - '&7Drags in the target,'
  - '&7regardless of ally or enemy,'
  - '&7bringing them closer'
  attributes:
    level-base: 1
    level-scale: 1
    cost-base: 1
    cost-scale: 0
    cooldown-base: 0
    cooldown-scale: 0
    mana-base: 0
    mana-scale: 0
  components:
    Cast-a:
      type: 'trigger'
      data:
        icon-key: ''
      children:
        Single-b:
          type: 'target'
          data:
            icon-key: 'target'
            range-base: 4
            range-scale: 2
            tolerance: 4
            group: 'Both'
            wall: 'True'
          children:
            Push-c:
              type: 'mechanic'
              data:
                icon-key: ''
                counts: 'True'
                speed-base: -1.2
                speed-scale: -0.6
}}}
== Venomous Strike.yml ==
{{{
Venomous Strike:
  name: 'Venomous Strike'
  type: 'Target'
  max-level: 5
  skill-req: ''
  skill-req-level: 1
  needs-permission: 'False'
  msg: '&6{player} &2has cast &6{skill}'
  icon: 'Spider Eye'
  icon-data: 0
  icon-lore:
  - '&d{name} &7({level}/{max})'
  - '&2Type: &6{type}'
  - ''
  - '{req:level}Level: {attr:level}'
  - '{req:cost}Cost: {attr:cost}'
  - ''
  - '&2Mana: {attr:mana}'
  - '&2Cooldown: {attr:cooldown}'
  - '&2Range: {attr:target.range}'
  - '&2Damage: {attr:dmg.value}'
  - ''
  - '&7Strikes a target enemy,'
  - '&7dealing damage and '
  - '&7applying a poison for'
  - '&75 seconds.'
  attributes:
    level-base: 1
    level-scale: 1
    cost-base: 1
    cost-scale: 0
    cooldown-base: 0
    cooldown-scale: 0
    mana-base: 0
    mana-scale: 0
  components:
    Cast-a:
      type: 'trigger'
      data:
        icon-key: ''
      children:
        Single-b:
          type: 'target'
          data:
            icon-key: 'target'
            range-base: 2
            range-scale: 0.25
            tolerance: 4
            group: 'Enemy'
            wall: 'True'
          children:
            Damage-c:
              type: 'mechanic'
              data:
                icon-key: 'dmg'
                counts: 'True'
                type: 'Damage'
                value-base: 3
                value-scale: 1
            Potion-d:
              type: 'mechanic'
              data:
                icon-key: ''
                counts: 'True'
                potion: 'Poison'
                ambient: 'True'
                tier-base: 2
                tier-scale: 0
                seconds-base: 5
                seconds-scale: 0
}}}
== Whistle.yml ==
{{{
Whistle:
  name: 'Whistle'
  type: 'Summon'
  max-level: 5
  skill-req: ''
  skill-req-level: 1
  needs-permission: 'False'
  msg: '&6{player} &2has cast &6{skill}'
  icon: 'Bone'
  icon-data: 0
  icon-lore:
  - '&d{name} &7({level}/{max})'
  - '&2Type: &6{type}'
  - ''
  - '{req:level}Level: {attr:level}'
  - '{req:cost}Cost: {attr:cost}'
  - ''
  - '&2Mana: {attr:mana}'
  - '&2Cooldown: {attr:cooldown}'
  - '&2Duration: {attr:wolf.duration}'
  - '&2Damage: {attr:wolf.damage}'
  - '&2Health: {attr:wolf.health}'
  - ''
  - '&7Summons a wolf that fights'
  - '&7by your side temporarily'
  attributes:
    level-base: 1
    level-scale: 1
    cost-base: 1
    cost-scale: 0
    cooldown-base: 0
    cooldown-scale: 0
    mana-base: 0
    mana-scale: 0
  components:
    Cast-a:
      type: 'trigger'
      data:
        icon-key: ''
      children:
        Wolf-b:
          type: 'mechanic'
          data:
            icon-key: 'wolf'
            counts: 'True'
            color: 'Green'
            name: "&2{player}'s Wolf"
            health-base: 12
            health-scale: 3
            damage-base: 3
            damage-scale: 1
            seconds-base: 20
            seconds-scale: 5
}}}
== Wild Hunt.yml ==
{{{
Wild Hunt:
  name: 'Wild Hunt'
  type: 'Passive Aura'
  max-level: 5
  skill-req: ''
  skill-req-level: 1
  needs-permission: 'False'
  msg: '&6{player} &2has cast &6{skill}'
  icon: 'Gold Boots'
  icon-data: 0
  icon-lore:
  - '&d{name} &7({level}/{max})'
  - '&2Type: &6{type}'
  - ''
  - '{req:level}Level: {attr:level}'
  - '{req:cost}Cost: {attr:cost}'
  - ''
  - '&2Mana: {attr:mana}'
  - '&2Cooldown: {attr:cooldown}'
  - '&2Radius: {attr:target.radius}'
  - ''
  - '&7Passively grants bonus'
  - '&7movement speed to yourself'
  - '&7and nearby allies.'
  attributes:
    level-base: 1
    level-scale: 1
    cost-base: 1
    cost-scale: 0
    cooldown-base: 0
    cooldown-scale: 0
    mana-base: 0
    mana-scale: 0
  components:
    Initialize-a:
      type: 'trigger'
      data:
        icon-key: ''
      children:
        Passive-b:
          type: 'mechanic'
          data:
            icon-key: ''
            counts: 'True'
            seconds-base: 1
            seconds-scale: 0
          children:
            Area-c:
              type: 'target'
              data:
                icon-key: 'target'
                radius-base: 4
                radius-scale: 2
                group: 'Ally'
                wall: 'True'
                caster: 'True'
                max-base: 99
                max-scale: 0
              children:
                Potion-d:
                  type: 'mechanic'
                  data:
                    icon-key: ''
                    counts: 'True'
                    potion: 'Speed'
                    ambient: 'True'
                    tier-base: 2
                    tier-scale: 0
                    seconds-base: 1.25
                    seconds-scale: 0
}}}