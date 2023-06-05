# Loss Functions

## Softmax

`Softmax` is a function that converts predicted values into probabilities for multiple classification problems.

```py
def softmax(x):
	return torch.exp(x) / torch.exp(x).sum(dim=1,keepdim=True)

# dim=1 ==> will help us with taking Sum along columns (0 = sum along rows)
# keepdim=True ==>  this will retain dimensions hence we can run calculations

```
Let's assume these are our predictions
```py

act = torch.randn((6,2))*2
act 

==============result=================
tensor([[-0.0758,  0.7714],
        [-0.5243, -0.7601],
        [ 1.1320, -1.8671],
        [ 1.2885,  3.6635],
        [-1.6853, -1.4489],
        [ 0.1385,  3.2162]])
```

These are our results after running through `softmax` function

```py
sm_act  = softmax(act)
sm_act

==============result==================
tensor([[0.3000, 0.7000],
        [0.5587, 0.4413],
        [0.9525, 0.0475],
        [0.0851, 0.9149],
        [0.4412, 0.5588],
        [0.0440, 0.9560]])

# If we sum along columns then totals will add up to 1

```

## Negative Log Likelyhood (NLL)

**Step1** : Take a log of Softmax results (ignore this step for now). This will allow us to expand probabilities to infinite. 

**Step2** : Compare these results with actuals (targets) and pick the value that our model has predicted (i.e. if our first prediction should be 1 then select probability of 1 even if our model predicted incorrectly (i.e. higher probability for 0 ) )

Assume these are our targets:

```py

targ = torch.tensor([0,1,0,1,1,0])

sm_act  = softmax(act)
sm_act

==============results================
tensor([[0.3000, 0.7000],
        [0.5587, 0.4413],
        [0.9525, 0.0475],
        [0.0851, 0.9149],
        [0.4412, 0.5588],
        [0.0440, 0.9560]])

sm_act[range(6),targ] # Index slicing 

==============results================
tensor([0.3000, 0.4413, 0.9525, 0.9149, 0.5588, 0.0440]) # refer below table

```