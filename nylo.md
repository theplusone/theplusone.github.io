# Nylo DPS stuff

> What's the average number of ticks to kill 2 smalls from a big?

## Assumptions

- Duo scale (16 and 8 hp for big and little nylos respectively)
- Two gear setups
  1. **Range gear**: e. void ranged with 1-way whip and sang (make sure that
     void bonuses aren't enabled for melee/mage since no void helm switch) (~~no
     boots?~~ primordials)
  2. **Melee freeze**: Serp helm, infernal, torture, anc legs, avernic, feros,
     swift blade, primordial boots, b ring (i). Melee freezer does one-way...?
     
     
## Possibilities

There are three types of crabs (melee, ranged, magic) and two sizes (big,
little). When killing a big, two littles of random type will spawn. These are
the possible scenarios (order does not matter):

```
Melee  -> Melee  -> Melee
                 -> Ranged
                 -> Magic
       -> Magic  -> Ranged
                 -> Magic
       -> Ranged -> Ranged
       
Ranged -> Melee  -> Melee
                 -> Ranged
                 -> Magic
       -> Magic  -> Ranged
                 -> Magic
       -> Ranged -> Ranged
       
Magic  -> Melee  -> Melee
                 -> Ranged
                 -> Magic
       -> Magic  -> Ranged
                 -> Magic
       -> Ranged -> Ranged
```

This is <sub>3</sub>C<sub>1</sub> * (4 choose 2) = 18 possibilities, though
these are arguably independent, so one could just say that there are 3
possibilities of big and 6 possibilities of small.

## Data

(you can skip this section if you want, I just needed somewhere to write stuff
down)

When attacking melee or magic, the void ranger is using a 1-way switch, and
similarly, when attacking magic, the melee freezer is also using a 1-way switch.

(overkill DPS would've been more meaningful here, but it doesn't matter since
TTK already uses overkill DPS)

|        |       |         | Void ranger | Mel. frz. |
|--------|-------|---------|-------------|-----------|
| Melee  | Big   | DPS     | 7.802       | 8.297     |
|        |       | TTK (s) | 3.747       | 5.154     |
|        |       | TTK (t) | 6.245       | 8.590     |
|        | Small | DPS     | 8.014       | 8.503     |
|        |       | TTK (s) | 2.980       | 2.350     |
|        |       | TTK (t) | 4.967       | 3.917     |
| Ranged | Big   | DPS     | 12.655      | n/a       |
|        |       | TTK (s) | 2.069       | n/a       |
|        |       | TTK (t) | 3.448       | n/a       |
|        | Small | DPS     | 13.096      | n/a       |
|        |       | TTK (s) | 1.563       | n/a       |
|        |       | TTK (t) | 2.605       | n/a       |
| Magic  | Big   | DPS     | 6.750       | 6.877     |
|        |       | TTK (s) | 4.069       | 3.994     |
|        |       | TTK (t) | 6.782       | 6.657     |
|        | Small | DPS     | 7.104       | 7.148     |
|        |       | TTK (s) | 3.086       | 3.067     |
|        |       | TTK (t) | 5.143       | 5.112     |

A more condensed table. Lower is better:

|        |       |         | Void ranger | Mel. frz. |
|--------|-------|---------|-------------|-----------|
| Melee  | Big   | TTK (t) | 6.245       | 8.590     |
|        | Small | TTK (t) | 4.967       | 3.917     |
| Ranged | Big   | TTK (t) | 3.448       | n/a       |
|        | Small | TTK (t) | 2.605       | n/a       |
| Magic  | Big   | TTK (t) | 6.782       | 6.677     |
|        | Small | TTK (t) | 5.143       | 5.112     |

Adding more switches for mage nylo:

|        |       |         | Mel. frz. | +Occult | +Torm | +Anc. top |
|--------|-------|---------|-----------|---------|-------|-----------|
| Magic  | Big   | TTK (t) | 6.657     | 6.323   | 6.202 | 6.075     |
|        | Small | TTK (t) | 5.112     | 4.987   | 4.947 | 4.905     |
