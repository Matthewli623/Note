# Linear Regression Note

## Linear Regression

For y and X has linear relationship

### Aims

Backward Elimination

- SL=0.05
- Find highest P-value If P > SL,else FIN
- Remove the predictor
- P is the importance of the coefficients

### Simple Linear Regression

- y = B0 + B1x1
- y is Dependent(DV)
- X1 is IV

### Multiple Linear Regression

- y = B0 + B1x1 + B2x2+... + Bnxn

### Polynomial Linear Regression

- y = B0 + B1x1 + B2x^2+... + Bnx2^n

### Prevent Dummy Variables

If select only one in A and B, Delete B

### Loss Function

- SSRes = Sum(y1 - ŷ1)->min
- SSTot = Sum(y1 - ŷavg)->min
- Max(R^2) = 1 - SSRes/SSTot
- Adj R^2) = 1 - (1-R^2)
