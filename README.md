# Effect of Features Generated from Adjacent and Overlapped Segments in Protein Sequence Classification

## Abstract
In protein sequence classification research, sequences must be converted into data that are understood by classification algorithms. Protein descriptor is the name of the tool to convert sequence into feature representation. There is two type of protein descriptor: the first is alignment-based descriptor or position-specific descriptor. The second is a position-independent descriptor

<img src="https://github.com/rezafaisal/ProteinSequenceClassificationProject/blob/master/images/01.JPG" width="400">

Position-independent descriptors convert a variable length sequence of protein into fixed length numerical features. These descriptors are useful since they apply to any length of a sequence, however, positional information of subsequence is discarded even though it might have a high contribution to classification performance. To solve this problem, we divided the original sequence into some segments. We generated to kind of segments those are adjacent segments and overlapped segments. Then we calculated the numerical features for them.

Features generated from adjacent and overlapped segments enables us to partially introduce positional information (for instance, compositions of serine in anterior and posterior segments of a sequence). Through comprehensive experiments on the number of segments and length of the overlapping region, we found our classification approach with sequence segmentation and feature selection is effective to improve the performance. 

## What has been done in existing researches?
There are two methods to generate new feature representation in active researches. First, A combination of various alignment free descriptors.
![combination of alignment free descriptors](https://github.com/rezafaisal/ProteinSequenceClassificationProject/blob/master/images/02.JPG)

Second, Combination of alignment free and alignment-based descriptor.
![alignment free & alignment-based descriptors](https://github.com/rezafaisal/ProteinSequenceClassificationProject/blob/master/images/03.JPG)

## What is new in our approach?
In existing reports, researchers only used an original sequence as the input to protein descriptor. We generate new feature representation by using additional segments.
![what is new](https://github.com/rezafaisal/ProteinSequenceClassificationProject/blob/master/images/04.JPG)

## Research Questions
The purpose of generating additional segments is to get more information. This illustration show the relation between number of additional segment and information. There are 2 type of information:
1. Position information, many segments will give rich position information.
2. Sequence information, few segment will give rich sequence information.
![problem](https://github.com/rezafaisal/ProteinSequenceClassificationProject/blob/master/images/05.JPG)

And, these are our research question:
1. What is the optimal way to create additional segments? (How many segment which is appropriate? Is it possible to get rich position and also sequence information?)
2. Can feature generated from additional inputs help to improve the accuracy prediction of the model?
3. Does this approach work on all protein classification problems?

## Method
Our approach has three steps to generate feature representation:
1. Sanity check of the amino acid types.
2. Generate additional segments.
3. Construct feature representation.

### Sanity check of the amino acid types
For the information, Protein descriptor functions in protr package only recognize 20 amino acids. For that reason, we have to eliminate amino acid that are not in these 20 amino acids.

Unrecognize code by protein descriptor function in PROTR:
* X: undetermined amino acid
* B: asparagine/N or aspartic acid/D
* Z: glutamic acid/E or glutamine/Q
* J: leucine/L or isoleucine/I
* O: Pyrrolysine (UAG)
* U: Selenocysteine (UGA)
![step-1](https://github.com/rezafaisal/ProteinSequenceClassificationProject/blob/master/images/06.JPG)

### Generate additional segments
We generate 2 type of additional segment in this process. The 1st type is adjacent segments, these segments are created by dividing original sequence with the same length. Second, overlapped segment are generated by using 2 adjacent segments:
* We divide each adjacent segment into 2 segment. 
* We use a half of 1st and 2nd adjacent segment, and we get the overlapped segment.
![step-2](https://github.com/rezafaisal/ProteinSequenceClassificationProject/blob/master/images/07.JPG)

### Construct feature representation
This process convert original sequence (blue), adjacent segments (orange) and overlapped segments (green) into feature representation. We convert original sequence and additional segments into feature representation by using existing protein descriptor in protr package.

This is formula if we use only one alignment free descriptor. If z = 2, we will use generated segments with k=2. If z=3, we will use generated segment with k=2 and k=3.
![step-3a](https://github.com/rezafaisal/ProteinSequenceClassificationProject/blob/master/images/08.JPG)

This is formula if we use a combination of various alignment free descriptors. Beside variable z, we also have variable type. For example, z=2 and we use 2 descriptors: AAC & DC.
![step-3b](https://github.com/rezafaisal/ProteinSequenceClassificationProject/blob/master/images/09.JPG)

## Summary
We developed simple but powerful approach to generate feature representation of protein sequence.
* Feature representation are generated by merging numerical feature of a original sequence, adjacent and overlapped segments.
* Adjacent and overlapped segments give position information.
* Evaluation on datasets from three protein classification cases.

Our approach achieved significant improvement in all cases which have a dataset with sufficient amino acid in each sequence.
* Our approach can be applied on single descriptor or a combination of various descriptor.
* But it cannot work well on cell-penetrating peptide prediction because sequences don’t have sufficient amino acids.

## Reference
[Improving Protein Sequence Classification Performance Using Adjacent and Overlapped Segments on Existing Protein Descriptors](http://www.scirp.org/Journal/PaperInformation.aspx?PaperID=85685)
DOI: [10.4236/jbise.2018.116012](https://doi.org/10.4236/jbise.2018.116012)
