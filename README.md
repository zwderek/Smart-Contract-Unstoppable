# Smart-Contract-Unstoppable

### Challenge #1 - Unstoppable
There's a lending pool with a million DVT tokens in balance, offering flash loans for free.
If only there was a way to attack and stop the pool from offering flash loans ...
You start with 100 DVT tokens in balance.

### Solution
The poolBalance can only be uodated through the depositTokens, but the users can directly send tokens to the pool address.
For example, if the attacker sends 1 token to the pool address, the actual balance will be 1000001, but the poolBalance is stil 1000000.
In this way, the assumption: assert(poolBalance == balanceBefore) can be broken.
