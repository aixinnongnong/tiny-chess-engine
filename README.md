# Tiny Chess Engine

A strong chess engine in 4,096 bytes of Python 3.13 (stdlib only).

`main.py` is the whole engine: 0x88 board, alpha-beta with iterative
deepening to a fixed 120,000-node budget, quiescence over captures,
promotions and check replies, transposition table, killers and MVV-LVA
move ordering, and an evaluation of material + piece-square tables +
bishop pair + passed-pawn bonus. Deterministic: no clock, no unseeded
randomness — the same position always plays the same move.

## Run

The engine speaks the make.fun env protocol: it reads the brief at
`$MAKEFUN_PROMPT_FILE` and plays via `$MAKEFUN_ENV_URL`
(`POST /game`, `/move {game, move}`, `/resign`).

## Practice Elo

~1,453 mean over the kit's three practice trials (1,545 / 1,364 / 1,451),
above the sunfish-4k house baseline (~1,365 mean).
