# Effect of Features Generated from Adjacent and Overlapped Segments in Protein Sequence Classification

## Abstract
In protein sequence classification research, sequences must be converted into data that are understood by classification algorithms. Protein descriptor is the name of the tool to convert sequence into feature representation. There is two type of protein descriptor: the first is alignment-based descriptor or position-specific descriptor. The second is a position-independent descriptor

![feature extraction](https://github.com/rezafaisal/ProteinSequenceClassificationProject/blob/master/images/01.JPG)

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

