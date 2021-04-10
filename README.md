# linear-programming

## Procedure of making A

For each state increment its value by 1 (outgoing edges) for a given action (column), then take all the consequences and for all the consequences (rows in A matrix) subtract the probability it occurring if this action is taken(in this column)(incoming edges for those states).So if this action itself is a consequence it will get subtracted from itself, accommodating self loops.

## Procedure of finding policy and analysis
First we make x,R,A arrays then we try to maximise Rx given constraints Ax =alpha using cvxpy library.Return value would be the values of x array.Then for a state, we choose action with maximum value.We do this for all states and map states to actions to build the policy.


## Analysis:
Since we don't have reward for hitting MM , Indiana would prefer to take movement/stay actions and stay away from MM when MM is in ready state.This matches with policy.Most of the actions are STAY,or GATHER,CRAFT for South and North position as moving to center is riskier as we might get hit by MM causing negative reward.

## Multiple policies:
* There can be multiple policies, if values of x are same for single action then we can choose any one among them, resulting in multiple policies.This won't show any affect on A,r and alpha.
* Secondly, we are using fixed start state, we can change i.e, change values of alpha array then the policy changes. It would still not show any effect on A or R array. Introducing rewards changes.
* introducing final rewrads changes R array, this change also can make policy change.
