---
template: no-redirect.html
---

# ExoGIS
*Exoplanet Geographical Information System*

Area control with objectives and light engine building.
Rune Wars (4-turn cycle, 8 card action hand) meets Terra Mystica (hexes with terraforming) meets Scythe (upgrades, light engine building).

## Flavor
*You are AIs owned by rival surveying corporations collecting geospatial data on an inhospitable exoplanet.*

*You'll need to adapt to the terrain, harvest resources, create more factories and mechs, and deploy scanners to retrieve the most complete picture of the planet to sell to colonists or mining companies.*

## Goal
You win by scoring the most points.
The only thing worth points is the number of unique hexes scanned.

[Scan the highest number of hexes](#scoring) before the [game ends](#game-over).

## Setup
You start with one [factory](#factories), two hexes, two [mechs](#mechs), all with [stands](#stands) of your starting color.
You start with 8 alloy.

![Setup](game/setup.png)

## Board
### Hexes
Hexes are one of 7 colors: red, blue, yellow, purple, green, orange, and black.
Some hexes are "special" hexes, marked with ??? (some icon).

A [mech](#mech) can only occupy hexes that are within 1 color of its [stand](#stand).
Within 1 color means exactly matching, or adjacent on the [color wheel](#color-wheel).

Special hexes require an exact color match, but produce an extra [alloy](#alloy) when [quarried](#quarry).

No color is adjacent to black on the [color wheel](#color-wheel).
This means black hexes cannot be [controlled](#glossary) and must be [terraformed](#develop).

#### Color Wheel
![Color Wheel](game/colorwheel.png)

## Factions
* 2-3p: played factions must be all primary colors (RBY) or all secondary colors (PGO).
* 4p: the unplayed factions must be directly opposite each other
* 5p: single unplayed faction gets neutral units that defend territories - TBD
* 6p: all factions in play

### Faction Abilities
TBD - expansion lol

## Pieces
You have [scanners](#scanners), [mechs](#mechs), [factories](#factories) in your color.
There are [stands](#stands) of every color.
Everyone can gather [alloy](#alloy).
There are, in some vague sense, [objective tokens](#objectives).
There are no piece limits.
## Scanners
Placed with the [scan](#scan) action to scan 1 or more hexes.
Scanners are *not* units, do not go on hexes, and cannot be destroyed.
Placed without stand (really, just place any stand under them, because they'll fall over without it).
Cannot be moved or destroyed.
## Alloy
The only resource.
[Quarried](#quarry) from hexes you control.
Goes into your personal supply; does not touch the board.
## Units
Mechs and factories are units and go on hexes.
Any unit controls a hex.
Each unit has a stand denoting modifications.
### Stands
Stands are just bases for pieces, and do nothing on their own.

[Mech](#mechs) stands show the modifications the mech has undergone, and thus, where the mech can move.

[Factory](#factories) stands show the modified mechs a factory can produce.

### Mechs
Mechs [control](#glossary) [hexes](#hexes), [build and expand](#develop) [factories](#factories), can [move](#movement), and can engage in [combat](#combat).

See other sections for details and exceptions, but in general, mechs have 1 attack, 1 defense, 2 movement.

### Factories
Can be expanded for extra defense and [mech spawning](#deploy). Can be stolen (damaged) in [combat](#combat).

Factory [stands](#stands) are **always** the color of the [hex](#hexes) they occupy - if the hex is [terraformed](#develop), immediately change the factory stand to match.
Factories produce mechs with matching stands.

Factories can only [deploy](#deploy) a number of mechs equal to the number of expansions.

Factories add extra defense to a hex - each level counts 

Factory number of expansions is the number of colors - 0 expansions: white, 1: primary, 2: secondary, 3: black.
Factories spawn as level 2 (1 expansion).
Factories stolen from enemies become unexpanded (level 1 / 0 expansions).

See [Manufacture](#manufacture) to details on mech production.

## Turns
Simultaneous declaration - reveal action cards at the same time.
Cards are mostly simultaneous action (with the exception of [combat](#combat)) , but if someone requests, [other cards can be ordered as well](#cards).

### Days
Days are 3 rounds - morning, evening, and night.

Cards played for the day cannot be reused until the following day.

#### Morning
Pick up all [cards](#cards) played yesterday.
[You have **+1 upgrade** for cards played in the morning.](#upgrades)
There is no benefit to +1 upgrade on maxed out cards.
### Evening
Nothing?
### Night
[ You have **-1 upgrade** for cards played at night.](#upgrades)
There is no detriment to -1 upgrade on base, non-upgraded cards.

## Cards
*Think Rune Wars, but no supremacy bonuses, only upgrades.*

Cards can be [upgraded](#upgrades) for better effect.
Cards start with zero upgrades.
On cards with multiple actions ([Develop](#develop) and [Streamline](#streamline)) you may take any number of the actions **in order**.

Cards are technically resolved in numbered order, though outside of [combat](#combat), most cards can be resolved simultaneously.
Ties are resolved by [completed objectives](#objectives), then unused alloy, then bidding alloy (say a number, next person must bid higher or lose the tie).
Tie winner chooses who goes first.

### Develop - TBD
Priority 1.

* With mech: expand any number of **existing** factories once each with `3 - # Upgrades` alloy;
* With mech: spend `8 - # Upgrades` alloy to create one factory one expansion;
* With mech: terraform up to 3 controlled or adjacent territories to be one color more or less using `6 - 2 * # Upgrades` alloy (enemy territories can only be cleaned).

Upgrade cap: 3

### Coordinate
Priority 2.
Choose 2 hexes. Move mechs from those hexes to 2 **adjacent** [controlled](#glossary) or empty destination hexes.
Each mech cannot move more than 1 hex this way.

Upgrades:

* **Multithreading**: No limit on number of hexes. Each mech may move to an adjacent [controlled](#glossary) or empty hex.
* **Overclocking**: Mechs may move at speed 2 this way.

### Explore
Priority 3.
Move any number of mechs from any number of hexes to a destination hex.

Can only move through [controlled](#glossary) or empty territories, and still have to match colors.

Upgrades:

* **Quantum tunneling**: Treat identical colors separated by 1 hex as adjacent instead. (This can result in an effective speed of 4.)
* **Overvolting**: Gain two extra [combat strength](#combat) this turn.
* **Multiprocessing**: Choose a second destination hex.

### Quarry
Priority 4.
Gain 2 alloy from each [controlled](#glossary) hex.

Upgrades:

* **Breadth-first search**: [Normal hexes](#hexes) produce 3 alloy instead of 2.
* **Depth-first search**: [Special hexes](#hexes) produce 5 alloy instead of 2.

### Manufacture
Priority 5.
With any number of factories: spend alloy to deploy mechs, with `# Upgrades` extra white mechs (can be modified as you spawn them, but you must pay for the modifications)
Factories can only spawn a number of mechs equal to their level.

Mechs cost 2, plus one per modification.

~~Mechs of your faction color are 1 cheaper.~~
The mech's stand is any color the base could produce that can stand on the hex.

Examples: 

* white hex, purple factory: white, blue, red, or purple
* yellow hex, orange factory: yellow or orange
* green hex, green factory: green
* yellow hex, red factory: cannot build

Upgrade cap: 3

### Streamline
Priority 6.
Can only be played at morning.

* Any number of times and hexes: combine mechs on the same hex to merge stand colors;
* Complete one new quest (must currently meet requirements) and [upgrade](#upgrade) a card X times based on `# Upgrades`;

* 0: once
* 1: once
* 2: twice

Upgrade cap: 2

### Scan
Priority 7.
With mech: Create a scanner between hexes you control.

Scanners can be placed between two hexes (on a line), or between 3 hexes (on a corner).
Scanners can also be placed off the edge of the board if you really want.

Scanner costs 6 alloy plus 1 per required mod, (with a 1 alloy discount for every scanner already present?).
Scanner requires:

* 0: all adjacent hex control
* 1: all adjacent hex control; 3 alloy discount
* 2: all but 1 adjacent hex control
* 3: all but 1 adjacent hex control; 3 alloy discount
* 4: all but 2 adjacent hex control
* 5: all but 2 adjacent hex control; 3 alloy discount

Scanners do not need a stand: they cannot be moved or destroyed once placed, regardless of terraform actions, hex control, or combat.
Scanners can be co-located.

(Level 4 does not mean you can airdrop a line scanner from anywhere; you still need an adjacent mech to deploy.)

Upgrade cap: 5

## Movement
By default, mechs have a speed of 2, meaning they can only move from a hex to an adjacent hex.
No other [pieces](#pieces) can be moved.

Upgrading the [Explore](#explore) action allow you to move mechs at speed 2.
Mechs can only move through friendly or empty hexes that they can stand in.

Upgrading the Explore action again allows you to blink between hexes of the same color that are less than 2 hexes apart.
Tunneling between these hexes counts allows you to to bypass enemy or inhospitable hexes.
Tunneling between these hexes treats them as adjacent, meaning you could move up to 4 hexes away.

## Combat
*Interstellar law prohibits sabotaging competing efforts, but short of destroying a company's scanners, no one will be able to prove anything.
This means your mechs aren't designed for combat, but neither are anyone else's.
Your best plan is mutually assured destruction: overload your power source and explode your units to take out theirs.
Factories will enter lockdown during combat - you'll have to spend some explosive strength to damage them enough to get in and take control.*

Combat is just 1:1 - attacker sacrifices X units to destroy X defender units.
Each factory expansion counts as a unit (each mech counts as one unit regardless of modifications).
If you successfully invade a hex with a factory, destroy your opponent's factory and place an unexpanded factory (white stand) on the hex.

You can choose to attack with fewer units if you want to weaken your opponent's forces, though you won't gain control of the hex.
A tie means the territory becomes unoccupied - any factories are completely destroyed.
Remember to remove the [overheat](#overheat) token after any attack where you don't [control](#glossary) the hex.

## Overheat
*Significant effort can cause mechs to overheat. You'll need to let them idle before they can be used.*

Mark target hexes for your [Explore](#explore) and [Annex](4-annex) actions with an overheat token.
After your turn has completed, if you don't control the hex, remove the overheat token you placed.

All mechs in a hex marked with an overheat token are overheated.
Overheated mechs cannot leave and cannot perform any "With mech" action ([Develop](#develop), [Coordinate](#coordinate), [Explore](#explore), [Annex](#annex), and [Scan](#scan)).
Moving **into** an overheated area is allowed - you may attack or reinfoce areas with overheated mechs.

Remove all overheat tokens from the board at the start of each [morning](#morning).

## Objectives
*Your technology wasn't designed with this particular planet's environment in mind. Gather more training data to make actions more efficient.*

Completing objectives can only be done via the [Streamline](#streamline) action, which will let you immediately [upgrade](#upgrades) a [card](#cards).
See the [list](#objective-list) below.

### Upgrades
*Every action is ultimately software. Deploying patches after release is standard procedure.*
Upgrades are per [card](#cards).
Upgrading involves ~~grabbing the higher number card of that name~~ adding a tally to your card and placing an objective token of your color on that objective to mark it off.

You may upgrade any card, regardless of whether it has been played today.
Upgrading the currently played card does not change your current action.

There are a total of 27 possible upgrades, but only 17 objectives.

When objective tokens run out, [game ends that **night**](#game-over).

### Objective List
* **Centrist**: [Control](#glossary) the center hex
* **Tourist**: [Control](#glossary) a hex 7 away from your starting hexes
* **Rogue**: [Control](#glossary) a hex in an enemy's [home row](#glossary)
* **Technologist**: Fully expand a factory
* **Specialist**: Fully upgrade a card
* **Settler**: [Control](#glossary) 15 hexes (4p, 2p: 30, 3p: 20, 5-6p: 10)
* **Linear**: [Control](#glossary) a straight line of 5 hexes (4p, 2p: 7, 3p: 5, 5-6p: 4)
* **Inhospitable**: [Control](#glossary) a black hex
* **Entrenched**: [Control](#glossary) 4 [home row](#glossary) hexes (secondary-advantaged)
* **Innovative**: [Unlock](#glossary) a secondary that includes a color you didn't start with (primary-advantaged)
* **Flexible**: [Unlock](#glossary) all secondaries (secondary-advantaged)
* **Strategist**: Terraform 3 times
* **Capitalist**: Control 4 factories
* **Ruthless**: Successfully invade
* **Generalist**: Upgrade a card, place a scanner, and expand a factory
* **Surveyor**: Place 3 corner scanners
* **Hoarder**: Have 15 unspent alloy

## Game Over
Game ends on the night of the day that we run out of objective markers?
Or someone completes 10 objectives? 
How much? No idea - 2-3: 8/p, 4: 7/p, 5-6: 6/p
^ These are probably too long.

### Scoring
*Surveying is zero-sum - miners and colonizers will buy from whomever has the most complete data set. The winner is the faction with the most hex data uploaded back to the Core Worlds.*

Each unique hex covered by a scanner is worth 1 point.
Ties are broken by number of upgrades.

## Glossary
* **Control**: Any [mech or factory](#units) controls the hex it occupies.
* **Enemy**: Any opponent's faction. Unplayed factions are not enemy factions.
* **Expansion**: Each expansion on a factory counts as one extra unit and is capable of adding one primary color modification to mechs. An unexpanded factory is the base level, counts as one unit, and can only produce white mechs.
* **Home row**: The set of 4 outer edge hexes for each faction, including unplayed factions and your own faction.
* **Unit**: A [mech or factory](#units)
* **Unlock** a color: Control a mech or a hex with that exact color.

## Questions
* What should end the game?
* Should you get a fixed number of scanners and running out ends the game?
* Should upgrading give you more scanners?
* Should combat favor defenders more?
* Should anything to do with your color be easier? Unit discount, extra harvest, farther teleport?
* Is there a cooler word for "upgrades"? I want it to be most software themed, like builds / releases / patches, but those don't really start from zero like upgrades do.
* I think scanner upgrades might be too necessary, is it too slow?
* What should make each faction different?

* Movement is super hard - should the map be more biome-based with regions of similar color? 
	* Yes, and I fixed it
* How should mobilize work? The map isn't really big enough for move speed 4.
	* Fixed.
* Should units automatically get your color for free?
	* No, doesn't make sense with primary vs secondary
* How do you gain a new color? Should the cost of adding a second or third color be more than adding a first color?
	* Gain through factories - keep it simple, fewer things to remember, each one costs 1 more
* What color should factories spawn with? How should you upgrade factory colors?
	* factories spawn with a single primary color, and upgrading unlocks more colors
* What color should units spawn with?
	* mechs can spawn with any combination of colors based on the factory that created them
* Dragon runes as objectives or end game scoring?
	* Cool, but then becomes more about persistent military might, which I don't want
* You drop down claim markers / experience tokens. Whoever has the fewest at end of game wins?
	* I like scanners slightly more because they require action and not combat vs just yolo combat pushing
* Colors aren't white primary secondary black, it's exact and off-by-one, where you can expand into similar territories (terra mystica style)
	* Boooo
* Upkeep mechs - 1 plus one per mod
	* then hexes have to produce more per color, and hexes have to produce like 3 base so each hex still nets 3? but then having 2 black units on a black hex net 0, that's terrible. 
	* upkeep mechs: 0 plus 1 per mod? hexes produce 4 base
	* Does upkeep do anything? You just have to scale production so that upkeep matches.
	* Maybe you don't need a limit or upkeep, since people are incentivized to spread out anyway.
	* Mechs are fundamentally workers, not fighters, so they kinda need to be the thing producing resources.
* night mech limit by controlled hexes - 3 * #hexes?
	* probs not since you're not even strongly incentivized to own hexes after deploying scanners
* can people place scanners in the same corners?
	* Yes

## Good and Bad
I like the 4 turn round setup.
I like the color requirements to expand, and the generalization penalty of more expensive units since they don't attack better.
I like terraforming to make defending / expanding easier.
I like teleporting / tunneling color to color to skip over terraformed defenses and reach the center.
I like the flavor concept of mechs plus mods to enter hexes hostile in different ways.
I like the base concept of combat and area control.
I like deterministic combat and MAD.
I like that permanent area control isn't the goal.

I dislike 8 different actions and having to explain how to pick them up - complexity penalty.

I dislike that more hostile hexes aren't more rewarding somehow.
I dislike that your faction color doesn't matter somehow.
I dislike that combat doesn't favor defenders.

## Alternate ideas
* You are organisms, and you have to adapt to terrain that's +/- one color off?
* You are claiming territory splatoon style?
* 61-hex map instead of 100? (hexagon of sides of 6 hexagons)

## Base principles
I want a color-based area control game engine-building game where area control isn't the win condition.

I like the trophy placement win condition.
I like the four turn days / years with different effects.

I don't know how to structure actions to be balanced.
I don't know how to make an engine builder.

I need to decide what the "engine" component is.
What drives the game?
I want it to be the board, not a deck to build or something.

so how can you build an engine with only one material type you gather from the board and objectives you complete?

I don't want to have multiple material types - that's too much like scythe or rune wars.

## Demoing
Drop into partially completed game - each player has different upgrades, starting alloys, setup, etc.




one factory on the first in

forced asymmetry with groups of 6 hexes to start

with 3 players take out the outer ring

it's a puzzle and not as much a game

to make it simpler, it needs to be more random

could do point salad based - secret objective or secret way to earn points per faction

scan upgrade could be "scan twice"

streamline should be automatic every morning

not completing an objective every turn felt like losing


make certain cards more incentivized by bonus points (upgrading certain cards gives bonus points)



17 objectives is hard to track
Scythe goals match an action very clearly and you need to do it all of the times, but this has a variable number for each objective

top-bottom

it would be nice to make the core 3 (scan streamline quarry) not played every time



