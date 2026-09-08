# Data Structures & Algorithm Course Project

Academic Year: 2025/2026

## Overview

This repository contains the projects, assignments and exercises for the Data Structures & Algorithms (DSA) course for the academic year 2025/2026.

The goal of this repository is to provide a single place where students can find:

- course programming assignments and reference implementations
- problem statements and example inputs/outputs
- unit tests and evaluation scripts
- notes, explanations and complexity analyses for implemented algorithms

This README gives an overview of the repository structure, how to run and test the code, contribution guidelines, and useful links.

## Table of contents

- [Repository structure](#repository-structure)
- [Getting started](#getting-started)
- [How to run solutions](#how-to-run-solutions)
- [Testing and evaluation](#testing-and-evaluation)
- [Coding style and conventions](#coding-style-and-conventions)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Repository structure

The repository is organized so each assignment or topic has its own subdirectory. A typical layout looks like:

- README.md                     — this file
- assignments/                   — assignment descriptions and input files
  - assignment-01/
  - assignment-02/
- src/                           — source code (organized by language or problem)
  - python/
  - cpp/
  - java/
- tests/                         — unit tests and example testcases
- docs/                          — notes, proofs, complexity analysis, and diagrams
- examples/                      — small example inputs and expected outputs

Each assignment folder should include a brief DESCRIPTION.md and at least one example input and output file. Each language subfolder in `src/` should contain a README with build/run instructions specific to that language.

## Getting started

Prerequisites

- Git (to clone the repository)
- One or more language runtimes/compilers depending on the exercises in `src/` (for example: Python 3.8+, g++ for C++, OpenJDK for Java)

Clone the repository:

```bash
git clone https://github.com/edoiannu/DSA_Project.git
cd DSA_Project
```

Check the `src/<language>/README.md` and the specific assignment folder for per-exercise instructions.

## How to run solutions

This repository may contain multiple languages. Follow the per-language README files. Example commands for common languages:

Python

```bash
# run a solution file
python3 src/python/problem_name.py < input.txt
```

C++

```bash
# compile
g++ -std=c++17 -O2 -o bin/problem src/cpp/problem.cpp
# run
./bin/problem < input.txt
```

Java

```bash
# compile
javac -d bin src/java/Problem.java
# run
java -cp bin Problem < input.txt
```

If an assignment uses a Makefile or build script, prefer those to the manual commands above.

## Testing and evaluation

Automated tests are kept in the `tests/` directory. Where provided, use the included test runner or the language-specific testing framework (pytest, GoogleTest, JUnit, etc.). Example (Python / pytest):

```bash
# from repository root
pytest -q
```

There may also be evaluation scripts in `assignments/assignment-XX/evaluate.sh` which run reference tests and produce a score or pass/fail report.

## Coding style and conventions

- Write clear, well-documented code. Add a short comment describing the algorithm and its time/space complexity at the top of each solution file.
- Prefer readability over clever one-liners. Use meaningful variable names and small helper functions.
- Keep functions single-purpose and aim for modular solutions.
- Include tests or at least example inputs/outputs for your solution.

## Contributing

Contributions are welcome from students and instructors. Suggested workflow:

1. Fork the repository and create a topic branch for your work: `git checkout -b feature/assignment-01-solution`
2. Add your solution to the appropriate `src/<language>/` folder and include tests or example inputs in `examples/` or `tests/`.
3. Run existing tests and add new tests that validate your code.
4. Open a pull request describing what you changed and why.

When submitting assignment solutions, follow the academic integrity rules of the course — only submit your own work unless collaboration is explicitly allowed.

## License

No license file is included in the repository. If you want to apply a license (for example, MIT), add a `LICENSE` file to the repository or update this section to reflect your chosen license.

## Contact

Repository owner: @edoiannu

For questions about the course material, contact the course instructors or open an issue in this repository with the `question` label.

---

If you want, I can also:

- add per-language README templates (Python/C++/Java) under `src/`
- create a CONTRIBUTING.md and ISSUE_TEMPLATE
- add a sample assignment with evaluation scripts

Tell me which of the above you'd like and I'll add it.