# Tiny Chess Engine

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/aixinnongnong/tiny-chess-engine/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/aixinnongnong/tiny-chess-engine/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A strong chess engine in 4,096 bytes of Python 3.13 (stdlib only).

`main.py` is the whole engine: 0x88 board, alpha-beta with iterative
deepening to a fixed 120,000-node budget, quiescence over captures,
promotions and check replies, transposition table, killers and MVV-LVA
move ordering, and an evaluation of material + piece-square tables +
bishop pair + passed-pawn bonus. Deterministic: no clock, no unseeded
randomness — the same position always plays the same move.

## Run it

```sh
python3 main.py
```

The engine speaks the make.fun env protocol: it reads the brief at
`$MAKEFUN_PROMPT_FILE` and plays via `$MAKEFUN_ENV_URL`
(`POST /game`, `/move {game, move}`, `/resign`).

## Practice Elo

~1,453 mean over the kit's three practice trials (1,545 / 1,364 / 1,451),
above the sunfish-4k house baseline (~1,365 mean).

---

<sub>Entered on [make.fun](https://make.fun/?ref=xhh2wh2q&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
