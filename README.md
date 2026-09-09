# Hamming Code Decoding

A Jupyter notebook exploring Hamming error-correcting codes: the theory behind them, a complexity analysis of encoding/decoding, and a Python implementation applied to a simulated noisy communication channel between "Alice" and "Bob".

**Author:** Edoardo Iannucci (Mat. 47414A)

## Overview

The notebook (`hamming.ipynb`) is organized as follows:

1. **Introduction** — modeling noise on a communication channel between two parties, Alice and Bob, with a bit-flip probability `p_e`.
2. **Hamming codes** — how `(n, k)` Hamming codes work, the space overhead of parity bits, and the difference between:
   - **SEC** (Single-Error Correcting): detects and corrects a single bit error.
   - **SECDED** (Single-Error Correcting, Double-Error Detecting): adds a global parity bit to also detect (but not correct) double errors.
3. **The algorithm** — the syndrome-based decoding logic, including a matrix formalism (generator matrix `G` and parity-check matrix `H`), a correctness proof, and a big-O time-complexity analysis of both encoding and decoding (`O(n log n)` and `O(n)` respectively).
4. **Implementation** — a from-scratch Python implementation, applied to a concrete example: Alice encodes a text message, random bit errors are injected into the transmitted blocks, and Bob decodes (and where possible corrects) the received blocks to recover the original text.

### Key functions implemented in the notebook

| Function | Purpose |
|---|---|
| `string_to_binary` / `binary_to_string` | Convert text to/from a binary bit sequence |
| `parity_bits(k)` / `message_bits(k)` | Determine which block positions hold parity vs. message bits |
| `block_builder(data)` | Assemble a Hamming-coded block from a chunk of message bits |
| `parity(i, block)` / `global_parity(block)` | Compute individual and global parity bits |
| `make_errors(block, p)` / `bitflip(b)` | Simulate channel noise by randomly flipping bits |
| `sindrome(block)` | Compute the error syndrome of a received block |
| `hamming(block, secded)` | Decode a block, correcting single errors and (in SECDED mode) detecting double errors |

## Files

- **`hamming.ipynb`** — the main notebook containing theory, derivations, and implementation.
- **`Alice.txt`** — the original message sent by Alice: *"Ciao Bob! Come stai? Tutto bene? Chiamami appena hai tempo!"*
- **`Bob.txt`** — the message as reconstructed by Bob after decoding. Depending on the random errors introduced during the simulated transmission, some characters may remain corrupted (e.g. blocks with more errors than the code can correct), so this file may differ slightly from `Alice.txt` — this is the notebook's demonstration of the code's error-correction limits.

## Requirements

- Python 3 (tested on 3.12)
- Jupyter Notebook / JupyterLab

No external libraries beyond the Python standard library are required.

## Usage

1. Open `hamming.ipynb` in Jupyter.
2. Run all cells in order (theory cells are markdown; implementation and simulation are in the code cells near the end).
3. The notebook will encode the message in `Alice.txt`, simulate transmission errors, decode the result, print diagnostics on where/why decoding failed, and write the reconstructed message to `Bob.txt`.

## Notes

Since transmission errors are generated randomly, re-running the notebook will produce a different pattern of corrupted/corrected blocks each time — and therefore a potentially different `Bob.txt` — unless a random seed is fixed.
