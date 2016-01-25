#SSW: A Python Wrapper for the SIMD Smith-Waterman

## Overview

[SSW][ssw_repo] is a fast implementation of the Smith-Waterman algorithm, which
uses the Single-Instruction Multiple-Data (SIMD) instructions to parallelize
the algorithm at the CPU level.  This repository wraps the SSW library into an
easy to install, high-level python interface with no external library dependancies.

The SSW library is written by Mengyao Zhao and Wan-Ping Lee, and this python
interface is maintained by Giles Hall.

## Installation

To install the SSW python package, use pip to install the current master archive:

```
$ pip install https://github.com/vishnubob/ssw/archive/master.zip
Collecting https://github.com/vishnubob/ssw/archive/master.zip
Downloading https://github.com/vishnubob/ssw/archive/master.zip
/ 16kB 661kB/s
Installing collected packages: ssw
  Running setup.py install for ssw
Successfully installed ssw-0.1
```

## Example Usage

```
import ssw
aligner = ssw.Aligner()
alignment = aligner.align(reference="ACGTGAGAATTATGGCGCTGTGATT", query="ACGTGAGAATTATGCGCTGTGATT")
print(alignment.alignment_report)
Score = 45, Matches = 24, Mismatches = 0, Insertions = 0, Deletions = 1

ref   1   ACGTGAGAATTATGGCGCTGTGATT
          ||||||||||||| |||||||||||
query 1   ACGTGAGAATTAT-GCGCTGTGATT
```

[ssw_repo]: https://github.com/mengyao/Complete-Striped-Smith-Waterman-Library
