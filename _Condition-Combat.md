=== Condition ===
Child components are applied to each player target who's combat status matches the conditions

=== Options ===
|= Name |= YAML Key |= Type |= Description |
| In Combat | combat | [[Boolean|_Option Boolean]] | Whether or not the target should be in target |
| Seconds | seconds | [[Integer|_Option Integer]] | The amount of time since the last attack before being out of combat |

=== Description ===
* The seconds option is multiplied by 20 to convert it into ticks before flooring it

=== Usage Examples ===
-- To be added --