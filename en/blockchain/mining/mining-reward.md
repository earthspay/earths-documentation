# Mining reward

## Description

It is proposed to add a **reward for mining** on the Waves blockchain. The miner will be rewarded with WAVES for each of the generated blocks.

This new feature implies the additional issue of WAVES tokens.

## Rationale

In the current model, miners earn only transaction fees; their income is less than 1% per annum.

The mining reward will increase the revenue for the miners. Once the new model is introduced, the miners' income will be increased to 7% per annum.

## Reward amount

The proposed initial reward is equal to 6 WAVES for each of the generated blocks. This amount of reward will remain the same for 100,000 blocks, i.e. approximately for 2.5 months. The amount of the reward for the next 10,000 blocks will be determined by the miners during the standard voting procedure.

## Voting

Every 100,000 blocks miners vote for increasing, decreasing, or saving the current reward value.

If a miner does not set up explicitly within the node configuration file whether they want to vote for increasing, decreasing, or saving the reward amount, then by default they will be voting for keeping the reward amount unchanged.

The step of changing the reward is equal to 0.5 WAVES. For example, if the current amount of reward is 7 WAVES, and the miners voted for reducing the reward, then the new amount of reward will be 6.5 WAVES.

For the new reward value to take effect, more than 50% of the block generators must vote for it.

The new amount is valid for the next 100,000 blocks.

The voting process is repeated every 100,000 blocks and lasts for 10,000 blocks.
