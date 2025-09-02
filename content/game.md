# Board Game
ExoGIS (geographical information system)

Area control with objectives and light engine building - rune wars meets terra mystica

## Flavor
*You are AIs owned by rival surveying corporations collecting geospatial data on an inhospitable exoplanet.*

*You'll need to adapt to the terrain, harvest resources, create more factories and mechs, and deploy scanners to retrieve the most complete picture of the planet to sell to colonists or mining companies.*

## Goal
Scan the highest number of hexes before the game ends.

## Board
### Hexes
*Most of the planet is inhospitable to default mechs - you'll need to modifications to traverse certain areas, and some areas will need more than 1.
Red modifications add electronic shielding for unimpaired functionality in highly radioactive hexes.
Blue modifications are additives to inhibit microbe growth and discourage fauna attacks.
Yellow modifications are paints and greases to prevent chemical corrosion.*

Hexes have color-coded requirements for occupation:
* White: no modifications necessary
* Red / Blue / Yellow: Red, blue, and yellow modifications, respectively
* Purple: Red and blue
* Green: Blue and yellow
* Orange: Yellow and red
* Black: Red, blue, and yellow

## Factions
* 2-3p: played factions must be all primary or all secondary
* 4p: the unplayed factions must be directly opposite each other
* 5p: single unplayed faction gets neutral units that defend territories - TBD
* 6p: all factions in play

Every unplayed faction gets neutral units in place (how many? where?)
### Faction Abilities
TBD - expansion lol

## Units
You have mechs and factories. Each thing has a stand denoting modifications.
### Stands
Mech stands determine where a mech can move.
Factory stands determine what stand a mech is built with.

### Mechs
#### Movement
Mechs can only go on or through hexes they have modifications for.

### Factories
Can be upgraded for extra defense and mech spawning. Can be stolen (damaged).
Factory stands determine what colors a mech can spawn with - not where a factory can exist.

Factory number of upgrades is the number of colors - 0 upgrades: white, 1: primary, 2: secondary, 3: black.
Factories spawn as level 2 (1 upgrade).
Factories stolen from enemies becomes level 1 (0 upgrades).

You can choose to spawn units of fewer colors than the factory, as long as they can occupy the hex.

## Turns
Simultaneous declaration - reveal action cards at the same time.
Cards are resolved in numbered order.
Ties are resolved by completed objectives, then unused alloy, then spending alloy (shout a number, the other person must pay a higher number or go second).

### Days
Days are 4 sets turns, using cards like Rune Wars.
There is no such thing as supremacy bonuses, just upgrades.
Cards played for the day cannot be reused until the following day.

morning, noon, evening, night.

You have +1 upgrade for cards played at noon.
You have -1 upgrade for cards played at night.

There is no benefit to +1 upgrade on maxed out cards?
There is no detriment to -1 upgrade on base cards (level 0)

## Cards
Cards can be upgraded for better effect.
Cards go in numbered order, ties go to upgrade level then  alloys and then they're simultaneous (for combat, that means declaring where you're attacking at the same time, then how many units you move in and from where at the same time)

TODO: intentional card ordering

### 1. Strategize
Move to 1 + $LEVEL friendly or empty territories, speed 1, does not activate the area.
Cap: 4

### 2. Mobilize
Move from multiple hexes, activating the area.
Can only move through friendly or empty territories, and still have to match colors.

* 1: Move at speed 2
* 2: Move at speed 2 using quantum tunneling between identical colors
* 3: Same as 2, does not activate the area.

### 3. Conquer
Attack from any number of adjacent hexes, activating the area, $LEVEL combat power.
Cap: 4

### 4. Harvest
Harvest based on hexes with $LEVEL bonus alloys.
Cap: 3

### 5. Recruit
Spawn with alloys and $LEVEL extra white mechs (can be modified as you spawn them, but you must pay for the modifications)
Cap: 3

Factories can only spawn a number of mechs equal to their level.

Mechs cost 2, plus one per modification.

~~Mechs of your faction color are 1 cheaper.~~
The mech's stand is any color the base could produce that can stand on the hex.

Ex: 
* white hex, purple factory: white, blue, red, or purple
* yellow hex, orange factory: yellow or orange
* black hex, green factory: black
* yellow hex, red factory: cannot build

### 6. Upgrade
combine mechs on the same hex to merge stand colors - free;
Complete new quest and upgrade a card;

Must be played before evening.

Could be interesting to make 2 upgrades upgrade this card to be able to double upgrade, but then this card becomes too powerful at noon.
Alternatively, +1 upgrade does nothing and the level 2 upgrade lets you double upgrade, but that's the same issue where you'll always level 1 upgrade this card and use it at noon.
(Could make this card only be played at morning?)

### 7. Fortify
$LEVEL defense bonus this turn;
With mech: create level 2 factory with 8 - $LEVEL alloy;
With mech: upgrade **existing** factories by one level with 3 - $LEVEL alloy;
With mech: terraform controlled or adjacent territories to be one color more or less using 6 - 2 * $LEVEL alloy (enemy territories can only be cleaned).
Cap: 3

### 8. Acquire Power
With non-activated Mech: Create a scanner between hexes you control.
Scanner costs 6 alloy plus 1 per required mod.
Scanner requires:
* 0: all adjacent hex control
* 1: all adjacent hex control; 3 alloy discount
* 2: all but 1 adjacent hex control
* 3: all but 1 adjacent hex control; 3 alloy discount
* 4: all but 2 adjacent hex control
* 5: all but 2 adjacent hex control; 3 alloy discount

(Level 4 does not mean you can airdrop a line scanner from anywhere; you still need an adjacent mech to deploy.)


## Combat
*Interstellar law prohibits sabotaging competing efforts, but short of destroying a company's scanners, no one will be able to prove anything.*

Combat is just 1:1 (attacker sacrifices X units to destroy X defenders).

## Upgrades
*Mechs weren't designed with this particular planet's gravity and topology in mind. Gather more training data to make actions more efficient.*

Upgrades are per card. Upgrading involves grabbing the higher number card of that name.

When upgrade tokens run out, game ends that night.

### Objectives
* Control the center hex
* Control a hex 7 away from your starting hexes
* Control a hex in an enemy's home row (home row: set of 4 outer edge hexes for each faction)
* Fully upgrade an factory
* Fully upgrade a card
* Control 15 hexes (4p, 2p: 30, 3p: 20, 5-6p: 10)
* Control a straight line of 5 hexes (4p, 5-6p: 4, 3p: 5, 2p: 7
* Control a black hex
* Control 4 rim hexes (secondary-advantaged)
* Unlock a secondary that includes a color you didn't start with (primary-advantaged)
* Unlock all secondaries (secondary-advantaged)
* Terrform 3 times
* Have 4 bases
* Successfully invade
* Upgrade a card, place a scanner, and upgrade a factory
* Place 3 corner scanners

## Game Over
Game ends on the night of the day that ... we run out of objective markers.
Or someone completes 10 objectives? 
How much? No idea - 2-3: 8/p, 4: 7/p, 5-6: 6/p
^ These are probably too long.

Winner is most hex data uploaded back to civilization.

## Setup
You start with two factories, two hexes, two mechs, 1 scanner, and 8 alloys.
Primaries get two of their color, secondaries get their neighboring primaries.
