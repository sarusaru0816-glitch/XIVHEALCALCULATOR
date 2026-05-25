# FFXIV Heal Calculator

FFXIV Lv100 healing simulator. Compares Tank, DPS, Healer output for direct-heal skills like Clemency and Cure II. Inputs: main stat, DET, TNC, WD, job, potency, buff %. Outputs expected HP, ±3% range, healer ratio, and difference. Formula uses AkhMorning Dawntrail model with main stat coefficient 179.

## Demo

`https://[your-username].github.io/[repo-name]/`

## Features

- 3ロール（Tank / DPS / Healer）の理論回復量を同時計算
- ジョブ別 JobMod プルダウン（タンク4種・DPS13種・ヒラ4種）
- 回復量バフ（%）対応
- 乱数±3%の範囲表示
- ヒラ比・差分を即座に表示

## Formula

```
H1 = ⌊⌊P × f(主ステ) × f(DET)⌋/100⌋/1000⌋
H2 = ⌊⌊⌊⌊H1 × f(TNC)⌋/1000⌋ × f(WD)⌋/100⌋ × Trait⌋/100⌋

f(主ステ) = ⌊179 × (Stat - 440)/440 + 100⌋
f(DET)    = ⌊140 × (DET - 440)/2780 + 1000⌋
f(TNC)    = ⌊112 × (TNC - 420)/2780 + 1000⌋   (Tankのみ)
f(WD)     = ⌊440 × JobMod/1000 + WD⌋
Trait     = 1.30 (Healer) / 1.00 (Tank, DPS)
```

Lv100基準値: MAIN=440, SUB=420, DIV=2780

## License

MIT
