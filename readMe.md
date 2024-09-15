# Design Doc

This project is a creature-collector RPG in the style of Pokemon, but designed to address what I feel are elements of the franchise that have aged poorly or weren't designed well from the start. The aim is to overhaul the battle mechanics with a more unique, more "fair" system, and address lore and logic related issues with the overworld. The era of Pokemon I'm trying to capture is between Gen 3 (Ruby, Sapphire, Emerald, Firered, Leafgreen) and Gen 4 (Diamond, Pearl, Platinum, Heartgold, Soulsilver), but ultimately this project should feel like a spin-off of those games rather than a copy or sequel. 

## Table of Contents

+ [Overworld](#overworld)
+ [Battle Mechanics](#battle-mechanics)
  + [Issue - Individual / Effort Values and Natures](#issue---individual--effort-values-and-natures)
  + [Solution - Direct Stat Manipulations and Enchantments](#solution---direct-stat-manipulation-and-enchantments)
  + [Issue - Abilities and Items](#issue---abilities-and-items)
  + [Solution - Enchantments](#solution---enchantments)
  + [Issue - Sweeping, Stalling, and Power Creep](#issue---sweeping-stalling-and-power-creep)
  + [Solution - Slow Progression, No Regression](#solution---slow-progression-no-regression)
+ [Battle System](#battle-system)
  + [Frontline and Backline](#frontline-and-backline)
  + [Hazards](#hazards)
  + [Weather](#weather)
  + [Type Attributes](#type-attributes)
  + [Move Types](#move-types)
  + [Strategies](#strategies)

# Overworld

[home](#table-of-contents)

## Concept

The game should feel very similar tonally and mechanically to Pokemon, with a pixelated, grid-based overworld. The biggest change that will effect every part of the overworld is that the sci-fi aspects of Pokemon will be replaced by pure fantasy elements. There will be several one-to-one mechanics to match Pokemon's, but they'll be given new in-game explanations and ways to access them.

### Pokemon vs Familiars

Unlike Pokemon, this world doesn't have powerful, elemental monsters gathering around by default. There are monsters, and they are dangerous if you're unprepared to face them, but they aren't nearly as threatening as a average Pokemon would be. Instead, these `beasts` have no typings and basic attacks, and the random encounter battles with them will be a very simplified, 1 vs 1 system instead of the more complex 3 vs 3 used for the rest of the game.

Beasts are present in all biomes, and have evolved to suit their environments, but are still `null type` in the wild. This makes the wild encounters extremely simple, easy to manage, and easy to ignore, leaving the complexity to the person vs person battles. Beasts can still be captured, and in a very similar way to Pokemon, and when they are, the beasts will go through an `awakening`. Awakened beasts are given their types, access to their move pool, and access to other enchantments. Each species of beast has present attributes, so if you capture a beast and it becomes a Grass and Earth type, all beasts of that species you caputre will also be Grass and Earth type, with the same stats and move pool. The customization happens later.

Beasts that have been awoken become `familiars`, and you have access to them for the remainder of the game.

### Pokeballs vs Runes

Instead of unexplained technology, the familiars are captured within magic `runes`. Runes vary in quality but are widely available, considered useless by the general public. This is because only sorceres are capable of using them to awaken beasts, and this world's government is dead set against letting the general public understand how familiars work. Every beast has intrinsic magic powers, which allows them to resist being captured, and it's the combination of the beast's instrinsic magic and the magic channeled through the runes that awakens them.

These will work the same as Pokeballs, with different kinds of runes offering better catch rates or working against specific types of beasts:

+ Iron Rune - Pokeball
+ Bronze Rune - Great Ball,
+ Silver Rune - Ultra Ball,
+ Obsidian Rune - Master Ball

And so on.

### PC vs Runebook

In Pokemon, you can carry six Pokemon in your bag, and more than most people will ever need in effectively Cloud storage. Instead of having biological creatures randomly digitized and rematerialized, familiars will have their energy tied to the Rune they were awoken with. Their souls are tied to the rune and can be recalled to them at any time. Your runes are also stored in a Runebook you keep on you, allowing you to store and organize all of your familiars. This also gives you permanent access to every familiar you capture, rather than needing to find a Pokemon Center or other building with PC access.

Pokemon Centers are also replaced with White Mages, a secret order that has learned to purify runes, completely healing the familiar tied to them. White Mages will purify your entire Runebook when asked to, and they have secret members in every tow or city.

Familiars in your party are determined by your armor. The player's armor will have slots for runes, and the runes in those slots will be the current party, so you still have to set up a team instead of throwing your entire Runebook at your opponent.

### Items vs Enchantments

Instead of the physical objects that Pokemon hold, you can enchant your runes with various gemstones. The gemstones act as a lens the familiar passes through, altering their attributes as it does. Adding a gemstone to your rune is mechanically the same as equipping a Pokemon with an item, but the attribute/ability the gem gives you is imbued within the familiar itself.

Enchantments also take the place of Abilities, Natures, and EVs, which I go over more in the "Battle Mechanics" section.

### Gyms and Elite Four vs Nobles and the King

Instead of a carefully themed progression system that rewards the player badges, this world is actively going after you. You become a fugitive when you accidentally awaken a familiar prophesied to destroy all tyrants, and the corrupt king of this realm wants to stop you at any cost. Rather than fighting Gym Leaders to test your progress, you have to fight the king's nobles, who are set on taking you out to gain the king's favor. As you become more and more of a threat, the forces set against you become stronger and stronger, until ulitmately you have to take on the kingdom itself.

This will feel very similar to the Gyms and Elite Four system, and it should, but this adds a sense of urgency, and allows the game to maintain and elevate conflict without having a 10 year old take on various terrorist organizations and whatever eldritch god they're trying to utilize.

### Hidden Moves (Overworld Moves) vs Artifacts

In earlier Pokemon games, progress in the Overworld was locked behind Hidden Moves, which were moves specifically designed to work both in battle and outside of battle. The most common examples are Strength, which lets you move giant boulders, Cut, which lets you cut down trees that are blocking your path, and Surf, which lets you travel across bodies of water. In addition to needing to access the moves, you also can't use them outside of battle until you get a particular Gym badge.

I never liked this, both as a mechanic or a concept, as there seemed to be no reaon why a Pokemon with swords for arms couldn't cut down a tree until a badge told him it was okay. Hidden Moves were also almost never the best option to use in battle, so most playthroughs ended up with an "HM Slave" in your party, a low-leveled Pokemon whose only purpose was to learn multiple hidden moves so you could move through the overworld. Later games solved this by giving you Pokemon that had these traversal methods already set up, but this still seemed clunky and still included multiple Pokemon in your party that aren't for battling.

Instead of having an HM Slave, my game will make the player the HM Slave. Instead of having a move called Cut that can cut down trees, but only after a certain badge is obtained, you now have an `artifact`, or an object granted some sort of power. So instead of being able to use moves outside of battle after beating a gym, you get access to an artifact after defeating a noble, in this case, a sword that allows you to cut down hazards in your path.

This has the same utility of locking player progress behind different acheivements, but it makes more logical sense, and makes it so you permanently have access to this new traversal method instead of needing to tie it to a specific set of familiars.

# Battle Mechanics

As this game was imagined foremost as a way to address the shortcomings of competetive Pokemon, the battle system is what I'm most concerned with getting right. There are several hidden mechanics that dramatically change a Pokemon's viability in battle, as well as visible mechanics that are nonetheless tedious and frustrating to manage, so the first step in my system is to address those.

## Issue - Individual / Effort Values and Natures

[home](#table-of-contents)

In Pokemon, each stat has an `Individual Value` (IV) that changes the in-battle value of that stat. For example, the base stats for Charizard are as follows:

```py
charizard_base_stats = {
    "hp": 78,
    "attack": 84,
    "defense": 78,
    "special-attack": 109,
    "special-defense": 85,
    "speed": 100
}
```

At level 100, before IVs or EVs are implemented, these base stats translate into real stat values of:

```py
charizard_real_stats = {
    "hp": 266,
    "attack": 173,
    "defense": 161,
    "special-attack": 223,
    "special-defense": 175,
    "speed": 205
}
```

IVs are a hidden value applied to each stat, ranging from 0 to 31. The above Charizard stats represent and IV of 0 in every stat, but this is what maximum IVs would look like:

```py
charizard_max_ivs = {
    "hp": 297,
    "attack": 204,
    "defense": 192,
    "special-attack": 254,
    "special-defense": 206,
    "speed": 236
}
```

While there are niche situations where a lower stat value is preferred, in general all competitive Pokemon will want the maximum of every stat. The issue is that these IVs are randomly generated. Future generations introduced several in game ways to manipulate these values, but this just adds a layer of complexity and grinding to address an issue that shouldn't need to be an issue in the first place.

`Effort Values` (EV) are a similar concept, but the trainer does have more explicit control over the results. Every Pokemon has a hidden value of EV points that they reward their opponent after being defeated in battle, called and `EV yield`. Charizard, for example, has an EV yield of 3 for Special Attack. So for every Charizard you defeat in battle, 3 EVs are rewarded to your Special Attack stat, which means your Special Attack stat increases at a higher rate as you level up.

While not random, Effort Values are more complex than IVs, as instead of being a randomized multiplier, it's a resource you have to manage. You can have EVs in any stat you want, but you can only have a maximum of 510 distributed among all six stats. In addition, each individual stats can only have 255 EVs. And to add even more complexity, 252 EVs is the maximum amount that will actually influence that final stat value. This is because every 4 EVs in a stat will contribute to 1 real stat point by the time the Pokemon reaches level 100, so the 3 point difference between 252 and 255 EVs won't translate into the stat being any higher. As a result, the general strategy is to maximize your two most important stats, and give an extra point to any other stat that might benefit, leading to an EV distribution of 252/252/4 instead of 255/255.

```py
charizard_ev_boost = {
    "hp": 298, # 4 EVs
    "attack": 204,
    "defense": 192,
    "special-attack": 317, # 252 EVs
    "special-defense": 206,
    "speed": 299 # 252 EVs
}
```

In addition to the process of getting the EVs being complex and tedious, the caps on the values are weird and force you to leave at least 2 of them on the table, as you can get those points, but they won't translate into an actual stat boost. 

`Natures` are the final stat manipulation mechanic, where each nature will give a 10% boost to one stat, in exchange for a 10% decrease in another stat. Charizard will typically rely completely on its Special Attack stat, so its Attack stat isn't important. In fact, there are actually benefits in battle to have an Attack stat you aren't using to be as low as possible. So in addition to getting the correct IV spread and training to collect the EV spread, you also want to give your Pokemon the optimal nature. In this case, it's the *modest* nature, which boosts Special Attack in exchange for reducing Attack.

```py
charizard_no_boosts = {
    "hp": 266,
    "attack": 173,
    "defense": 161,
    "special-attack": 223,
    "special-defense": 175,
    "speed": 205
}

charizard_ivs_evs_modest = {
    "hp": 298, # 31 IVs, 4 EVs
    "attack": 155, # 0 IVs, Modest drop
    "defense": 193, # 31 IVs
    "special-attack": 348, # 31 IVs, 252 EVs, Modest boost
    "special-defense": 206, # 31 IVs
    "speed": 299 # 31 IVs, 252 EVs
}
```

In later games, Mints were introduced to override the boosts that Natures created, but outside of the Mints, natures were randomly generated, and finding a Pokemon with the right nature was just one more randomized chance you had to deal with while trying to get the correct IV spreads.

Note that because IVs and Natures are multipliers, it's objectively better to boost stats that are already good than it is to try and compensate for bad stats. Charizard's Attack stat only has an 18 point difference, despite losing all IVs and having a nature that reduces the end result by 10 percent. Even if you wanted to make Charizard a physical attacker by giving it 31 Attack IVs and an Attack boosting nature, this boosts the Attack stat to 244, which is only one more stat point than Special Attack is without any investment at all. The majority of boosting comes from EVs, which lets you add a static 63 points to any stat you want.

## Solution - Direct Stat Manipulation and Enchantments

[home](#table-of-contents)

The concept of IVs will be removed entirely. Pokemon's solution to randomized values was to add additional ways to undo that random generation and manipulate it from there, but I'd rather just avoid the problem entirely. There can still be cases where a trainer will want a stat to be lower than usual, but this will be addressed in a more efficient way.

Instead, all Monsters will have a basic stat distrubution, and their stats will grow at the same rate. As a result, all uninvested Monsters of the same species will have exactly the same stats at the same levels. However, EVs and Natures will be retooled for both simplicity and even more flexibility. The specific numbers are subject to change during playtesting, but the idea is as follows:

Instead of EV yields and EVs being tied to a specific stat, each Monster will have a pool of values called `potential`. Every level adds two points into this pool. At any time, these pools can be translated into a point for the stat of your choosing. This pool can be reset at any time, and because it's raw numbers instead of percentage boosts, you can decide to give your offensive Monsters better bulk, let your defensive Monsters hit harder, and give your tanks more speed to help them keep up with more aggressive battles, but you can also lean into your Monster's strengths by making them even better in the areas they already excel. You can also swap back and forth between these strategies to be better equipped for specific battles. In order to prevent min-max power creep, these values will still be capped at 75 points per stat, but given that it's a 1 to 1 relationship between potential points and stat points, there's no wasted values or ambiguity on how your Monster's stats are being improved.

Instead of Natures, the Runes that the Monsters are stored in can be `enchanted`. There are multiple types of enchantments, but this type of enchantment is for stat distribution. Instead of being random, all Monster have no enchantment by default, and when this type of enchantment is unlocked, you can choose which one you want and change them at will (likely for some in-game mana cost). This will not manipulate the growth of a stat, but rather change the stat directly. Whatever the current stat is - not including the boosts from potential points - will be either multiplied by 10% or reduced by 10%, depending on which enchantment you use on it. This ensures there's no penalty for changing the enchantment at higher levels.

While this normalizes the stat distribution of unboosted Monsters, it also gives a lot more flexibility on how the boosts are distributed by relying more on raw numbers rather than percentages. This prevents the power creep of current Pokemon games, where every modern Pokemon has completely min-maxed stat distrubutions and uses percentage multipliers to balloon those stat values into completey absurd numbers.

## Issue - Abilities and Items

[home](#table-of-contents)

While not quite issues, there's still some thematic concerns I want to address. As a refresher, `Abilities` are attributes that are unique to a Pokemon species that change the way they battle. For example, Bronzong, a part Steel type, is vulnerable to both Ground type attacks and Fire type attacks. However, Bronzong can have one of two Abilities, Heatproof or Levitate. The Heatproof Ability reduces the damage from all Fire type attacks by half, while the Levitate Ability adds a complete immunity to Ground type attacks. In either case, Bronzong has a new resistance or even immunity to types of attacks that now differentiate it from other Steel types. Similarly, Ghost type Pokemon are completely immune to Normal and Fighting type attacks, but Kangaskhan has the Scrappy Ability, which allows it to hit Ghost types with Normal and Fighting moves. This allows it to use `STAB`** boosted attacks against Ghost types, differentiating it from other Normal types.

** *"Same Type As" Bonus - which means if a Pokemon uses an attack whose type matches their own type, that attack's power is increased by 1.5*

Abilities also scale well beyond adding or removing type immunities, as they can boost stats, create weather, neutralize certain types of moves, increase the power of certain move classes, activate boosts or other effects in certain conditions, and too many other types of attributes to mention. While these are almost completely a net positive, there remains the issue of them being randomly generated. Each Pokemon has one or two possible Abilities, and most have a "hidden" Ability that you need to jump through some hoops to get (different hoops depending on the game or generation). This Ability is set when the Pokemon is generated, and again, while later generations have means of resetting these Abilities, I'd rather make this a built in feature.

One aspect the Trainer does (mostly) have full controll over, however, is a Pokemon's held `Item`. Like abilities, these give Pokemon different attributes in battle that, with a handful of exceptions, aren't unique to the Pokemon species itself. Just like Abilities, these attributes are too numerous to list, but they can add type immunities and resistances, boost stats, regenerate health, boost move strenghts, and so on. Some Items are always present, having small but consistent effects throughout the battle, while other are consumable, having a dramatic, important effect in battle, but only once, or at least until the Item is consumed. The problem with consumable Items is that, outside of specific post-game or PvP environments, those Items are gone once they're consumed. This can make the normal playthrough tedious, as certain battles can greatly benefit from an Item's attributes, but that Item can be difficult to obtain or have limited distribution. This again is fixed in later generations (expect for Berries), but it's something that took Pokemon a while to resolve and should be avoided in our game entirely.

## Solution - Enchantments

[home](#table-of-contents)

The second and third types of enchantments will take the place of Abilities and Items. Because it's an enchantment on a Rune instead of an instrinsic attribute or a physical object, they can be changed at will. Likely we'll keep the idea of a "hidden" Ability by making a third ability a strict upgrade that needs to be unlocked, but the player should be able to cycle through whatever Ability style attribute they want at will. For balance purposes, we still need to tie specific "abilities" to specific species, so this enchanment type will be the most unique. But outside of niche instances where a certain species has a stronger connection to one "item" over another, the "item" style enchantments will be universal, just like the "nature" enchantments are.

## Issue - Sweeping, Stalling, and Power Creep

[home](#table-of-contents)

The design choices Pokemon has made fundamentally make the competetive meta-game lean in a certain direction. This has always been present, but has been most clearly notable in the later generations. One of the most celebrated, and deservedly so, aspects of Pokemon battles is the ability to switch Pokemon as one of the turn actions, making it so no Pokemon is locked into a clearly losing battle, and a more defensive or better typed Pokemon can take over. This is important and gives competetive Pokemon singles a lot of its personality, but I feel it's an issue how mandatory it becomes. Certain Pokemon aren't just in a disadvantage in certain matchups, they are entirely useless. Pokemon can be incredibly strong, knocking out Pokemon that aren't explicitly defense in a single hit, and that single hit is granted for free when a trainer swaps a Pokemon out. Certain Items and Abilities have been introduced to solve for this by granting defensive utility when the Pokemon is at full health, but given the amount of new features added to chip away at health, including entry hazards that directly punish Pokemon for switching, it's not common for Pokemon to be at full health to utilize these benefits. A lot of the meta-game revolved around managing to switch in safely, which I feel takes away from the overall health of the meta-game by centralizing so much of the strategy around just showing up on the field rather than making bold moves or dramatically changing the game state. This state where it's so easy for Pokemon to lose completely in a single turn leads to three situations I feel have damaged Pokemon's gameplay and can't be resolved without a complete rework.

### Sweeping

Not only is the power level of Pokemon incredibly high and climbing, it's incredibly easy to boost those stats even higher, and by percentage multipliers that boost already strong stats even more than they help struggling stats. Each stat, expect for health, can be temporarily boosted or reduced by `stages` in battle. The default stage is 0, and the floor and ceiling are negative and positive six:

```py
stat_modifiers = {
    "-6": base * .25,
    "-5": base * .285,
    "-4": base * .33,
    "-3": base * .4,
    "-2": base * .5,
    "-1": base * .66,
    "0": base,
    "1": base * 1.5,
    "2": base * 2,
    "3": base * 2.5,
    "4": base * 3,
    "5": base * 3.5,
    "6": base * 4
}
```

This can get out of hand very quickly, especially when a Pokemon already has good stats. Take Sneasler, a newer Pokemon with a very respectable base Attack value of 130. With the proper IVs, EVs, and a boosting nature, this can reach a total stat value of 394. It's also incredibly fast, with a base speed of 120, than can become 339 with IV and EV investment, making it outspeed a huge majority of the meta-game. The attempt to balance it was giving it flimsy defensive stats and an exploitable defensive typing, but one of the major issues is that it knows a move called Swords Dance. If Sneasler manages to get on the field against a Pokemon that isn't prepared to take it on, it can use Swords Dance and boost its attack stat by two stages. As you can see above, 2 stage literally doubles the stat, and it doubles the actual calculated stat, not any growth modifiers. This means in a single move, one of the fastest Pokemon in the game manages to get a real Attack value of 788. This stat is absurd and can melt a majority of the meta-game in a single hit, connected to a Pokemon that can hit the majority of Pokemon before they have an oppurtunity to move. And if the opportunity presents itself against a Pokemon that maybe could withstand it, one more Swords Dance could elevate this already insane stat value up to 1182. But even in a meta-game too fast-paced to waste a turn boosting, there are items that boost stats immediately, such as a Choice Band giving a 1.5 times stat boost to your Attack in exchange for locking into a single move. While not as dramatic as Swords Dance, this still gives an incredibly fast Pokemon with amazing coverage moves an immediate stat value of 591 just for entering the field.

There are ways around this, as there literally couldn't be a competitive meta-game if there wasn't, but I personally don't think it's healthy to have a meta-game that has to account for rapid and dramatic stat increases that can win entire games in a single well placed move, especially when it's not especially difficult to use the move. The competive community's response has often been to ban Pokemon that are too problematic, but this problem could be avoided entirely if the the stats weren't so extreme and volatile.

### Stalling

On the opposite end of the spectrum, teams can focus on shoring up their defensive stats and trying to wait out the other team instead of taking them head-on. There are defensive boosting moves just as strong as offensive boosting moves, and those being used on Pokemon that are already bulky can have similarly dramatic increases. Pokemon also has a lot of incredibly strong health regeneration moves, abilities, and items that, even after attempts to nerf them, are still incredibly powerful options that can make it incredibly difficult to remove certain Pokemon without setting up equally absurd damage dealers. The strategy to still win while stalling is to set up things like entry hazards that hurt enemy Pokemon as they switch in and status conditions that whittle health down over time, leading to long and stressful wars of attrition.

### Power Creep

The more Pokemon get made, the harder it is to distinguish the newer, unestablished ones from the well known prior ones. One of the easiest ways to make them stand out is by making them stronger and stronger with each subsequent generation. This isn't unique to Pokemon, but given how Pokemon works, it seems especially egregious with them. In older generations, Attack and Special Attack where tied to types rather than the type of move it was (Fire Punch was Special Attack because it's fire, Shadow Ball is Attack because it's Ghost). From Gen 4 onward, it's determined by what kind of move it is (Fire Punch is Attack because it's physical, Shadow Ball is Special Attack because it's energy based). Neither one of these are intrinsically good or bad, but the issue lies on how Pokemon has tried to balance this.

Tyranitar, a Rock and Dark type, was the best Pokemon in Gen 3, with a very good Attack stat and a decent, but not great Special Attack stat. But it also had a huge variety of Special moves it could learn to cover bad matchups for its teammates, especially in using Special based Dark moves to handle Ghost types. But to do so effectively, you had to invest in your weaker Special Attack stat in order to do so, taking away from boosting its defenses or speed and making it more vulnerable in exchange for having more ultility. From Gen 4 onward, Tyranitar remained a solid option, but the introduction of Attack-based Dark type attacks removed the need to balance your stat distribution, letting you invest everything into Attack and Speed/Defenses. While this still works, and a lot of people welcomed the change, this reduce how much you could customize it. Nothing is stopping anyone from trying to make a Special Attack focused Tyranitar, but it will be objectively less effective than leaning into its more obvious strengths.

As more Pokemon got created, it became more clear that balanced Pokemon are obviously worse than Pokemon who are extremely skewed in one direction or the other, and the easiest way to make the newer ones more interesting than the last is to just keep making those numbers bigger and bigger. This leads to Pokemon like Metagross, who is in a special class of Pokemon called "psuedo-legendaries" for how high their stat distribution is, being in a competitive tier called "Under-Used" for Pokemon that aren't strong enough for basic competition. Meanwhile the aforementioned Sneasler, who has objectively bad stats outside of Attack and Speed, was literally too powerful for the basic competetive tier and had to be banned into the "Ubers" tier. Metagross is a much more balanced, interesting, and customizable Pokemon than Sneasler, and ended up punished for it.

## Solution - Slow Progression, No Regression

[home](#table-of-contents)

### Lower Power Levels

The power level of this game will be dramatically lower than Pokemon's. The damage calculation will be reworked so that even boosted, powerful moves will be all but incapable of wiping out opponents in a single hit. This isn't to say it won't take out huge chunks of health, but the idea is that it should always take more than one mistake to lose a game. Instead of relying on a single setup and speed running the rest of the fight, you have to manage several resources and battle states to take out opponents over time. Stat boosts will still be in the game, and will actually be improved in that they no longer go away once a Monster leaves the field, but in exchange, they can only gain or drop 2 stages, and will completely cap at 1.5 and 0.5 times the stat value.

### Permanent Progress

In exchange for it being impossible to break through opponents with single, powerful moves, health regeneration is rare and risky for moderate reward. The hazards system will also be reworked to deal minor, but constant damage rather than larger chip damage only upon entering the field. Bulky Monsters will still exist to facilitate set up strategies and redirect aggro, but will no longer sit on the field healing off damage every turn and preventing meaningful progress.

This combination of strategies removes both the breakneck sweeping and glacial stalling of the Pokemon franchise and replaces it with something like a hybrid of both. You can still use extremely aggresive Monsters and playstyles, but you have to devote some of your strategy and resources to not melting once the opponent attacks back, and you can still have a slower, methodical strategy, but you need to understand that you can't wait out the clock and you need to make offensive progress along the way.

## Battle System

[home](#table-of-contents)

This battle system does heavily borrow a lot of its concepts from Pokemon, as Pokemon is by no means a bad or incompetent franchise. The idea is to instead extend the basic concept into something less frustrating and polarizing by adding new mechanics.

### Frontline and Backline

The standard competetive format facilitated by the Pokemon Company is Double Battles, where each Trainer has four Pokemon in their party, with two on the field at any time. At the beginning of the turn, both trainers select one action per Pokemon. "Actions" can involve either using a move or swapping a Pokemon out for a different Pokemon in their party. At the beginning of the turn, switching happens first, and moves are executed in the order of each Pokemon's Speed stat. Moves can target a single opponent, both opponents, their ally, all three other Pokemon, the battefield itself, or the user itself. Smogon, a fan-governed competetive format, uses single battles, which function mostly the same, but without having to manage a teammate and two opponents.

This game borrows from both of those and creates something distinct. Each trainer has three Monsters on the field at a time, but they are separated into a `Frontline` and a `Backline`. Each of these segments have extremely distinct concerns, and the goal is to integrate both of them into your strategy.

#### Frontline

> Of the three Monsters on the field, only one is in the Frontline at any given time. While in the Frontline, Monsters are vulnerable to attacks, but it's also the only way to perform attacks of your own. While on the Frontline, you have no access to healing, support moves, or environmental moves, you have to attack. Choosing what Monster is in your Frontline is how you advance the battle state, either by using an offensive Monster to make direct progress, or using a defensive Monster to facilitate your support strategies.

#### Backline

> The remaining two Monsters are in the Backline, where they are completely immune to direct damage. The Frontline Monster cannot target the Backline, so they are free to use any support moves without being vulnerable to attacks by faster, stronger Monsters. However, they are also locked out of any attacking moves as well. While the Frontline exists only to execute the battle strategy, the Backline exists only to facilitate the Frontline.

The final catch is the amount of actions: you only get one. Not one per Monster, but one per turn. If you want to set up hazards, or weather, or give your Frontline a stat boost, you're completely free to, but your Frontline is a sitting duck while you do, and if they're knocked out while you do so, you've completely wasted a turn. Meanwhile, if you want to make progress, you can use your Frontline to knock out their Frontline, but your opponent might be setting something up in their Backline that swings the battle state in their favor, and you're letting them do it by not trying to counteract it with your own Backline. Neither one of these moves are optimal in a vacuum, it relies completely on the situation, and it's your job as a player to understand which situation calls for which action.

Switching also exists in this game, but in a limited capacity. It still counts as a turn, and you can only switch one layer deep. Meaning, if you want to switch out your Frontline, you can only switch with a Monster that's already in your Backline, while Monsters in your Backline can freely switch with any Monster in your party. Upon a Monster's defeat in the Frontline, the slot must also be filled with a Monster already in the backline, and that slot with a Monster in your party.

This stresses the importance of having a synergistic Frontline and Backline. You can have a Monster extremely well suited for the Backline with all their moves based on support, but you can only have one at a time or you'll be forced to put an extremely weak and vulnerable Monster on the field upon losing your Frontline. If your Frontline Monster has type vulnerabilities and you'll need to be ready for defensive switches, you'll need to make sure you already have Monsters in the backline that can facilitate this, and the opponent will also know the only two possible switch-ins you can access, making it an even riskier action.

### Hazards

If the backlines are completely immune to damage, and entire strategies can be centered around specific field conditions, it can be easy to run into stalemates. For instance, say you have a team heavily based on Fire and Grass types utilizing harsh sunlight, while your opponent has a Water and Electric team that relies on heavy rain, you can spend dozens of turns making it rain, then causing a drought, then making it rain, then causing a drought, all while no progress is being made. While I don't want to take away the ability to play ridiculous games of chicken like this, I don't want to encourage it either, which is why there will be `elemental hazards`.

One of the support move types your backline can use involves putting hazards all over the opponents side of the field, which deal 1/20th of each Monster's health at the end of every turn. This is by no means catestrophic, but because they're elemental, they factor in type vulnerabilities. For example, if the hazards are Fire type, Fire is super-effective against Grass, so instead of 1/20th, they'll deal 1/16th against Grass types. If the Monster has two types and both are vulnerable to Fire, they'll instead do 1/12th. Likewise, resisting the hazards with one type will reduce the damage to 1/22nd, and resisting with both types reduces it to 1/24th. By design, being vulnerable to the hazards is more bad than resisting them is good, so no matter what your type is, hazards aren't something you can just ignore.

Hazards are one of the few ways that you can damage the opponent's Backline, as they cover the entire field, not just the Frontline. By setting up hazards, you've started a countdown. By design, the Monsters in the Backline can't fall to just hazard damage, but the Frontline can, and this forces you to put a Monster with extremely low health in the Frontline to either get attacked or get knocked out from hazards the next turn. This makes it so hazards aren't winning the game by themselves, but they can't go unaddressed, and by forcing an opposing team to manage hazards, you're creating opportunities to set up your own team.

### Weather

Weather is another environmental state you can manage, but rather than causing damage, it facilitates types and strategies. This will have different effects and applications, but is in spirit almost a direct copy from Pokemon. Specific moves are given new utility in specific weather conditions, elemental types are stronger or weaker based on the weather, and certain "ability" enchantments and type attributes are enhanced or activated by it.

### Type Attributes

The Pokemon franchise has always had certain mechanics tied to types as a whole, ranging from random and useless to niche and interesting to meta-game defining, but it's always felt inconsistent. Grass types became immune to powder based moves, Dark types became immune to the priority boost of status moves from the Prankster ability, Rock types got a Special Defense boost in sandstorms, and so on. But a lot of these attributes weren't commonly useful, and some times, such as Bug and Ground, never got any special attributes at all. This game will reduce the amount of possible types, but give each of them several usefull attributes, as well as exploitable weaknesses, that make it so types aren't just a means of resisting certain moves or hitting certain Monsters harder, but help facilitate entire strategies.

Types will also have design philosophies behind them to help give players a general idea of where to look to fill what roles. These philosiphies are not set in stone, and creatively implemented outliers are welcome, but types should largely inform strategies in the short term. In general, types will be offense-centric or defense-centric, and go about this in role in extremely powerful but rigid ways, flexible, strategic ways, or a balance of brute force and utility.

#### Fire

> Offensive and Balanced. Fire types are heavily focused on dealing damage directly and through hazards, but also have weather conditions and status effects they can use to boost themselves or wear the opponent down. Fire is incredibly powerful and useful when channeled and controlled, but can burn out of control and leave massive destruction in its wake, and likewise the Fire types can be careful and targetted, or pure, relentless offense.

+ Strengths - increased Fire type damage in the sun, Fire type attacks can't miss when Fire hazards are active
+ Cons - reduced accuracy and half damage from Fire type attacks in the rain

Strong Against: Grass, Metal, Ghost

Weak Against: Water

Resists: Fire, Grass, Metal

Vulnerable: Water, Earth

#### Water

> Defense and Balanced. Water rarely does severe damage on its own, but is incredibly resilient. Water is purifying and a source of constant change, and in battle will often be removing hazards and status conditions to make the game state less chaotic. However, it can help faciliate severe offensive power from other Monsters provided with the right teammates.

+ Strengths - increased Water type damage and immune to status conditions in the rain
+ Cons - reduced accuracy and half damage from Water attacks in the sun

Strong Against: Fire, Earth

Weak Against: Grass

Resists: Fire, Water, Metal

Vulnerable: Grass, Electric

#### Plant

> Offense and Flexible. Nature finds a way. One of the few types that are largely self sufficient, and work well without any other type. They benefit from both sunlight and rain, can resist sand and cold, and take whatever form they need to for survival. These rely on outlasting opponents and wearing them down with thorns, poisons, and spores, while being able to provide health and longevity to themselves and their teammates.

+ Strengths - increased Speed and Special Attack in the sun, heals 1/20th of total health per turn in rain
+ Cons - loses 1/20th of total health per turn in the sun, reduced speed in the rain

Strong Against: Water, Earth

Weak Against: Fire, Grass, Metal

Resists: Water, Electric, Earth

Vulnerable: Fire

#### Earth

> Defensive and Flexible. Between sand, rocks, and soil, Earth can take many forms, but all of them are incredibly resilient. While not the best suited for combat, once they show up, they aren't going anywhere soon. Between hazards, sandstorms, field conditions, and sheer bulk, earth types are designed to be in the battle for the long haul.

+ Strengths - increased Defense and Special Defense and no accuracy reduction in sandstorms
+ Cons - takes extra hazard damage in the sun, reduced Defense and Special Defense in the rain

Strong Against: Fire, Electric, Metal

Weak Against: Water, Grass

Resists: Electric (immune)

Vulnerable: Water, Grass

#### Electric

> Offensive and Rigid. Like lighting, Electric types won't stick around for long, but they'll cause catestrophic damage before they leave. Blindingly fast and incredibly powerful, this type will absolutely shatter defensive cores that aren't prepared for them, especially as they deal extra damage to two of the three defense-centric types (although they're shut out entirely by the third). This type is riskier to utilize as they're fragile and don't match up well against multiple common types, but in the right place at the right time, they can melt opposing teams.

+ Strengths - Electric attacks never miss Metal types, or any type if Metal hazards are set
+ Cons - reduced accuracy from Electric attacks in the sun, reduced power from Electric attacks in sandstorms

Strong Against: Water, Metal

Weak Against: Earth (immune), Grass

Resists: Metal

Vulnerable: Earth

#### Metal

> Defensive and Rigid. While weak to both Fire and Electric, it makes up for this shortcoming with insane bulk. Against everything else, Metal types are immovable objects, shrugging off all but the most powerful attacks and wearing opponents down in turn. Physical attacks in general, regardless of type, are greatly resisted by these Monsters, allowing them to sponge damage for their teams to ensure victory down the line. There isn't much these types do beyond resisting hits, but it does this better than anything else can.

+ Strengths - damage from all physical moves are halved, in sun (or fire hazards) has a chance to burn opponents that make contact
+ Cons - damage from all physical moves only reduced by 25% in sun, takes 25% more damage from energy-based moves in sun

Strong Against: ---

Weak Against: Fire, Electric, Water

Resists: Grass, Earth

Vulnerable: Fire, Electric

#### Ghost

> Distruptive and Flexible. Completely immune to physical attacks. They break under energy attacks, but they'll cause a lot of chaos while they're around. As the only type able to directly target the Backline, they can severely disrupt team structures if the Frontline ignores them, or isn't equipped with energy attacks to handle them. While they aren't capable of much direct damage, they can cause several status conditions and other ailments, slowly draining their opponent's energy for its teammates to pick off.

+ Strengths - immune to all physical moves, chance to cause "Fear" status upon contact, bypasses accuracy checks in "Void" aura
+ Cons - 50% extra damage from all energy-based moves, loses 1/12th of total health in the sun

Strong Against: ---

Weak Against: ---

Resists: ---

Vulnerable: Fire, energy-based moves

#### Dark

> Offensive and Flexible. Like Ghosts, these types excel at disrupting enemy teams with status ailments and other debuffs, but unlike Ghosts, Dark types get their hands dirty. These types are pure offense, hitting opponents hard causing all sorts of debuffs as they do, but they need to be utilized carefully, as there are good answers to them, and they won't last long after running into those answers.

+ Strengths - added priority to all status inflicting moves, all moves with a chance for secondary effects have that chance increased
+ Cons - all stats reduced in "Luminous" aura, all Dark type strengths neutralized

Strong Against: ---

Weak Against: ---

Resists: ---

Vulnerable: ---

#### Light

> Defensive and Balanced. Light types are no-nonsense. They are immune to status conditions, they ignore stat changes and accuracy rolls, and don't have any tricks up their sleeves. However, this applies to all opponents when they're on the field as well. All the benefits of not falling prey to debuffs and status conditions, as well as all the downsides of not being able to debuff or status your opponents, apply to every Monster that interacts with the Light type. Monsters that rely on disrupting and wearing down opponents will crumble to Light types, as they're forced to play a more "honest", careful game than they would like to.

+ Strengths - ignores stat changes**, immune to status conditions, no accuracy checks on attacks
+ Cons - all strengths apply to Monsters that interact with the Light types as well

** *The stat changes are not reverted, just ignored. When the Light type is no longer in play, they will take effect again.*

Strong Against: ---

Weak Against: ---

Resists: ---

Vulnerable: ---

#### Primary Vs Secondary Types

> Monsters can have two types at the same time, which could lead to combined attributes that are either game-breakingly powerful, or anti-synergistic and cancel each other out. To solve for both of these issues, the type attributes a Monster has will be based entirely on the `Primary` type of the Monster. The `Secondary` type still grants type immunties, resistances, and weaknesses, as well as boosting any attack moves that share the Monster's type, but the special type attributes of the Secondary type won't apply. As part of the player's customization options, a player can swap their Monster's type order outside of battle, granting them the attributes they feel are better suited to their team's layout.
> 

### Move Types

Moves can also have Types, which is how the strong against / weak against attributes are factored (Water type attack strong against Fire type Familiar, Grass type attack weak against Metal type Familiar). If the Move type is the same as one of the Familiar types, that Move's base power is given a 50% increase, a direct holdover from Pokemon. 

Where this will differ from Pokemmon is in Null type attacks. Pokemon has a few niche moves that are considered typeless, either implicitly or explicitly, but this will be a major component of this battle system. While typed Moves are generally powerful and objectively better, they will have limited uses (same as Power Points in Pokemon). Null type Moves, however, will be incredibly weak and lack most utitily (think Pound, Tackle, Scratch, etc), and will deal neutral damage to all Familars (barring Ghost and Metal resisting physcial Moves) with no chance for a Same-Type boost, but the benefit is that they will have unlimited uses. This is useful for tanks who want to deal consistent damage without worrying about matchups or sweepers who want to save their powerful nuke attacks for specific targets, but the main use will likely be for coverage.

In Pokemon, there was a move called Hidden Power, that used a Pokemon's IVs to determine what type and base power the move would be. This was used to give Pokemon who didn't have a lot of move variety a way to cover some of their weaknessess, such as Zapdos using Hidden Power Water against the Rock/Ground types that otherwise wall it out completely, or as a way to discourage defensive switch ins, such as Dugtrio using Hidden Power Bug against Celebi who would otherwise shut it down completely. This is a good concept, but it tying it to IVs limits it. Various types that would be amazing converage are either impossible because certain event Pokemon have locked IVs, or the Ivs have to be so low to get the coverage type that you make the Pokemon worthless in the process.

In this game, one of the item-styled enchantments will do this for you. Pokemon has Abilities that override Normal type attacks, making them a new type and giving them a 30% boost (Pixelate => Fairy type, Aerilate => Flying type, Refrigerate => Ice type). Each of our types will have an item-enchantment that converts all Null type attacks the Familar knows into that enchantment's type, while giving the Move's base power a 50% increase. This is balanced by the Null type Moves being weak by default, and that rather than being a free Move you can add, you have to use your item slot to accomplish this. However, this will also stack with the Same-Type bonus, so if you place a Fire enchantment onto a Fire type Familar and use a 40 power Null attack, it will have 90 power instead of just 60.

There will also be a Hidden Power style Move designed to utilize this, which will have a base power of 80 when the Familiar is using a type enchantment, making it 120 power if you stack the enchantment on top of Same-Type Bonus. This is will put it on par with some of the strongest moves in the game, but with perfect accuracy and unlimited uses. Even without a Same-Type bonus, a consistent 80 power move is solid coverage as well. The idea here is to make a Hidden Power that's substantially stronger than the one in Pokemon, but requires more commitment in exchange.

### Strategies

While it's hard to go into detail without referencing specific moves, there are general strategies you can implement. For example, you have a move that's extremely powerful in the rain, but useless outside of it. To pull this move off, you need to activate the rain in your Backline, then use the move in your Frontline. If your Backline Monster is too fast, they can set up rain in the first turn, but have it overridden that same turn by a slower enemy setting up the sun. Likewise, if your Backline is slower, you can guarantee the second turn begins with rain, but if the opponent's Backline is fast enough, they can remove the rain before your Frontline attacks. In order to pull this off, reliably, you need your Frontline to be the fastest Monster on the field, and your rain-setting Monster to be the slowest on the field.

You also need to ensure that your Frontline is bulky enough to survive the set up process, or threatening enough to scare the opponent away from focusing solely on weather, while not being so threatening that it gets targetted and wiped out before getting a chance to utilize the move you're waiting on the rain for. Hazards can also create pressure that allow you to set up, but it's a gamble if the opponent tries to address the hazards before they address the Frontline.

The gameplan is to apply constant pressure from several different angles, and try to get your opponent to crack before you do. To do this, you need to balance speed control, bulk, and syngery between support moves and attacking moves. The 75 addition points you can add from each Monster's potential pool lets you dynamically add speed, bulk, or offensive power depending on what your specific team needs.
