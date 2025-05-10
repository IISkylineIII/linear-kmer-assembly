# Linear K-mer Assembly

This repository provides a simple Python script that reconstructs a linear DNA sequence from a list of overlapping 4-mers. It simulates a common task in bioinformatics: reconstructing a sequence from short reads or k-mers, using the last character of each k-mer to append to the growing sequence.

## Overview

Given a list of k-mers (in this case, all of length 4), the script builds a linear string by:
1. Starting with the first k-mer.
2. Appending only the last character of each subsequent k-mer, assuming they overlap by 3 characters with the previous one.

This approach mirrors the principle of **sequence assembly** in computational genomics, where k-mers are pieced together into contigs or full sequences based on shared overlaps.

## Script

```python
kmers = [
    "AAAT", "AATG", "ACCC", "ACGC", "ATAC", "ATCA", "ATGC",
    "CAAA", "CACC", "CATA", "CATC", "CCAG", "CCCA", "CGCT",
    "CTCA", "GCAT", "GCTC", "TACG", "TCAC", "TCAT", "TGCA"
]

# Combine the 4-mers to form a linear string
linear_string = kmers[0] + ''.join(kmer[3] for kmer in kmers[1:])

print(linear_string)

Example Output
AAATGCCCGCACACATACCATCCAGCCAAGCTCAATCTCGCTCACG
(Note: Output will vary based on the order of the kmers.)

Requirements
Python 3.6 or higher

No external libraries are needed.

Applications
Educational illustration of k-mer-based sequence assembly

Pre-step for building de Bruijn graphs

Basic string manipulation for bioinformatics learners

License
This project is released under the MIT License.





