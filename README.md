# Crossword Solver
A Python implementation of a Constraint Satisfaction Problem (CSP)
Crossword Solver developed as the final project for PROG2301 –
Data Structures and Algorithms during the Summer Term 2026.

The project models crossword solving as a CSP and uses recursive
backtracking to assign words to crossword slots. Two solver versions
are included: a baseline implementation and an optimized version that
uses the Minimum Remaining Values (MRV) heuristic to reduce the
search space.

--- 

## Project Overview
The project contains two implementations of the crossword solver.

- `solver_initial.py` implements the original recursive
  backtracking algorithm.
- `solver.py` contains the optimized implementation, which
  applies the **Minimum Remaining Values (MRV)** heuristic to
  select the next crossword slot with the fewest possible
  candidate words.

Both implementations share the same CSP formulation and helper
functions. The primary difference lies in the variable-selection
strategy used during backtracking.

The repository also includes crossword rule validation,
benchmarking scripts, and test cases covering puzzles from
5×5 up to 15×15.

---

## Features
- Constraint Satisfaction Problem (CSP) formulation
- Recursive backtracking search
- Minimum Remaining Values (MRV) heuristic
- Crossword rule validation
- Memory benchmarking using `tracemalloc`
- NYT crossword rule validator (`rules.py`) 
- Visualization of benchmark results using `matplotlib`
- Test cases for multiple crossword sizes

--- 

## Repository Structure

```text
DSA-LT-4/
│
├── README.md
├── requirements.txt
│
├── src/
│   ├── __init__.py
│   ├── solver.py                  # Final CSP solver (MRV)
│   ├── solver_initial.py          # Initial solver (without MRV)
│   └── rules.py                   # Implementation of the crossword validation rules
│
├── tests/                         # All tests from 5x5 to 15x15 require solver.py to run first before the tests
│   ├── test_5x5_v1.py 
│   ├── test_5x5_v2.py
│   ├── test_7x7_v1.py
│   ├── test_7x7_v2.py
│   ├── test_10x10.py
│   ├── test_15x15.py
│   ├── test_15x15_two_removed.py
│   ├── test_15x15_ten_removed.py
│   ├── test_15x15_twenty_removed.py
│   ├── test_15x15_all_removed.py
│   └── test_rules.py               # Tests of the crossword validation rules
│
├── benchmarks/
│   ├── memory_usage.py             # Benchmarking script (measuring and comparing the memory consumption)
│   └── results/
│       ├── current_memory_usage.png
│       ├── peak_memory_usage.png
│       ├── memory_comparison_current_peak.png
│       ├── memory_comparison_15x15.png
│       └── memory_comparison_all.png
```

---

## Crossword Validation Rules
The project validates crossword grids using common New York Times (NYT)
construction rules.

Implemented rules include:

- 180° rotational symmetry
- Limited percentage of black squares
- No unkeyed letters
- Minimum word length of three letters
- Fully connected (interlocked) grid
- No repeated words
- Dictionary validation

---

## Supported Puzzle Sizes
The solver has been tested on:
- 5×5
- 7×7
- 10×10
- 15×15
- 15×15 with partially and completely removed words

---

## Benchmarks
Memory usage was measured using **tracemalloc**.

The repository includes benchmark visualizations comparing:

- Current memory usage
- Peak memory usage
- Current vs. peak memory
- 15×15 crossword performance
- Overall memory comparison

Benchmark figures are located in:

```text
benchmarks/results/
```

---

## Running the Project

Clone the repository:

```bash
git clone https://github.com/<username>/DSA-LT-4.git
cd DSA-LT-4
```

Install the required packages:

```bash
pip install -r requirements.txt
```

Run one of the test files:

```bash
python tests/test_10x10.py
```

Generate the benchmark graphs:

```bash
python benchmarks/memory_usage.py
```

---

## Code Style
The project follows **PEP 8** conventions and was checked using
`pycodestyle`.

--- 

## Requirements 
- Python 3.10 or later 
- matplotlib
- tracemalloc (standard library) 
- pycodestyle (optional) 

## Authors

Developed as the final project for PROG2301 – Data Structures and
Algorithms (LT4), Summer Term 2026.

Members of LT4:
- Ko, Deric Joaquin
- Peñaflor, Jzascha Vittoria
- Rempillo, Isaiah Christopher
- Ticke, Marcus Sebastian
- Yong, Chris John
- Valera, Chantelle


