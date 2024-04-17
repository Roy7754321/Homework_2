# Homework_2
3-1
![image](https://github.com/Roy7754321/Homework_2/assets/57666321/ef64b6a4-8da4-409f-9400-dd571254a318)


3-2
![image](https://github.com/Roy7754321/Homework_2/assets/57666321/f02013b5-e1cb-44d1-831c-193b0fe31ee8)

3-3

(1)
Provide your profitable path, the amountIn, amountOut value for each swap, and your final reward(your tokenB balance).
![image](https://github.com/Roy7754321/Homework_2/assets/57666321/9c010b7c-0a89-457f-bedd-b5546674e2cb)

(2)
What is slippage in AMM, and how does Uniswap V2 address this issue? Please illustrate with a function as an example.

a.
Slippage in AMMs refers to the difference between the expected price of a trade and the price at which the trade is executed. This discrepancy can occur due to changes in a pool's token reserves between the time a transaction is submitted and when it is executed.

b. 
Uniswap V2 addresses slippage by: Price Impact Limitation: Users can set a maximum slippage tolerance.
The swap transaction reverts if the actual price deviates more than the specified tolerance.
Constant Product Formula: Ensures price adjusts with pool reserve changes.
![image](https://github.com/Roy7754321/Homework_2/assets/57666321/86cc48f8-63bb-4f8a-9481-60825e21d97c)

(3)
Please examine the mint function in the UniswapV2Pair contract. Upon initial liquidity minting, a minimum liquidity is subtracted. What is the rationale behind this design?

When the mint function is first called in the UniswapV2Pair contract, a small amount of liquidity tokens, typically MINIMUM_LIQUIDITY of 1000 tokens, is permanently locked in the pool. This is to prevent issues with rounding errors on very small amounts of liquidity that could lead to non-intuitive results or exploits due to extremely high values due to very small liquidity values.

(4)
Investigate the minting function in the UniswapV2Pair  contract. When depositing tokens (not for the first time), liquidity can only be obtained using a specific formula. What is the intention behind this?

For deposits after the initial creation of the pool, liquidity tokens are  minted based on the relative contribution to the pool's reserves. The formula is:
![image](https://github.com/Roy7754321/Homework_2/assets/57666321/ca59ea13-5780-48c5-8071-041ff624843e)
This design ensures that the share of the pool a liquidity provider receives is proportional to their contribution relative to the existing total reserves. This preserves fairness and maintains value for all liquidity  providers.

(5)
What is a sandwich attack, and how might it impact you when initiating a swap?

A sandwich attack is a manipulation technique where an attacker sees a pending swap transaction on the blockchain and places one order directly before and one directly after the targeted transaction. The first order increases the price of the swap, and the second order profits from the artificially inflated price, at the expense of the user caught in the middle
