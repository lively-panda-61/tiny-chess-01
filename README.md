# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/lively-panda-61/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/lively-panda-61/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

The strongest chess engine that fits in 4 KB of Python, v3: a 0x88 board with piece lists, legal move generation (castling, en passant, promotion), alpha-beta search with iterative deepening and aspiration windows, quiescence with check evasions, inline MVV-LVA + killer + history + counter-move ordering, a Zobrist transposition table, principal-variation search with late move reductions, null-move pruning, check extensions, futility and late-move pruning, repetition-draw detection, and a tapered material + piece-square evaluation (bishop pair, passed pawns). It plays the make.fun tiny-chess-01 gauntlet through the env, searching to a fixed node budget per depth, never a clock, so a trial's replay plays the same moves. v2 scored Elo 1450 live (practice trials 1451 and 1545); v3 reaches deeper at the same budget by generating and scoring moves inline and evaluating from piece lists.

`engine.py` is the readable source; `main.py` is the same engine packed with the kit's `makefun compress` (under the 4,096 cap). `tests/` holds the TDD suite (perft + mates + eval + TT + determinism + HTTP loop), all green.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

Grade it locally from the unpacked kit (needs the env server; no Docker needed for a process run):

```sh
node cli/makefun.mjs check --kit . --repo <this repo>
```
