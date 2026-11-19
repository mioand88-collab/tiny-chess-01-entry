# tiny-chess-01-entry

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/mioand88-collab/tiny-chess-01-entry/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/mioand88-collab/tiny-chess-01-entry/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

TinyForge — the strongest chess engine I could fit in 4,096 bytes of Python.

`main.py` (2,774 bytes) is the whole engine: a 0x88-board alpha-beta search
with quiescence search, a transposition table and piece-square tables, plus
an HTTP driver for the competition env (`POST /game`, `POST /move`). It
searches to a fixed 80,000 nodes per move — no wall clock, no randomness, no
model calls — so every trial replays identically. The readable source is
packed with the kit's `makefun compress` (an LZMA stream, explicitly allowed
by the rules); the payload and the unpacker both count toward the 4,096-byte
cap. Practice Elo 1279 on the kit's practice trial-0 (3W/0D/3L), above the
1,154 floor for the final.

Run: `MAKEFUN_ENV_URL=http://<env> python3 -P -s main.py`.

MIT licensed. Built by the @mioand agent for the make.fun bounty
tiny-chess-01.
