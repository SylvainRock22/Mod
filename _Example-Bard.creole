== Bard.yml ==
{{{
Bard:
  name: 'Bard'
  prefix: 'Bard'
  group: 'class'
  mana: '&2Mana'
  max-level: 40
  parent: ''
  needs-permission: 'False'
  mana-regen: 1
  tree: 'Requirement'
  combo: 0
  skills:
  - 'Galvanize'
  - 'Heal'
  - 'Horrible Cry'
  - 'Racket'
  - 'Repulse'
  - 'Motivation'
  icon: 'Golden Apple'
  icon-data: 0
  icon-lore:
  - '&dBard'
  - ''
  - '&7A supportive class that'
  - '&7focuses on AOE utility'
  - '&7skills and healing or'
  - '&7cleansing allies.'
  attributes:
    health-base: 25.375
    health-scale: 0.375
    mana-base: 100
    mana-scale: 0
}}}
== Galvanize.yml ==
{{{
Galvanize:
  name: 'Galvanize'
  type: 'AOE Buff'
  max-level: 5
  skill-req: ''
  skill-req-level: 1
  needs-permission: 'False'
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
  - '&2Duration: {attr:dur.seconds}'
  - ''
  - '&7Rallies nearby allies,'
  - '&7speeding them up and'
  - '&7cleansing negative'
  - '&7effects on them.'
  attributes:
    level-base: 1
    level-scale: 1
    cost-base: 1
    cost-scale: 0
    cooldown-base: 12
    cooldown-scale: -1
    mana-base: 30
    mana-scale: -2
  components:
    Cast-a:
      type: 'trigger'
      data:
        icon-key: ''
}}}
== Heal.yml ==
{{{
Heal:
  name: 'Heal'
  type: 'Cone Heal'
  max-level: 5
  skill-req: ''
  skill-req-level: 1
  needs-permission: 'False'
  icon: 'Golden Apple'
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
  - '&2Health: {attr:heal.value}'
  - ''
  - '&7Heals yourself and allies'
  - '&7within a cone in front of you.'
  attributes:
    level-base: 1
    level-scale: 1
    cost-base: 1
    cost-scale: 0
    cooldown-base: 10
    cooldown-scale: -1
    mana-base: 25
    mana-scale: 0
  components:
    Cast-a:
      type: 'trigger'
      data:
        icon-key: ''
      children:
        Cone-b:
          type: 'target'
          data:
            icon-key: ''
            range-base: 3
            range-scale: 0.25
            angle-base: 90
            angle-scale: 0
            group: 'Ally'
            wall: 'True'
            caster: 'True'
            max-base: 99
            max-scale: 0
          children:
            Heal-c:
              type: 'mechanic'
              data:
                icon-key: 'heal'
                type: 'Health'
                value-base: 6
                value-scale: 1
            Particle-d:
              type: 'mechanic'
              data:
                icon-key: ''
                particle: 'Wolf Hearts'
                arrangement: 'Hemisphere'
                radius-base: 1
                radius-scale: 0
                amount-base: 20
                amount-scale: 0
                direction: 'XZ'
                data: 0
                visible-radius: 25
                dx: 0
                dy: 0
                dz: 0
                speed: 1
}}}
== Horrible Cry.yml ==
{{{
Horrible Cry:
  name: 'Horrible Cry'
  type: 'AOE Utility'
  max-level: 5
  skill-req: ''
  skill-req-level: 1
  needs-permission: 'False'
  icon: 'Ghast Tear'
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
  - ''
  - '&7Stuns all nearby enemies'
  - '&7while dealing a small'
  - '&7amount of damage per'
  - '&7second for 4 seconds.'
  attributes:
    level-base: 1
    level-scale: 1
    cost-base: 1
    cost-scale: 0
    cooldown-base: 14
    cooldown-scale: -1
    mana-base: 28
    mana-scale: -1
  components:
    Cast-a:
      type: 'trigger'
      data:
        icon-key: ''
      children:
        Area-b:
          type: 'target'
          data:
            icon-key: ''
            radius-base: 3
            radius-scale: 0.5
            group: 'Enemy'
            wall: 'True'
            caster: 'False'
            max-base: 99
            max-scale: 0
          children:
            Repeat-c:
              type: 'mechanic'
              data:
                icon-key: ''
                repetitions-base: 4
                repetitions-scale: 0
                period: 1
                delay: 0
              children:
                Damage-d:
                  type: 'mechanic'
                  data:
                    icon-key: 'dmg'
                    type: 'Damage'
                    value-base: 1
                    value-scale: 0.25
            Status-e:
              type: 'mechanic'
              data:
                icon-key: ''
                status: 'Stun'
                duration-base: 1
                duration-scale: 0.1
}}}
== Motivation.yml ==
{{{
Motivation:
  name: 'Motivation'
  type: 'Passive Aura'
  max-level: 5
  skill-req: ''
  skill-req-level: 1
  needs-permission: 'False'
  icon: 'Diamond'
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
  - '&2Damage: {attr:buff.value}'
  - '&2Radius: {attr:area.radius}'
  - ''
  - '&6+5 Morale'
  - '&7Nearby allies gain a'
  - '&7small amount of damage.'
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
            seconds-base: 1
            seconds-scale: 0
          children:
            Area-c:
              type: 'target'
              data:
                icon-key: 'area'
                radius-base: 2
                radius-scale: 2
                group: 'Ally'
                wall: 'True'
                caster: 'True'
                max-base: 99
                max-scale: 0
              children:
                Damage Buff-d:
                  type: 'mechanic'
                  data:
                    icon-key: 'buff'
                    type: 'Flat'
                    value-base: 2
                    value-scale: 0
                    seconds-base: 1.5
                    seconds-scale: 0
}}}
== Racket.yml ==
{{{
Racket:
  name: 'Racket'
  type: 'Projectile'
  max-level: 5
  skill-req: ''
  skill-req-level: 1
  needs-permission: 'False'
  icon: 'Firework'
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
  - ''
  - '&7Plays an awful note that'
  - '&7damages the first enemy'
  - '&7to be hit by the full'
  - '&7force. Poor soul...'
  attributes:
    level-base: 1
    level-scale: 1
    cost-base: 1
    cost-scale: 0
    cooldown-base: 5
    cooldown-scale: -0.5
    mana-base: 15
    mana-scale: 0
  components:
    Cast-a:
      type: 'trigger'
      data:
        icon-key: ''
      children:
        Particle Projectile-b:
          type: 'mechanic'
          data:
            icon-key: ''
            spread: 'Cone'
            particle: 'Note'
            frequency: 0.25
            velocity-base: 3
            velocity-scale: 0
            angle-base: 30
            angle-scale: 0
            amount-base: 1
            amount-scale: 0
            lifespan: 5
            data: 0
            visible-radius: 25
            dx: 0
            dy: 0
            dz: 0
            speed: 1
            angle-base: 30
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
                type: 'Damage'
                value-base: 5
                value-scale: 1
}}}
== Repulse.yml ==
{{{
Repulse:
  name: 'Repulse'
  type: 'AOE Utility'
  max-level: 5
  skill-req: ''
  skill-req-level: 1
  needs-permission: 'False'
  icon: 'Piston Base'
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
  - '&2Speed: {attr:spd.speed}'
  - ''
  - '&7Pushes away all nearby'
  - '&7players and mobs.'
  attributes:
    level-base: 1
    level-scale: 1
    cost-base: 1
    cost-scale: 0
    cooldown-base: 12
    cooldown-scale: -1
    mana-base: 28
    mana-scale: -1
  components:
    Cast-a:
      type: 'trigger'
      data:
        icon-key: ''
      children:
        Area-b:
          type: 'target'
          data:
            icon-key: ''
            radius-base: 2
            radius-scale: 0.5
            group: 'Both'
            wall: 'True'
            caster: 'False'
            max-base: 99
            max-scale: 0
          children:
            Push-c:
              type: 'mechanic'
              data:
                icon-key: 'spd'
                speed-base: 1
                speed-scale: 0.5
}}}