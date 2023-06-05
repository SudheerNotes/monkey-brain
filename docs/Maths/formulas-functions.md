# Formulas & Functions


## What is a Sigmoid function

The `sigmoid`  function always outputs a number between 0 and 1. Below code snippet is a python implementation of `Sigmoid` function

```py

def sigmoid(x): 
	return 1/(1+torch.exp(-x))

```

## What is L1 & L2 Norm

### L1 norm

Take the mean of the absolute value of differences (absolute value is the function that replaces negative values with positive values). This is called the mean absolute difference or L1 norm

```py
(preds - actuals).abs().mean()
```

### L2 norm

Take the mean of the square of differences (which makes everything positive) and then take the square root (which undoes the squaring). This is called the root mean squared error (RMSE) or L2 norm.

```py
(preds - actuals).sqr().mean().sqrt()
```