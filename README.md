# Advent of Code 2021 in Datalog

[AoC21](https://adventofcode.com/2021) using [Souffle](https://souffle-lang.github.io/) datalog.

## How to run?

Puzzles are organized by day; answer to part 1 of day 1 is in `day01/day01a.dl`, answer to part 2 is in `day01b.dl`.
The datalog files have `.dl` extension. The input files have `.facts` extension.

### Interpreter mode

The quickest way to run a datalog program is to execute Souffle in interpreter mode.
The interpreter mode may use `N` threads with option `souffle -j N`.

```bash
cd day01
souffle -D- -F. day01a.dl
souffle -D- -F. -j 4 day01b.dl
```

### Compiled mode

For long programs, or programs with large input, Souffle can generate c++ code.

```bash
cd day06

# compile, run on 8 threads and drop the executable
souffle -D- -F. -j 8 -c day06a

# compile and keep the executable
souffle -D- -F. -o day06a day06a.dl
# run on 4 threads
./day06a -j 4
```

## What is going on?

By default only the `answer` relation is printed out and provides the answer to the puzzle.

You may want to reveal the content of any of the intermediate relation by adding the appropriate `.output`
directive in the datalog code.

For instance add the line `.output larger_than_previous` in `day01/day01a.dl` so that the `larger_than_previous` relation gets printed on the standard output.
