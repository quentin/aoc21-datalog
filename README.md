# Advent of Code 2021 in Datalog

[AoC21](https://adventofcode.com/2021) using [Souffle](https://souffle-lang.github.io/) datalog.

## How to run?

Puzzles are organized by day; answer to part 1 of day 1 is in `day01/day01a.dl`, answer to part 2 is in `day01b.dl`.
The datalog files have `.dl` extension. The input files have `.facts` extension.

```bash
cd day01
souffle -D- -F. day01a.dl
souffle -D- -F. day01b.dl
```

## What's happening?

By default only the `answer` relation is printed out and provides the answer to the puzzle.

You may want to reveal the content of any of the intermediate relation by adding the appropriate `.output`
directive in the datalog code.

For instance add the line `.output larger_than_previous` in `day01/day01a.dl` so that the `larger_than_previous` relation gets printed on the standard output.
