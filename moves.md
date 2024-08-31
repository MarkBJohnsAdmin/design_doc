# Pokemon Moves

Each Pokemon species has what's called a `movepool`, which is a list of every Move that a Pokemon can possibly know. There are a variety of ways a Pokemon can learn a Move, and even multiple ways that a Pokemon can learn the same Move. 

## Level Up

The most common and intuitive way that Pokemon learn Moves is by leveling up:

### Charmander Level Up
| Level | Attack Name | Type |
|:-|:-|:-|
| ---- | Scratch | Normal |
| ---- | Growl | Normal |
| 7 | Ember | Fire |
| 13 | Smokescreen | Normal |
| 19 | Rage | Normal |
| 25 | Scary Face | Normal |
| 31 | Flamethrower | Fire |
| 37 | Slash | Normal |
| 43 | Dragon Rage | Dragon |
| 49 | Fire Spin | Fire |

The `----`  values show that every Charmander knows the Moves Scratch and Growl immediately. Upon leveling up to level 7, Charmander learns Ember, level 13 learns Smokescreen, and so on. Different Pokemon learn different Moves upon leveling up, even different Pokemon within the same evolution chain:

### Charizard Level Up

| Level | Attack Name | Type |
|:-|:-|:-|
| ---- | Scratch | Normal |
| ---- | Growl | Normal |
| ---- | Ember | Fire |
| ---- | Smokescreen | Normal |
| 7 | Ember | Fire |
| 13 | Smokescreen | Normal |
| 20 | Rage | Normal |
| 27 | Scary Face | Normal |
| 34 | Flamethrower | Fire |
| 36 | Wing Attack | Flying |
| 44 | Slash | Normal |
| 54 | Dragon Rage | Dragon |
| 64 | Fire Spin | Fire |

Note that even though a lot of the Moves are the same, there are additional Moves, and they're typically learned at higher levels. As a general rule, weaker evolutions learn strong moves faster as a trade-off for keeping your Pokemon weaker longer. Sometimes there are even powerful moves you can only learn by not evolving your Pokemon until several levels after they're capable of it.

## TM and HM Attacks

Pokemon also has items called `Technical Machines` and `Hidden Machines`. The mechanics have changed throughout the different games, but as a general rule, TMs are a single use item the teaches a single Pokemon a Move, and is then consumed. HMs are similar, but they are not consumed after being used. Additionally, a Move learned by an HM cannot be unlearned without special NPCs who are capable of forcing them to learn them. This is because the HMs have the moves that Gym Badges allow Pokemon to use outside of battle, and the game wants to make sure you can't soft-lock yourself somewhere, such as getting to an area you can't leave without surfing across the ocean, but removing the move Surf. This is also HMs are not consumed, so releasing or trading your only Pokemon who knows an HM Move can't prevent you from accessing certain areas.

| Machine #| Attack Name | Type |
|:-|:-|:-|
| TM01 | Focus Punch | Fighting |
| TM02 | Dragon Claw | Dragon |
| TM03 | Water Pulse | Water |
| ... | ... | ... | 
| TM49 | Snatch | Dark |
| TM50 | Overheat | Fire |
| HM01 | Cut | Normal |
| HM02 | Fly | Flying |
| HM03 | Surf | Water |
| ... | ... | ... |
| HM07 | Waterfall | Water |
| HM08 | Dive | Water |

A Pokemon's movepool includes all Moves that they can learn via Machines, and is often the simplest - if not the only - way to reliably teach your Pokemon powerful and consistent moves.

## Egg Moves

If a male and female Pokemon (or a Pokemon and a Ditto) are left unattended at a daycare, for totally unknown reasons that Nintendo will never explain, they'll produce an egg. After a certain amount of time in a trainer's party, the egg will hatch into whatever the first stage evolution of the female's (or non-Ditto's) species was. In addition to being useful for getting more an a rare or difficult to obtain Pokemon, the baby Pokemon can also inherit Moves from the father. There are several Moves that Pokemon can only learn using this method. For example, Belly Drum, Outrage, and Beat Up are all strong options on Charizard for various strategies, but they don't learn any of these Moves normally, and they don't exist as TMs or HMs. The only way for Charizard to learn these Moves is for a male Pokemon that knows them to breed with a female Charizard, and the egg will come out learning whichever move you passed down.

## Move Tutors

The rarest version of Move learning is by dedicated Tutors, which are NPCs that have a single Move or collection of Moves that they can teach a Pokemon to use. Sometimes they'll only teach a Move one time per game, sometimes they'll only teach a certain category of Pokemon, and sometimes they'll take some form of currency in exchange for teaching a Move, but they're generally a way to give Pokemon very useful Moves, balanced by scarcity or by being a reward for grinding.

## Movepools

Movepools, along with Stats and Abilities, are another way that Pokemon are balanced. Some Pokemon look incredibly powerful on paper, but are all but useless because they don't know any Moves that let them play to their strengths. Generation 3 Crawdaunt is a great example, as it has a very good Water and Dark typing, as well as an impressive Attack stat:

```py
crawdaunt = {
  "hp": 63,
  "attk": 120,
  "def": 85,
  "spatk": 90,
  "spdef": 55,
  "speed": 55
}
```

In Generation 3, all Water and Dark type Moves had their damage calculated with the user's Special Attack, which for Crawdaunt is considerably lower than its Attack, so any of the Water and Dark type Moves it learns were considerably weaker than they could be, and it didn't know very many good Moves of other types, so it ended up being a very poor competitive Pokemon.

On the other hand, Smeargle has been a very good competitive Pokemon in every generation, occasionally even banned from standard play for being too strong, despite its stats looking like:

```py
smeargle = {
  "hp": 55,
  "attk": 20,
  "def": 35,
  "spatk": 20,
  "spdef": 45,
  "speed": 75
}
```

This is because Smeargle has a Move called Sketch, which lets him copy and permanently learn whatever your opponent's last move was. You can use this on a teammate in double battles, meaning that Smeargle can learn (almost) every single Move in the franchise. Even with garbage stats, having access to every single utility Move in the game can dramatically swing a battle in your favor.

## Mechanics

### Damaging Moves

Pokemon Moves have a handful of universal attributes:

| Name | Power | Accuracy | Priority | Class | Type |
|:-|:-|:-|:-|:-|:-|
| Tackle| 40 | 100 | 0 | Physical | Normal |
| Vacuum Wave | 40 | 100 | 1 | Special | Fighting |
| Extreme-Speed | 80 | 100 | 2 | Physical | Normal |
| Fake Out | 40 | 100 | 3 | Physical | Normal |

The `power` attribute is straightforward, it's just how strong a move is. `Accuracy` is also straightforward, it's the percentage chance that, barring any outside influence, a move will connect with the opponent instead of miss. 

`Priority` is a way to overcome lower speed stats. Pokemon isn't turn-based in that Pokemon A moves, then Pokemon B moves, and so on. It's turn-based in that Pokemon A and Pokemon B move at the same time. The order in which Moves are executed depends on each Pokemon's Speed stat, with the higher value going first. However, this is only the case when the opposing Moves have the same priority value. So if Pokemon A has a Speed stat of 102 and Pokemon B has a Speed stat of 98, and both use Tackle, Pokemon A will move first. But if two opposing Moves have different priority values, the Speed stats are ignored completely and the higher priority Move goes first. Every Move in the list above will outspeed Tackle, Extreme-Speed will outspeed Vacuum Wave, and Fake Out will outspeed everything.

The `class` attribute had a major rework between the 3rd and 4th generation, but it still did the same thing: the class determines if a damage dealing Move uses the Attack stat to calculate damage, or the Special Attack stat. For Gen 1-3, whether a Move dealt Attack damage or Special Attack damage was based on the Move type - Fire Punch did Special Attack damage because it's Fire type, Shadow Ball did Attack damage because it's Ghost type. From Gen 4 onward, each Move handled this distinction independently - Fire Punch does Attack damage because it's a physical Move, Shadow Ball does Special damage because it's energy based. So above, Vacuum Wave calculates damage with the user's Special Attack, and all other Moves use Attack. There's a third class called "Status", which handles all non-damaging Moves.

The final universal attribute is `type`, which is the elemental type the move uses. This has two purposes. 

The first, matchups, will double or half (and sometimes even negate) the damage a Move does based on the elemental type of the opponent. Take Vacuum Wave, a Fighting type Move. Against an Ice type or Rock type, both of which are weak to Fighting, the base power of Vacuum Wave is boosted to 80 instead of 40. Against Flying and Poison, both of which resist Fighting, the base power of Vacuum Wave becomes 20. This effect also multiplies against Pokemon with two types. Against a Pokemon that is both Rock and Ice type, Vacuum Wave now has 160 base power, and against a Pokemon that is both Flying and Poison, it only has 10. Against a Ghost type Pokemon, which is immune to Fighting type attacks, Vacuum Wave will do nothing.

The second purpose of Move types is to set up `STAB`, or "same type as" bonus. If a Pokemon uses a Move with the same type as itself, that Move's power is given a 1.5 times bonus. Meaning any Fighting type Pokemon that uses Vacuum Wave is actually using a Move with 60 base power. This bonus takes place before any other matchup calculations, so instead of doing 80 or 160 against vulnerable Pokemon and 20 or 10 against resistances, a Fighting type Pokemon is doing 120 or 240 and 30 or 15. 

### Status Moves

The "Status" class encompasses everything that doesn't directly deal damage, so it's very hard to pin down, but there are a handful of very common use cases:

#### Stat Boosts / Drops

Your stats are calculated based on a variety of invisible values I won't get into here, but those stat calculations are set at the beginning of each battle. But while in battle, all stats, besides HP, can be temporarily modified by putting it in a different `stage`. All stats are in stage 0 by default, with 6 being the highest stage and -6 being the lowest stage. Various Moves can raise and lower certain stats by placing them into a different stage. Accuracy and Evasion also have the same stages, with Accuracy raising or lowering your own Move's accuracy attributes and Evasion raising or lowering your opponent's Move's accuracy.

#### Healing

Several Moves do nothing but heal the user, with some healing a static percentage of the user's health, some having different percentages based on battlefield conditions, and some actually being attacks that heal based on a percentage of the damage your caused.

#### Status Conditions

There are various status conditions that give Pokemon debuffs, and the most reliable way to cause those effects are with Moves designed to inflict them.

| Status | Effect |
|:-|:-|
| Confuse | Chance to inflict damage to yourself rather than the enemy |
| Attract | Chance to be too infatuated to attack |
| Poison | Lose a static percentage of health after each turn |
| Badly Poison | Lose a incrementally increasing percentage of damage after each turn |
| Burn | Lose a static percentage of health after each turn, damage from contact moves is halved |
| Paralyze | Speed stat is reduced, chance to be immobilized and miss a turn |
| Sleep | User is asleep and can't use any moves until they awake |
| Freeze | User is frozen and can't move until they thaw, or are attacked by a Fire type attack

The are both Moves that directly and explicitly cause these status effects, as well as Moves that deal damage with an additional percentage chance to cause the status as well as the damage.

#### Battlefield Conditions

Some Moves target the battlefield instead of the opponents directly. The three main categories of battlefield conditions are hazards, weather, and terrain. 

Hazard Moves place physical objects on the field that damage Pokemon each time they are switched in. Spikes can be placed in three layers, dealing 12.5% of the opponent's total health with one layer, 16.67% with two layers, and 25% with all three. Toxic Spikes will cause the Poison status to each switch in with one layer and Badly Poison status with two layers. Both only work on grounded Pokemon. Stealth Rock, the strongest of the hazards, is treated like a typed Move, so type matchups are calculated.

| Rock Matchup | Damage (% of max HP) |
|:-|:-|
| x2 resist | 3.125 |
| resist | 6.25 |
| neutral | 12.5 |
| weak | 25 |
| x2 weak | 50 |

Entire Pokemon have become effectively useless in certain generations just because they were weak to Rock types and Stealth Rock was so easy to set up, especially since it hit the Flying types that avoided the other hazards particularly hard.

Weather setting Moves put weather on the field that help certain elemental types, usually at the expense of others.

| Weather | Effect | 
|:-|:-|
| Sun | Doubles Fire type attack damage, halves Water type damage |
| Rain | Doubles Water type attack damage, halves Fire type damage |
| Sandstorm | Deals 6.25% of total health to every Pokemon the isn't Rock, Ground, or Steel type, boosts Special Defense of Rock types |
| Snow | Boosts the Defense stat of Ice types |

In addition to universal changes, specific Moves and Pokemon also benefit from certain weathers, and it's common to base entire teams around them.

Terrains are like weather, but they only effect grounded Pokemon.

| Terrain | Effect |
|:-|:-
| Electric | Grounded Pokemon can't fall asleep, Electric attacks are boosted |
| Grassy | Small amounts of health are gained after each turn, Grass attacks are boosted |
| Misty | Pokemon because immune to status conditions, Dragon attacks are halved |
| Psychic | Priority moves are disabled, Psychic attacks are boosted |

While less polarizing than weather, there are also Moves and Items that interact with terrains, so these are also common strategies to build teams around.

## Conclusion

There are entirely too many moves, and even move categories to get into in one paper, but there are a few general concepts you can use as a jumping off point. Note that even though most Pokemon have a massive movepool, each Pokemon can only know four moves at a time. 

A lot of Moves are also bad by design, as they're meant to be placeholders for weaker Pokemon until they level up to learn better versions. Flamethrower, a Fire type Special move with 90 base power, 100 accuracy, and a 10% chance to burn is a strict upgrade to Ember, which has all the same attributes but only 40 base power, so the only reason to run Ember is because you're only level 7 and you haven't learned Flamethrower yet.

Pokemon also have architypes, so it's generally understood what role they play in battles. This also helps to simplify decisions on what Moves your Pokemon should know, while also letting you know what an opponent might not be expecting you to know.

