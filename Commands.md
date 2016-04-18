### Commands

The main commands for SkillAPI

/class acc <accountId>

User: player only 
This changes the current active account for the player

/class ap [player] amount

User: player or console 
Gives attribute points to yourself or a specified player

/class attr

User: player only 
Opens the menu to invest points in and view attributes

/class bar

User: player only 
Toggles skill bars on or off (if enabled)

/class bind <skill>

User: player only 
This binds the skill to the player's held item if they have the skill unlocked

/class cast <skill>

User: player only 
This causes the player to cast the skill if all conditions are met

/class clearbind

User: player only 
This clears all bound skills the player has

/class combo <skill> <combo>

User: player only 
Sets the click combo for the skill

/class exp [player] <amount>

User: player or console 
This gives experience to a player

/class info [player]

User: player or console 
This displays class information about the player including what class they are and their level/experience

/class level [player] <amount>

User: player or console 
This gives levels to a player

/class list [player]

User: player or console 
This lists out the player's accounts along with what their main class and level is on each one

/class lore <lore>

User: player only 
Adds a line of lore to the held item (mostly for testing purposes)

/class mana [player] <amount>

User: player or console 
This gives a player mana that cannot exceed their max amount

/class options

User: player only 
This displays the available classes that the player can turn into

/class points [player] <amount>

User: player or console 
This gives a player skill points for all classes that accept command points

/class profess <class>

User: player only 
This changes the player's class to the specified one unless they are not able to do so at the time

/class reload

User: player or console 
This reloads the plugin, unloading all data then reloading it to apply config changes (VERY SLOW)

/class reset

User: player only 
This resets the player's active account data, wiping all their professed classes

/class skill

User: player only 
This causes the player to open up their skill tree

/class unbind

User: player only 
This removes any binds on the player's held item

/class forceaccount <player> <accountId>

User: console only 
Sets the active account for a specified player

/class forceattr <player> [attr] [amount]

User: console only 
Resets all attributes for a player if only a player is specified 
Resets a specific attribute for a player if an attribute is specified 
Gives a player attribute points if an attribute and an amount is specified

/class forcecast <player> <skill> [level]

User: console only 
Causes a player to cast a skill, ignoring any requirements to do so

/class forceprofess <player> <class>

User: console only 
Forces a player to try to profess as the specified class