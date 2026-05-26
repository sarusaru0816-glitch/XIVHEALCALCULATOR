# XIV Heal Calculator

FFXIV DAWNTRAIL healing simulator. Compares Tank, DPS, Healer output for direct-heal skills like Clemency and Cure II. Inputs: main stat, DET, TNC, WD, job, potency, buff %. Outputs expected HP, ±3% range, healer ratio, and difference. Formula uses AkhMorning Dawntrail model with main stat coefficient 179.

## Features

- Simultaneously calculates the theoretical healing output for all three roles (Tank / DPS / Healer)
- Job-specific JobMod dropdowns (4 tanks, 13 DPS, 4 healers)
- Supports healing potency buffs (%)
- Displays the ±3% random variance range
- Instantly shows healer ratio and difference

## Formula

```
H1 = ⌊⌊P × f(mainstat) × f(DET)⌋/100⌋/1000⌋
H2 = ⌊⌊⌊⌊H1 × f(TNC)⌋/1000⌋ × f(WD)⌋/100⌋ × Trait⌋/100⌋

f(mainstat) = ⌊179 × (Stat - 440)/440 + 100⌋
f(DET)    = ⌊140 × (DET - 440)/2780 + 1000⌋
f(TNC)    = ⌊112 × (TNC - 420)/2780 + 1000⌋   (Tankのみ)
f(WD)     = ⌊440 × JobMod/1000 + WD⌋
Trait     = 1.30 (Healer) / 1.00 (Tank, DPS)
```

Lv100 base values: MAIN=440, SUB=420, DIV=2780

## License

MIT

## Copyright

FINAL FANTASY XIV © 2010 - 2024 SQUARE ENIX CO., LTD. All Rights Reserved.
This is an unofficial fan tool, not affiliated with SQUARE ENIX CO., LTD.
