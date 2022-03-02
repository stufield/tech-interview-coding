
# Technical Skills Exercise

Below is a real world example of a problem that regularly occurs 
in the SomaLogic data science workflow.


## Background

Every 6 months, samples from two subjects are run through the assay, with each sample run 
three times each (for a total of 6 runs). Predictions for the SomaSignal Tests are then 
made for each of the 6 runs and the average for each subject is calculated.
This process is part of maintaining our regulatory certification.
The final deliverable looks like this:

```bash
##   SubjectId mean\_testA mean\_testB
## 1         1       0.69   62.26667
## 2         2       0.63   61.74000
```

The current method for providing this final table involves a lot of cutting and pasting,
because the files are disjoint. We want to move as far away as possible from any
cut-and-paste operations, as they are very error prone. The information we need to
calculate the table comes from two files, a predictions file and an ID file.

`Predictions.csv` file:

```bash
##   barcode testA testB
## 1      d2  0.71 62.37
## 2      a4  0.63 62.72
## 3      y3  0.67 62.74
## 4      g6  0.69 61.69
## 5      w5  0.67 60.19
## 6      b1  0.59 62.31
```

In `Predictions.csv`, we have predictions for testA (probability) and testB (linear response).

* The first column contains a barcode that is tied back to an individual
* The second and third columns contain the predictions

`Barcode.csv` file:

```bash
##   SubjectId barcode_1 barcode_2 barcode_3
## 1         1        y3        d2        g6
## 2         2        a4        b1        w5
```

This file allows us to link the barcodes in the predictions file to specific subjects.

* The first column contains the `SubjectId`
* The remaining columns contain the barcodes for the three replicate runs


## Instructions
Open the `tech-exercise.Rmd` file and follow the directions inside.


