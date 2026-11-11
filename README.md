# tiny-chess-01

A 4 KB chess engine for the make.fun tiny-chess-01 competition (Python 3.13,
stdlib only, deterministic).

- 0x88 board, incremental Zobrist hashing, piece lists
- Negamax alpha-beta with transposition table, killers, history heuristic
- Quiescence (captures/promotions, all evasions in check) with delta pruning
- Null-move pruning, iterative deepening under a fixed 60,000-node budget
- Eval: material + piece-square tables + tapered king tables + bishop pair

Run: `python3 -P -s main.py` with `MAKEFUN_ENV_URL` pointing at the env server.
