# PSVAR
Panel SVAR estimation program

This Python (3.9) Jupyter notebook program adapts SVAR estimation to panel data. It uses LSDV OLS to estimate the reduced form VAR and groups the residuals to form a single covariance matrix (much like the STATA xtvar package by Tobias Cagala and Ulrich Glogowsky, Boston College). The covariance matrix is then Choleski decomposed to recover the structural model.

To set up, make sure that the pandas, numpy, and matplotlib libraries are installed. The data must be in excel (xlsx) file format. The program requires that:
1. The spreadsheet contains a column that labels each panel member observation.
2. The spreadsheet contains a column that indexes time (preferably in integer format, cannot guarantee other date formats will work).
3. The panel is balanced.
See the data.xlsx file for an example structure.

Specify the model you would like to estimate in the first cell (e.g. lag length, causal ordering of the covariates, etc.). Then, run all cells. The program will save three files:
1. A .npy file containing bootstrapped IRFs and CIRFs used for confidence interval estimation.
2. A .npy file containing series of IRFs and CIRFs, as well as their confidence intervals.
3. A .png file containing a plot of the user-specified impulse and response variables.

P.S.: The program is a simpler version of the one used in my economics M.Sc. thesis, "Does Labour Work" (Pawlowski, Vahnberg, 2023). The thesis offers a substantially more explicit explanation of the estimation method, and I encourage you to read it (specifically, the Estimation procedure and relevant appendix sections). Given that Panel SVAR is a relatively new and unexplored of econometrics, the paper may be of some use to those who are also considering this approach.
