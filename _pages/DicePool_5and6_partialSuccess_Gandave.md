---
layout: page
title: D6 Dicepool - 5 and 6 Win - Partial Success
permalink: /pool2/
---

## Overview
For each task a players rolls a pool of D6 as determined by his stats and the difficulty of the check. The player counts the number of dice that score a ***5*** or a ***6***.

- If no dice scored, the check was failed.
- If one dice scored, the check was a partial success.
- If two or three dice scored, the check was a (regular) success.
- If more than three dice scored, the check was a critical success.

A partial success means a glancing hit, only slight progress or success at a cost. A critical hit means additional damage or progress or a boost in addition to regular success.

Number of Dice = 5 + attribute bonus + skill bonus + circumstance bonus/penalty - difficulty class

- If the number of dice is exactly 0, you still roll 1 dice, but only a ***6*** results in a partial success. A regular success is impossible.
- If the number of dice is less than 0, you automatically fail.
- If the number of dice is more than 9, you automatically succeed and probably critically so (depending on the situation and GM interpretation).

The number of dice is dependent on four factors:
- Attribute bonus/penalty is between -1 and +3, default is +1.
- Skill bonus is between +0 and +3, default is +0.
- Circumstance bonus/penalty is between -3 and +3, but defaults to +0.
- The Difficulty is technically unrestrained, but usually should be between 0 and 6 with emphasis on the lower half.

## Bonuses

| Bonus | Attribute | Skill | Circumstance |
| - | - | - | - |
| -3 |  |  | abysmal |
| -2 |  |  | very poor |
| -1 | abysmal |  | detrimental |
| 0 | poor | untrained | average |
| +1 | average | trained | beneficial |
| +2 | good | expert | great |
| +3 | great | master | exceptional |

## Difficulties

| Difficulty | For average | For expert | For master |
| - | - | - | - |
| -3 | trivial |  |  |
| -2 | very easy |  |  |
| -1 | easy | trivial |  |
| 0 | average | very easy |  |
| 1 | slightly challenging | easy | trivial |
| 2 | challenging | average | very easy |
| 3 | very challenging | slightly challenging | easy |
| 4 | hard | challenging | average |
| 5 | very hard | very challenging | slightly challenging |
| 6 | near impossible | hard | challenging |
| 7 |  | very hard | very challenging |
| 8 |  | near impossible | hard |
| 9 |  |  | very hard |
| 10 |  |  | near impossible |

- All names are subject to change.
- This table is meant as an orientation for GMs to set difficulties, but the names do not matter, only the numbers.
- In most cases it makes no sense to ask for rolls with a difficulty below 0, unless the circumstances warrant it.
- The different difficulties are each two steps apart. This is more or less arbitrary, but fits nicely - what is *challenging* for an average person is *average* for an expert and *very easy* for a master.

## Examples

- The "average" bonus is +6 (*Average* (+1) attribute and *Untrained* (+0) against *average* (DC 0) difficulty under *average* (+0) circumstances). This gives a success rate of ~2/3 (~70%).
- A character with an *Average* (+1) "Perception" attribute and *Trained* (+1) in "Searching" will roll 7d6 for *average* (DC 0) tasks and succeed at a rate of ~3/4 (~74%). Even if he won't succeed there's a chance of ~1/5 (~20%) that he'll score at least get a partial success. His crit chance is ~2/5 (~43%).
- If the difficulty is instead *hard* (DC 2), his success rate drops to ~1/2 (~54%). His partial|critical success chance is ~1/3 (~33%)|
- The highest he can reasonably attempt is *hard* (DC 4), for a ~1/9 (~11%) chance of success.
- It would be possible to attempt a *nearly impossible* (DC 6) task, but the best he could hope for is a partial success at a 1/6 chance (~17%).

## Possible Progression

At low levels, the PCs will probably start out with mostly *Average* (+1) attributes, maybe one *Good* (+2) or two *Good* and one *Poor* (+0). They will have some skills as *Trained* (+1), maybe even one skill at *Expert* (+2), and the rest at *Untrained* (+0).

At mid level, the PCs will probably have a lot of skills *Trained* (+1) or are *Experts* (+2) with their attributes being mostly *Good* (+2) or *Average* (+1).

At high levels, the PCs will have one or two attributes at *Great* (+3), the rest at *Good* (+2), maybe one or two at *Average* (+1). Their specialty skills are mostly *Expert* (+2), though some may be *Mastered* (+3). The rest are a mix of *Trained* (+1) and *Untrained* (+0).

An average starting bonus is +6, the maximum bonus with stats alone is +11, so about double the starting bonus. Any more than that might widen the gap between the average person and the PCs too much.

## Design Considerations

- This method is similar to the "6 wins" and "5 and 6 win" dice pool methods. Players are able to resolve a dice roll very quickly (as long as they have enough dice).
- In this version the PCs will be more competent than in the other versions as the "partial success" result makes true failure unlikely.
- For *very hard* and *near impossible* rolls, only a partial success is possible, for *hard* and *very challenging* rolls, no critical success is possible. This could in play lead to some difficulties being "soft-gated" behind certain stats. E.g. players are most likely not or only rarely going to attempt *very hard* or *near impossible* rolls, especially if the cost for a partial success is high.
- Mathematically, one could move the total bonuses of attributes and skills around a bit, e.g. attributes going from +1 to +4 and skills only to +2.
- The system assumes that most actions can be resolved using a skill. For pure attribute based actions, the difficulty has to be set accordingly. This can be done be only using the difficulty column "for average person", i.e. generally no DC greater than 4 or 5.
- Mathematically, all factors (attribute, skill, circumstances, difficulty) are equal, so raising a skill by one does the same as raising an attribute by one, and a high difficulty task is equivalent to a lower difficulty task under bad circumstances.
- The bonuses are not very large (between +0 and +5), but might still suffice to satisfy players who love customization (such as myself).
- It might be unintuitive to add a fixed number of 5 to the total bonus of a character. This can simply be changed by setting the base attribute at +5 for poor, +6 for average, etc.
- By the same token, it might be unintuitive that an *Average* attribute is +1, so shifting everything up one step and starting with 6 dice instead of 5 would also work.
- I'm not sure how intuitive the DC system is for GMs at the table. We'd have to playtest to find that out.
- As the math is quite restrictive, it would probably not be a good idea to allow items to give additional bonuses aside from offering beneficial circumstances. I.e., my magic sword does not give me a +1 bonus in general, but a sword of dragon slaying might be *beneficial* in a fight with a wyrm.

## Icky Math

The math behind this is a bit more complicated. One can use the binomial distribution to determine how likely one, two, three or more "hits" are.

| No. of D6 | Fail Chance | Partial Success Chance | DC on D20 for partial success | Success Chance | DC on D20 for success | Critical Success Chance | DC on D20 for critical success | Difficulty for average DC and person |
| - | - | - | - | - | - | - | - | - |
| "0" | 83,33% | 16,67% | 18 | 0,00% | 21 | 0,00% | 21 | near impossible |
| 1 | 66,67% | 33,33% | 14 | 0,00% | 21 | 0,00% | 21 | very hard |
| 2 | 44,44% | 44,44% | 10 | 11,11% | 19 | 0,00% | 21 | hard |
| 3 | 29,63% | 44,44% | 7 | 25,93% | 16 | 0,00% | 21 | very challenging |
| 4 | 19,75% | 39,51% | 5 | 39,51% | 13 | 1,23% | 21 | challenging |
| 5 | 13,17% | 32,92% | 4 | 49,38% | 10 | 4,53% | 20 | slightly challenging |
| 6 | 8,78% | 26,34% | 3 | 54,87% | 8 | 10,01% | 19 | average |
| 7 | 5,85% | 20,48% | 2 | 56,33% | 6 | 17,33% | 18 | easy |
| 8 | 3,90% | 15,61% | 2 | 54,63% | 5 | 25,86% | 16 | very easy |
| 9 | 2,60% | 11,71% | 2 | 50,72% | 4 | 34,97% | 14 | trivial |
| 10 | 1,73% | 8,67% | 1 | 45,52% | 3 | 44,07% | 12 | don't roll |
