# Nylo DPS stuff

> What's the average number of ticks to kill 2 smalls from a big?

## Assumptions

- Duo scale (16 and 8 hp for big and little nylos respectively)
- Two gear setups
  1. **Range gear**: e. void ranged with 1-way whip and sang (make sure that
     void bonuses aren't enabled for melee/mage since no void helm switch)
  2. **Melee freeze**: Serp helm, infernal, torture, anc legs, avernic, feros,
     swift blade, primordial boots, b ring (i)
     
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
these are arguably independent of each other, so you could just say that there
are 3 possibilities of big, and 6 possibilities of small.
