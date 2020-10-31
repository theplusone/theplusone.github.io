# Trailblazer DPS calcs

_Note: depending on the regions you unlock and the gear you have, the numbers
here could vary a bit. The calculations here are less about seeing exact DPS and
more about seeing what weapons are better than others._

Sorry it took so long. Figuring out how to hack the relic stuff into the DPS
calcs took some time.

## Gear setups

### Melee

Infernal cape, amulet of torture, bandos chestplate, bandos
tassets, avernic defender (if 1h), rune gloves, dragon boots

Includes T3 "Fluid Strikes" relic that grants halved attack speed (rounded up)
and 25% increased accuracy. Assuming the increased accuracy is calculated by
multiplying the final max attack roll by 1.25.

2t whip, 2t rapier, 3t scythe (charged), 3t scythe (uncharged), 2t zamorakian
hasta, 3t bandos godsword, 2t saradomin sword, 3t guthan's warspear (wearing
full guthan's), 3t verac's flail (wearing full verac's), 4t dharok's greataxe
(wearing full dharok's, 1hp)

### Ranged

Armadyl helmet, ava's assembler, necklace of anguish, armadyl chestplate,
armadyl chainskirt, rune gloves

Includes T3 "Quick Shot" relic that grants halved attack speed (rounded up), 10%
increased damage, and 100% increased accuracy. Similar to melee, assuming the
increased accuracy is calculated by multiplying the final max attack roll by 2
and the increased damage is calculated by multiplying the final max hit by 1.10.

3t acb (ruby drag bolts e), 2t crystal bow (wearing full crystal), 3t heavy
ballista (dragon javelin), 2t karil's crossbow, 1t blowpipe (d darts)

## Melee calcs

DPS values are rounded to the nearest thousandth, and assume super combat and
piety.

### Verzik p3

P3 Verzik is less resistant to slash (relative to crush and stab). 

```
16.452 - Scythe (charged)   - 3t
16.256 - Dharok's (slash)   - 4t
15.385 - Whip               - 2t
15.414 - Rapier (slash)     - 2t
14.679 - Rapier (stab)      - 2t
14.383 - Z hasta (slash)    - 2t
14.305 - Dharok's (crush)   - 4t
14.081 - Sara sword         - 2t
13.480 - Scythe (uncharged) - 3t
13.277 - Z hasta (stab)     - 2t
12.984 - BGS                - 3t
 8.654 - Guthan's           - 3t
 8.425 - Verac's            - 3t
```

### Zero-defense maiden

Maiden has no additional stab/slash/crush defense, just a 200 def stat that
can get spec'd down to 0.

```
20.397 - Scythe (charged)   - 3t
20.124 - Dharok's           - 4t
19.856 - Rapier             - 2t
19.020 - Whip               - 2t
18.196 - Z hasta            - 2t
18.168 - Sara sword         - 2t
17.612 - Scythe (uncharged) - 3t
15.723 - BGS                - 3t
11.283 - Guthan's           - 3t
11.106 - Verac's            - 3t
```

### Inferno mager (Jal-Zek)

nteventhrice has a fire max cape

Jal-Zek also has no additional stab/slash/crush defense, just a 260 def stat.

```
<needs to be redone -- still had 200 def reduction from maiden applied>
```

## Range calcs

### Verzik p3

Verzik's +230 range defense doesn't matter much when the relic doubles your
accuracy.

```
16.282 - Blowpipe    - 1t
12.147 - ACB         - 3t
11.201 - Crystal bow - 2t
10.441 - H. ballista - 3t
 7.974 - K. crossbow - 2t
```

### Zero-defense maiden

```
<WIP>
```


## DIY

You will be modifying some spreadsheet internals, so I recommend making a
separate copy of the DPS spreadsheet solely for Leagues use. When switching
between combat styles, be sure to apply the new relic changes so you have
accurate numbers. With enough time and effort, I could probably add some toggles
that'd make this a lot easier, but for now, here's how you can manually hack the
relics into the DPS spreadsheet:

### Melee relic

Accuracy: change 'Dps p1'!D22 from `=INT(D21)` to `=INT(D21)*1.25`

Attack speed: go to 'Items' sheet, find melee weapon and it's attack speed
column (column U), divide by 2 and round up

### Range relic

Accuracy: change 'Dps p1'!D22 from `=INT(D21)` to `=INT(D21)*2.00`

Max hit: wrap the giant formula at 'Dps p1'!D107 in parentheses, multiply it
by 1.10, and round down.

Attack speed: Dealing with this one sucks because ranged attack speed can vary
based on attack style. This is a really shitty way of doing it, but a quick way
to do this is to set the attack speed manually at 'Dps p1'!D134. What I've done
is change D135 to `=D132/IF(Input!M35, Input!M35, D134)`; this changes the
attack speed only if I have a custom one set on the main sheet. 
