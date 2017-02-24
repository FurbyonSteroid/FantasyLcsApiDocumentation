# Unofficial Fantasy LCS API
---
## Table of Contents
 1. [api/season/{number}](http://fantasy.na.lolesports.com/en-US/api/season/)
    1. rosterLocksByWeek
    2. proTeams
    3. proPlayers
    4. proMatchups
    5. stats
        1. projectTeamStats
        2. actualTeamStats
        3. projectPlayerStats
        4. actualPlayerStats
2. not yet
---
## Definitions of Fields
Fieldname|Type|Description
---|---|---
seasonName|String|The name of the season e.g. "Spring 2016"
seasonSplit|String|The split of the season e.g. "Spring"
seasonBegins|DateTime|A date and time representing the start of the season
seasonEnds|DateTime|A date and time representing the end of the season
numberOfWeeks|byte|A representation of the maximum numbers of weeks for this season
byeWeeks|Array:byte|An array (not sure why) which contains a number of already passed weeks
### rosterLocksByWeek
Fieldname|Type|Description
---|---|---
numeric (1 to numberOfWeeks)|Strings|Contains two values which are called "NA" and "EU". The Value contains the date and time when the picks for that specific week lock
### proTeams
Fieldname|Type|Description
---|---|---
id|Short|The ID used for referencing this object
riotId|Short|Internal ID from Riot... unsure what it's for
name|String|Full name of the team
shortName|String|The shortened version of the team name; used for results etc
flavorTextEntries|Array|Unknown
trendsByWeek|Array:float|Trends by week. Calculated via bot from riot; used for future matchup scores; only contains a 5 Values Array which numbers purpose are unknown yet
positions|String|The positions e.g. Jungle, Top etc; Teams only have the term TEAM
league|String|The region of the league; currently only NA and EU
### proPlayers
Fieldname|Type|Description
---|---|---
id|Short|The ID used for referencing this object
riotId|Short|Internal ID from Riot... unsure what it's for
name|String|Name of the player
photoUrl|String|The photourl of the player; can be empty
positions|String|The positions the player can play at e.g. Jungle, Top, ADC etc.
proTeamId|Short|The id of the team the player currently plays at
flavorTextEntries|String|Unknown
trendsByWeek|Array:float|Trends by week. Calculated via bot from riot; used for future matchup scores; only contains a 5 Values Array which numbers purpose are unknown yet
### proMatchups
Fieldname|Type|Description
---|---|---
id|Short|The ID used for referencing this object
riotID|String|Internal ID from Riot... unsure what it's for
week|short|The current LCS week
time|DateTime|The time of when it starts/when it started
redTeamId|Short|The team id of the team who played on the red side
blueTeamId|Short|The team id of the team who played on the blue side
complete|boolean|If the game is over or not
winner|Short|The id of the team who won; or 0 if the game is not finished yet

## stats
### actualTeamStats
not yet worked on
### projectTeamStats
The predictions calculated by riot bots. Content equals "actualTeamStats"
### actualPlayerStats
Includes Arrays in one Array.

Index|Type|Description
---|---|---
0|Short|The player ID of the player
1|Short|The team ID the player currently plays at
2|Short|The match ID
3|Short|The match number of the game (1-3)
4|Short|Number of kills
5|Short|Number of deaths
6|Short|Number of assists
7|Short|Number of minions killed
8|Short|Number of double kills
9|Short|Number of tripple kills
10|Short|Number of quadra kills
11|Short|Number of penta kills
12|Byte|If the player has 10+ kills or assists (0 = no, 1 = yes)
### projectedPlayerStats
The predictions calculated by riot bots. Content equals "actualPlayerStats"
