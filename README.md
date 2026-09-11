# sigbovik2024

Code behind the e-shuffledness section of *We Found the Best Shuffled Deck*,
Proceedings of SIGBOVIK 2024, pp. 70–82 (Section 3.8, Figure 14).

## What it does

Write a 52-card deck out as a string of card names — `ACE OF SPADES, TWO OF
SPADES, …` — and score the deck by how the letter E is distributed through
that string. `main.py` runs a local search over the deck order (pairwise
swaps, single-card moves, and small random shuffles), keeps the best deck it
finds for the chosen metric, and plots that deck next to a histogram of where
its E's fall — the figure in the paper.

Metrics (`--metric`): `max_entropy`, `min_entropy`, `max_std`, `min_std`.

## Files

- `main.py` — the search, the scoring, and the deck plotter
- `max_entropy_best_deck.json`, `max_std_best_deck.json`,
  `min_std_best_deck.json` — the best deck found for each metric, as a list
  of card numbers and as the deck string. These are the three decks in
  Figure 14 (a), (b), (c).

## Run

```
pip install fire tqdm numpy matplotlib
python main.py --metric max_entropy --num_runs 20
python main.py --metric max_entropy --search=False   # plot the saved deck only
```

A run starts from the saved deck for its metric when one exists and
overwrites the file only when it finds a better score, so the JSON files
only ever improve.

## History

Until September 2026 this folder lived at
`github.com/mattabate/wordplay/tree/main/sigbovik2024`, the address printed
in the paper. That path now points here; the commit history stays in
[wordplay](https://github.com/mattabate/wordplay).

## Citation

P. Mallory et al., "We Found the Best Shuffled Deck," *Proceedings of SIGBOVIK
2024*, pp. 70–82, 5 Apr. 2024.
https://sigbovik.org/2024/proceedings.pdf#page=74

## License

MIT.
