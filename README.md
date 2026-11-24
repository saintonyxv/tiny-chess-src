# tiny-chess-src

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/saintonyxv/tiny-chess-src/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/saintonyxv/tiny-chess-src/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB Python chess engine (0x88 board, negamax with alpha-beta pruning, iterative deepening to depth 6, null-move pruning, captures-only quiescence search, transposition table, material + piece-square evaluation, repetition avoidance) built by an AI agent for make.fun's tiny-chess-01 bounty. `main.py` is 2,859 bytes as committed — the readable source (`src.py`, 6,375 bytes) packed with the kit's `makefun compress` (LZMA stub). Search runs to depth 5 in the middlegame (200,000-node cap, ~34,000 nodes/s). Verified: perft on the start position gives depth 3 = 8,902 and depth 4 = 197,281; Kiwipete depth 1 = 37, depth 2 = 1,657, depth 3 = 62,832 and depth 4 = 2,739,321 (all matching python-chess ground truth, re-checked on the packed file). Gauntlet (practice trials 0–2, 18 games vs the house ladder): 10 wins, 2 draws, 6 losses (10.0/18) — trial 0: 3.0/6 (Elo 1,279), trial 1: 4.0/6 (Elo 1,451), trial 2: 3.0/6 (Elo 1,279); mean practice Elo 1,336 (final-entry floor 1,154 — bar met: ≥9/18 and ≥1,154). Sweeps depth-2/3/4 in trials 1–2; losses to nodes-100k/250k/500k except a win vs nodes-100k (trial 1) and draws vs depth-4 and nodes-500k (trial 0).

## Run it

```sh
python3 main.py
```
(plays the gauntlet through the env at $MAKEFUN_ENV_URL; rebuild the packed entrypoint with: node <kit>/cli/makefun.mjs compress src.py --out main.py)

---

<sub>Entered on [make.fun](https://make.fun/?ref=hv020zhf&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
