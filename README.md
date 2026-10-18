# File Integrity Checker

A beginner Python project that uses SHA-256 hashes to detect
whether a file has changed from a saved baseline.

## Tools
- Python 3
- hashlib and pathlib from Python's standard library
- Thonny

## How It Works
The script reads sample.txt in 4,096-byte chunks and calculates
its SHA-256 hash.

If baseline.txt does not exist, it saves the current hash as
the baseline. On later runs, it compares the current hash
with that baseline and reports UNCHANGED or CHANGED.

If sample.txt is missing, it reports the missing file.

## How to Run
1. Download integrity_checker.py into a folder.
2. Create a plain-text file named sample.txt in that folder.
3. Run integrity_checker.py with Python 3.
4. Run it again without editing sample.txt to test UNCHANGED.
5. Edit and save sample.txt, then rerun to test CHANGED.
6. Temporarily rename sample.txt, then rerun to test a missing file.

Only create a baseline from a file you already trust.

## Tests Completed
| Test | Observed result |
| --- | --- |
| Unchanged file | UNCHANGED |
| Edited file | CHANGED |
| Renamed file | File missing: sample.txt |

Full results are recorded in test-results.txt.

## What I Learned
- How to calculate a file's SHA-256 hash.
- How to save and compare a baseline.
- How to check whether a file exists.
- How to test normal and missing-file conditions.

## Limitations
This script checks one file per run. It detects changes but
cannot determine whether they are malicious.

The baseline is stored as an unprotected local text file.
Someone who can replace both the file and baseline could
hide a change. Permission and other file-access errors
are not currently handled.

## Development
Built with AI guidance and tested locally using unchanged,
modified, and missing-file cases.