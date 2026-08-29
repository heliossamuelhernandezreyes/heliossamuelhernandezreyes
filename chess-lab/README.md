# Texcatlipocatl Chess Lab

Automated PGN analysis with Stockfish + python-chess.

## How it works

1. Put a `.pgn` file in `chess-lab/games/` on branch `chess-lab`.
2. GitHub Actions installs Stockfish and analyzes the game at depth 20 with MultiPV 3.
3. Results are written to `chess-lab/analysis/<game>.md` and `.json`.
4. The Markdown report contains each played move, Stockfish's best move, evaluation, centipawn loss, and a simple classification (ok / inaccuracy / mistake / blunder).

The JSON file is intended for longitudinal statistics: openings, recurring tactical errors, conversion rate, performance with White/Black, and style analysis.

## Local command

```bash
pip install -r chess-lab/requirements.txt
python chess-lab/analyze.py chess-lab/games/your-game.pgn --depth 20 --multipv 3 --outdir chess-lab/analysis
```

Stockfish defaults to `/usr/games/stockfish`; set `STOCKFISH_PATH` if needed.
