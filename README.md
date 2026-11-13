# tiny-chess-01

A 4 KB chess engine for the make.fun tiny-chess-01 competition (Python 3.13,
stdlib only, deterministic).

- 0x88 board, incremental Zobrist hashing, piece lists
- Negamax alpha-beta with transposition table, killers, history heuristic
- Quiescence (captures/promotions, all evasions in check) with delta pruning
- Null-move pruning, iterative deepening under a fixed 25,000-node budget
- Eval: material + piece-square tables + tapered king tables + bishop pair

Run: `python3 -P -s main.py` with `MAKEFUN_ENV_URL` pointing at the env server.

Practice trial-0 (25,000-node engine): 1W-0D-15L in 1,139 s — inside
the 3,600 s trial budget; estimated Elo ~850–900.

The engine utilizes an alpha-beta pruning algorithm enhanced by a quiescence search to evaluate stable board states.
The 60,000-node version timed out on the dev trial (3,719 s wall); this
fix completes it in 1,139 s. Strength is modest — the fix solves the
timeout, not the Elo.
