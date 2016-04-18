The main part of the plugin is it's API that allows developers too hook into the features of SkillAPI and create their own unique skills with ease! The provided API allows for easy registration of skills and classes alike along with base classes to extend that provide all of the features of the plugin. 

All of the source code of the API is also provided in case you want to see how it works and become more familiar with it in order to use it more easily. The link to the source is both at the bottom of this page and on the main page! 

== Classes ==
For classes, there is a CustomClass class that can be extended. This only requires a few parameters to be passed into the superconstructor and then the class will be able to be registered and available to players. There are optional methods as well that let you control the class's health, mana, damage for each item, available click combinations for skills, and many others. For a detailed list of available methods, check out the javadocs either through the link at the bottom of this page or on the main page. 


== Skills ==
For skills, there is a ClassSkill class that can be extended. This, similar to the CustomClass, requires only a few parameters to be passed to the superconstructor. Only doing this for skills doesn't make the skill do anything though, just lets it be added to a class and show up. In order to make it do something, the API also provides a few interfaces that you can implement for various effects. The interfaces that are used are:

== SkillShot ==
This interface turns your skill into something that can be cast at any time. The interface provides a cast method that is called whenever a player uses the cast command, right clicks with a bound item, or performs the click combination for your skill. This makes it very easy to know when to make your skill do something. The method also provides you the level of the skill so you can quickly determine how effective to make the skill as well! SkillShots are also automatically assigned click combinations for players to use if they are enabled.

== TargetSkill ==
Similar to the SkillShot, this provides a cast method that is called when the player uses the cast command, right clicks with a bound item, or performs the click combination for your skill. This interface however requires the player to be looking at a target to use it, and also provides a few extra arguments to the method. It provides the target the player was looking at along with whether or not the target is an ally. This allows you to determine easily whether or not the target should be affected by your skill. Target skills are also automatically assigned click combinations for players to use if they are enabled.

== PassiveSkill ==
Passive skills provide methods for setting up, updating, or removing effects for players whenever they log in, out, or upgrade/downgrade their skill. These methods allow for simple determination of what players have the skill as all the checks are handled by the API. Passive skills do not receive click skill combinations and cannot be cast as they are meant to be applied all the time.

== Listener ==
The Bukkit interface Listener is also supported by the API so that you don't have to register events yourself. All you need to do is implement it and make your EventHandler methods like normal, and the event registration will be automatically taken care of. This is due to many skills needing listeners for various effects from applying when a player takes/deals damage or when a projectile lands. This was more of just a minor convenience when setting up more effects, but also helps prevent issues of trying to register events before your plugin was enabled. 

Aside from the main skill and class utilities, the API also provides various helper classes for effects such as statuses, launching projectiles, playing effects, applying DOTs, and many others! Most of these can be found in the com.sucy.skill.util package and you can look through that in the javadocs. 

If you need help getting into the API, check out the tutorials linked to below! 