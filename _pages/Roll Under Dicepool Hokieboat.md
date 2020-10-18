---
layout: page
title: Roll Under Dicepool
permalink: /pool1/
---
## Mixed Dicepool, Roll Under TN and Count Successes

## Goals
- multiple (3+) mechanical input levers (think ability mod, proficiency, advantage, etc are levers).
- combined roll approximates difficuty as _challenge_ and _effort_ (the math nerd in me compares it to a force vector's _direction_ and _magnitude_, respectively). This gives the GM two levers to play with when setting challenge.
- Increasing player ability increases likelihood of success for more difficult tasks AND increases amount of effort able to be generated for tasks of constant difficulty.
- Able to easily accommodate group rolls / PCs aiding another.
- Able to work for both player rolls, GM rolls, and opposed rolls. 
- Able to accommodate things as straighforward as kicking doors in, or more complex like combined hit and damage rolls.
- All difficulty levels are technically achievable for all characters. 
- All rolls are "negotiated contests" in that the player specifies an action and the GM calls for the roll based on what the player says their character attempts. 
- Dice do not "force a narrative"
- GM is expected to adjust Ground, Effort, and Challenge, and call for the appropriate Ability based on the PC's Approach. Some things (like picking a lock) might have fixed effort and challenge based on the lock. Most things without fixed effort and challenge will typically be resolved with an opposed roll. 


## Four Player Inputs:
1. General Ability
	- d12: minimal
	- d10: some/average
	- d8: significant
	- d6: legendary
2. Tool/Implement/Procedure
	- d20: nothing
	- d12: bare hands
	- d10: useful/relevant
	- d8: purpose built
	- d6: masterwork purpose-built
3. Ground/Situation
	- d20: disadvantageous
	- d12: unfavorable
	- d10: neutral
	- d8: favorable
	- d6: advantageous
4. Specific Training / Practice
	- No dice: nothing relevant
	- d12: familiarization
	- d10: practiced (extensively)
	- d8: professional
	- d6: peerless master

## Two GM Levers
1. Challenge (CN = Challenge Number)
	- Trivial: CN 5
	- Easy: CN 4
	- Moderate: CN 3
	- Hard: CN 2
	- Insane: CN 1
2. Effort
	- Low: 1 die <= CN
	- Medium: 2 dice <= CN
	- High: 3+ dice <= CN

Environmental / Externalities range from d20 - d6, Abilities range from d12 - d6

Range from 1d12 & 2d20 to 4d6 vs CN 1-5 and EFF 1-3 (see anydice function)
- i.e. worst case is 1d12 and 2d20

| TN | EFF 1+ | EFF 3+ |
|:---:|:---:|:---:|
| 1 | 17.27% | 0.02% |
| 5 | 67.19% | 2.6% |

- best case is 4d6

| TN | EFF 1+ | EFF 3+ |
|:---:|:---:|:---:|
| 1 | 51.77% | 1.62% |
| 5 | 99.92% | 86.81% |

### AnyDice Function

```
function: roll A:d B:d C:d D:d E:d vs CN:n for EFF:n {
    if 1@{A} != 0 {AD: (#A)d(d(1@[reverse {1@A}]) <= CN)} else {AD: 0}
    if 1@{B} != 0 {BD: (#B)d(d(1@[reverse {1@B}]) <= CN)} else {BD: 0}
    if 1@{C} != 0 {CD: (#C)d(d(1@[reverse {1@C}]) <= CN)} else {CD: 0}
    if 1@{D} != 0 {DD: (#D)d(d(1@[reverse {1@D}]) <= CN)} else {DD: 0}
    if 1@{E} != 0 {ED: (#E)d(d(1@[reverse {1@E}]) <= CN)} else {ED: 0}
    result: (AD + BD + CD + DD + ED) >= EFF
}

output [roll 1d12 2d20 {} {} {} vs 1 for 1]
output [roll 4d6 {} {} {} {} vs 5 for 1]
```

These show % odds of specified for a given dice input (up to 5 different dice) vs a CN for a minimum EFF

## Expanded Options

- Group checks can simply be everyone rolls dice, and there is a table that scales effort based on # of participants, and the total effort from everyone's dice is what is used in adjudication by the GM. 
- Opposed rolls can be number of dice lower than opponents dice (like a roll-under version of Risk). Ties could be resolved using the next-lowest dice for each character.
4d6 has a 71.91% chance of rolling 1+ EFF against 1d12+2d20 
1d12 has a 12.32% chance of rolling 1+ EFF against 4d6 (not equivalent due to ties)

### Opposed AnyDice: 

```
\caution: server timeout likely\
function: oppose A:d B:d C:d D:d E:d vs F:s G:s H:s I:s J:s for EFF {
    S: [sort {F, G, H, I, J}]
    CN: {#S}@S

    if 1@{A} != 0 {AD: (#A)d(d(1@[reverse {1@A}]) < CN)} else {AD: 0}
    if 1@{B} != 0 {BD: (#B)d(d(1@[reverse {1@B}]) < CN)} else {BD: 0}
    if 1@{C} != 0 {CD: (#C)d(d(1@[reverse {1@C}]) < CN)} else {CD: 0}
    if 1@{D} != 0 {DD: (#D)d(d(1@[reverse {1@D}]) < CN)} else {DD: 0}
    if 1@{E} != 0 {ED: (#E)d(d(1@[reverse {1@E}]) < CN)} else {ED: 0}
    result: (AD + BD + CD + DD + ED) >= EFF
}


output [oppose 1d12 2d20 {} {} {} vs 4d6 {} {} {} {} for 1]

\this is faster but only calculates odds of winning\
function: oppose A:s B:s C:s {
    T: [sort {A, B, C}]
    result: {#T}@T
}


X: [oppose 1d12 2d20 {}]
Y: [oppose 4d6 {} {}]

output Y = X
```

## Advantages

- Natural language is possible. (i.e. "That's a high effort, moderate \_\_\_\_(ability)\_\_\_\_ challenge on favorable ground, and your \_\_\_\_\_\_\_\_ training and \_\_\_\_\_\_\_\_ tools apply." "Okay, I managed/rolled high effort.")
- Lots of levers to adjust the odds.
- Effort can equal damage, or degree of success, or anything appropriate to the scale of the input roll. 
- No asking the GM if you succeeded, mechanics mostly force the GM to state difficulty in advance and ensure players know the result when the dice hit the table (e.g. eliminates "is an X good enough?")

## Issues

- Probabilities are funky
- Roll under is not as intuitive as roll over
- General ability only has four different levels (compared to D&D, where ability scores have 11 discrete modifier levels).