# Terraria NPC Happiness
The 1.4 Terraria update made it so that [NPCs have preferences](https://terraria.gamepedia.com/Happiness#Happiness) regarding their location, who they are near, etc. This script simulates the happiness of various groups of NPCs and finds the best possible layout for where they all should live. It internally uses [Dijkstra](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm) (and some smaller optimizations) to find the optimum.

## Running the program
Download the repository (Clone or download) and run `python3 npc.py` (you need to have Python 3 installed!).

## Restrictions
You can add certain biome and NPC restrictions by modifying the
`NPC.biome_restrictions` and `NPC.npc_restrictions` variables (although this might provide less optimal of a solution!).

## Contents
The `in` file is [this table](https://terraria.gamepedia.com/index.php?title=NPCs&action=edit&section=11) from Terraria's Wiki -- this is where preferences are parsed from.

The `out` file contains all of the resulting optimal layouts after the program stopped running. It currently contains the best layout, given the following constraints:

- Witch Doctor lives in the Jungle
- Truffle lives in the Mushroom
- Santa Claus lives in the Snow
- Steampunker, Cyborg and Goblin Tinkerer live together

Personally, I think this is the best one:
```
Desert:
- Dye Trader (0.85)
- Stylist (0.8)

Forest:
- Arms Dealer (0.8)
- Guide (0.85)
- Nurse (0.8)

Forest:
- Demolitionist (0.8)
- Merchant (0.85)
- Tavernkeep (0.8)

Hallow:
- Painter (0.85)
- Party Girl (0.75)
- Wizard (0.85)

Jungle:
- Golfer (0.85)
- Witch Doctor (0.85)
- Zoologist (0.75)

Mushroom:
- Dryad (0.85)
- Truffle (0.85)

Ocean:
- Angler (0.85)
- Pirate (0.75)

Snow:
- Clothier (0.85)
- Tax Collector (0.85)

Snow:
- Mechanic (0.85)
- Santa Claus (0.8)

Underground:
- Cyborg (0.85)
- Goblin Tinkerer (0.85)
- Steampunker (0.8)
```
