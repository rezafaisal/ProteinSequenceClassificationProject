# ProtSegR

ProtSegR is R Package for Generating Segments and Numerical Representation Schemes for Protein Sequences described in Mohammad Reza Faisal et al. (2018) <DOI: [10.4236/jbise.2018.116012](https://doi.org/10.4236/jbise.2018.116012)>

## Installation
To install the latest version on GitHub:
```
devtools::install_github("rezafaisal/ProtSegR")
```

## Description
This package has 3 main functions:
1. RemoveUnrecognizeAminoAcid.
2. GenerateSegments.
3. ConvertToFeatureRepresentation

### RemoveUnrecognizeAminoAcid
This function remove amino acid code that is not in these 20 amino acids: Glycine/G, Alanine/A, Valine/V, Cysteine/C, Proline/P, Leucine/L, Isoleucine/I, Methionine/M, Tryptophan/W, Phenylalanine/F, Lysine/K, Arginine/R, Histidine/H, Serine/S, Threonine/T, Tyrosine/Y, Asparagine/N, Glutamine/Q, Aspartic Acid/D, Glutamic Acid/E.

### GenerateSegments
This function generate adjacent and overlapped segments from a protein sequence.

### ConvertToFeatureRepresentation
This function generate feature representation from original sequence, adjacent and overlapped segments.
