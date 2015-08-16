MaskOfFutures
=============

This plugin contains three features of varying degrees of completeness originally prepared for Nerd.Nu's Halloween 2014 event.

- Death signs (incomplete)
- Brick dropping from wither sounds (complete, though broken by 1.8 Spigot transition)
- Death messages (complete, though made incomplete by transition to 1.8 Spigot)


The original concept for death signs was the idea that a sign reporting player name, reason of death, and time of death (server time) would be placed at the location of the player's death.  Policy and maintainability concerns ended development of this partway through, but bits of this are still present in the code.

===
MoF In-Game Config Changing
===

/mof will bring up the current config states of brick dropping and custom death messages.  These can be altered in-game with:

/mof <brick-dropping|death-msgs> <true|false>

Additionally, if the config is changed while the plugin is running, 

/mof reload

will reload the config file.

===
Brick Dropping
===

Whenever a Wither explodes when it spawns in, all players on the server will drop a brick at their feet with the lore: "<Player> dropped this on hearing a Wither".  Players in Modmode will not drop this brick to prevent the sight of bricks falling out of the sky, but their presence will instead be logged to console in the hope that they will be reimbursed some time after they leave Modmode.  The list of players who received a brick will also be logged to console for record keeping.

===
Death Messages
===

These custom death messages are specified in the config file (config.yml) and, when on, will replace the vanilla death messages with the custom one if one exists.  When off, the plugin will instead log debug information to the console while allowing the vanilla death message to be broadcast unhindered.  The debug information consists of:

- Reason of death
- Last entity to deal killing blow to player (if killed by entity such as a mob)
- Death message (if it exists; if this does not appear, then a death message for that particular reason and killer is missing!)