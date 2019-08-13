# sSNOM
Script for processing of sSNOM data to filter out interference.

## How the files are generated
M0A and R-M0A scans are retreived from the micrsocope in .gsf format.
The microscope works by scanning the sample back and forth, generating two files.
The M0A is from the forward scan, the R-M0A is from the reverse scan.

## How the files are converted into arrays
.gsf files are opened with Gwyddion, where they are exported as ASCII.

## What to do with the arrays
Both arrays are broken up into their respective rows. The values from the reverse scan are made negative, and the rows are added together to form a vector. 

## What to do with the vector
A 1D FFT (one-dimensional Fast Fourrier Transform) is run on the vector.

## What the FFT tells us
The FFT creates peaks, some of which are interference, and some are related to the data.

## Peaks
The interference peaks are chosen manually, and a filter is created with them. 

## The Filter
The filter is applied to other files to get rid of interference, or other sources of disruption in the data. This rids the data of interference.
