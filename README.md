# Simulated Annealing for 3-SAT

This project uses a simulated annealing heuristic to search for assignments that satisfy as many clauses as possible in 3-SAT instances. It is implemented as an interactive Jupyter notebook and includes DIMACS CNF input files.

## How It Works

The notebook reads a DIMACS CNF file, represents a candidate assignment as a binary vector, and evaluates it by counting satisfied clauses. It then repeatedly generates neighboring assignments by flipping a small percentage of variables. Better assignments are accepted; worse assignments may also be accepted according to the Metropolis criterion, with acceptance becoming less likely as the temperature decreases.

The search tracks the best assignment found and stops when it reaches the evaluation limit or the temperature threshold. Since simulated annealing is a heuristic, it may not find an assignment satisfying every clause.

## Project Contents

- `main.ipynb` - DIMACS parser, objective function, simulated annealing implementation, and convergence plot.
- `instances/uf20-01.cnf` - 20 variables and 91 clauses.
- `instances/uf100-01.cnf` - 100 variables and 430 clauses.
- `instances/uf250-01.cnf` - 250 variables and 1,065 clauses.

The notebook uses `uf20-01.cnf` by default. To run a different instance, change the filename in the execution cell near the end of the notebook.

## Requirements

- Python 3
- Jupyter Notebook or JupyterLab
- Matplotlib

Install the Python packages with:

```bash
python -m pip install jupyter matplotlib
```

## Run

From the project directory, start Jupyter:

```bash
jupyter notebook main.ipynb
```

Run the notebook cells in order. The final execution cell loads the selected instance, runs simulated annealing, prints the best number and percentage of satisfied clauses, and displays a convergence plot.

The default search parameters in that cell are an initial temperature of `100.0`, cooling factor `0.99`, `100` iterations per temperature, and a maximum of `200000` objective evaluations.
