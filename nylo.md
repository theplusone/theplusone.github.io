# Nylo DPS stuff

> What's the average number of ticks to kill 2 smalls from a big?

## Assumptions

- Duo scale (16 and 8 hp for big and little nylos respectively)
- Two gear setups
  1. **Range gear**: e. void ranged with 1-way whip and sang (make sure that
     void bonuses aren't enabled for melee/mage since no void helm switch) (no
     boots)?
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
similarly, when attacking ranged or magic, the melee freezer is also using a
1-way switch.

|        |       |         | Void ranger | Mel. frz. |
|--------|-------|---------|-------------|-----------|
| Melee  | Big   | DPS     | 7.598       |           |
|        |       | TTK (s) | 3.789       |           |
|        |       | TTK (t) | 6.315       |           |
|        | Small | DPS     | 7.807       |           |
|        |       | TTK (s) | 2.996       |           |
|        |       | TTK (t) | 4.993       |           |
| Ranged | Big   | DPS     | 12.65       |           |
|        |       | TTK (s) | 2.069       |           |
|        |       | TTK (t) | 3.448       |           |
|        | Small | DPS     | 13.10       |           |
|        |       | TTK (s) | 1.562       |           |
|        |       | TTK (t) | 2.603       |           |
| Magic  | Big   | DPS     | 6.774       |           |
|        |       | TTK (s) | 4.055       |           |
|        |       | TTK (t) | 6.758       |           |
|        | Small | DPS     | 7.113       |           |
|        |       | TTK (s) | 3.082       |           |
|        |       | TTK (t) | 5.137       |           |

