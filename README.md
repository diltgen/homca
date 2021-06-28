# homca

An extension for L. Lewark's program "khoca" (available [here](https://github.com/LLewark/khoca)) for computing (reduced) Z[G]-homology. It takes as input a plain-text file containing the output of khoca when run with the parameters "0 e2 0" and "calcred0" (i.e. the reduced Z[G]-complex) and tries to decompose the chain complex into direct summands that are as simple as possible (in terms of rank) and from which the homology can be read off.

# Installation

homca is written in Sage with Python and comes packed as a Jupyter Notebook (hence the .ipynb file extension). In order to run it, you need to have:

1. [khoca](https://github.com/LLewark/khoca);
2. [SageMath](https://www.sagemath.org/) (v.9.2.0 or higher);
3. [Jupyter (Notebook)](https://jupyter.org/install).

To run homca, simply open a terminal and type "jupyter notebook" to start Jupyter Notebook and open the file "homca.ipynb". You should now see the input cell with the source code. Below the big "Setup"-Box, specify the path to your khoca output file and directly below the name of the file (if you already have one). This completes installation.

# How to use

1. If you don't already have a khoca output file for which you would like to compute the homology, run khoca as follows: "./khoca.py 0 e2 0 KNOT calcred0 > /path/to/save/output/output.txt", where KNOT is your knot encoded in one of khoca's supported options (e.g. braid or PD), and "/path/to/save/output/output.txt" is the path where you would like to save the output-file (the name of the file may be changed).
2. In homca, specify the path of your khoca output file and directly below the name of the file.
3. Set printing options (see below).
4. Hit "Shift+Enter".

# Printing options

homca features various options for printing the output. These include:

1. printing the simplified matrices of the differentials ("prntmatrices");
2. printing the direct summands obtained from the simplified matrices of each differential ("prntpieces");
3. printing summands that are supported in more than two homological degrees ("prntchains");
4. printing the (unique) direct summand of odd rank ("prntoddpiece").

Parameters for the printing options are stored as python lists; check homca to see the options.

# IMPORTANT

homca tries to simplify the Z[G]-complex as much as possible by performing elementary row- and column-operations on the differentials. As Z[G] is no PID, this might not always produce the optimal result (i.e. there may appear direct summands that can be further decomposed). Therefore, one has always to check by hand if the resulting summands are indecomposable (which is crucial for computing the correct homology). Also, as of now Gaussian elimination is not implemented, which makes it likely that for big knots (e.g. 30+ crossings) the result is hardly usable.

# To be implemented

1. Gaussian Elimination.
2. Option for printing direct summands containing higher powers (greater or equal than 2) of G.

If you encouter bugs or have any questions, please send an e-mail to damian.iltgen@mathematik.uni-regensburg.de
