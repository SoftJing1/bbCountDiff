# Basic Block Count Difference Script

This script compares the basic block counts collected by a proxy and the LLVM instrumentation pass. It processes the following input files:

- **Proxy file**: Contains basic block counts collected by the proxy.
- **LLVM raw profile file**: Contains basic block counts from the LLVM instrumentation pass.
- **IR file**: Intermediate representation file.

## Features

- Generates a text file with the basic block counts from the LLVM instrumentation pass.
- Compares the counts with those from the proxy file.
- Prints any differences found and returns a non-zero exit code.
- If no differences are found, prints a success message and returns a zero exit code.

## Installation

Clone the repository and ensure you have Python installed on your system:

```bash
git clone https://github.com/your-repo/bbCountDiff.git
cd bbCountDiff
```

Install any required dependencies:

```bash
pip install -e .
```

## Usage

```bash
python3 diff.py <proxy_file> <instr_raw_file> <ir_file>
```

Replace `<proxy_file>`, `<instr_raw_file>`, and `<ir_file>` with the appropriate file paths.

## Example

```bash
python3 diff.py proxy.txt default.profraw ir.ll
```

### Proxy File Example

An example of the `proxy.txt` file format:

```
-2046222912 for_begin_yy.for_end_yy_crit_edge.split.us.split.us59.us.us.us.13 0
-2046222560 for_begin_xx.for_end_xx_crit_edge.split.us50.us.us.us.us.13 0
-2046219264 for_begin_yy.for_end_yy_crit_edge.split.us.split.us59.us.us.us.8 0
-2046218960 for_begin_xx.for_end_xx_crit_edge.split.us50.us.us.us.us.8 0
-2046217696 vector.body282 0
-2046217600 middle.block275 0
```

Each line contains the basic block name followed by the count, separated by a space. Ensure the file is properly formatted for accurate comparison.

## Exit Codes

- **0**: No differences found.
- **Non-zero**: Differences detected.

Ensure all input files are correctly formatted and accessible before running the script.  