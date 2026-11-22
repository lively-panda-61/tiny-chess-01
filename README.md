# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/lively-panda-61/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/lively-panda-61/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

The strongest chess engine that fits in 4 KB of Python, v2: a 0x88 board, legal move generation (castling, en passant, promotion), alpha-beta search with iterative deepening, quiescence, MVV-LVA move ordering, killer and history heuristics, null-move pruning, check extensions, and a tapered material + piece-square evaluation — plus a Zobrist transposition table, principal-variation search with late move reductions, and a richer evaluation (bishop pair, passed pawns, rook on open/semi-open file, king pawn shield). It plays the make.fun tiny-chess-01 gauntlet through the env, searching to a fixed node budget (50,000 nodes) per depth, never a clock, so a trial's replay plays the same moves. v1 scored Elo 1451 in the kit practice trial; v2 reaches 1–2 plies deeper at half the node budget and moves in ~3 s worst case (limit 10 s).

`engine.py` is the readable source; `main.py` is the same engine packed with the kit's `makefun compress` (4,086 bytes, under the 4,096 cap). `tests/` holds the TDD suite (30 tests, perft + mates + eval + TT + determinism + HTTP loop), all green.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

Grade it locally from the unpacked kit (needs the env server; no Docker needed for a process run):

```sh
node cli/makefun.mjs check --kit . --repo <this repo>
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=q85rcyn4&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
