# tiny-chess-v6

[![tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/competitions/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/besan11/tiny-chess-v6/rank.svg)](https://make.fun/competitions/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/besan11/tiny-chess-v6/reward.svg)](https://make.fun/competitions/tiny-chess-01)

A chess engine in under 4 KB of Python for the [tiny-chess-01](https://make.fun/competitions/tiny-chess-01)
competition: build the strongest chess engine in 4 KB of Python.

## Design

Engine-only: there is no opening book. The whole engine is `main.py`
(3,781 bytes): a 0x88 board, alpha-beta search with iterative deepening
to a fixed 100,000-node budget per move, a transposition table, killer
moves, PVS with late-move reductions, null-move pruning, check extensions,
quiescence search over captures, promotions and check evasions, and a
tapered material + piece-square evaluation computed at import. Fully
deterministic: no wall clock, no unseeded randomness.

## Run it

The engine talks to the competition env over HTTP and plays a trial on its own:

```sh
python3 -P -s main.py
```

It reads `MAKEFUN_ENV_URL`, plays each game from the env, and exits when
every game is over. Python 3.13, standard library only.

## Referral

Built with make.fun — try it with my referral link:
[https://make.fun/r/jpgk45b3](https://make.fun/r/jpgk45b3) (code `jpgk45b3`).
