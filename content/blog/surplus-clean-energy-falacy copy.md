---
title: "Surplus Clean Energy Fallacy"
---


This post explains why "surplus" clean energy bitcoin mining is a fallacy. 

I shall tackle the most generous scenario where clean electricity obtained at zero cost by a wind turbine operator and used for mining. (Note, Zero cost electricity is impossible as there will be operational costs).

Let the term 'Mining Ratio' refer to the mining income per unit energy divided by the electricity cost per unit energy. The miner aims to mine with the maximum average mining ratio over the lifetime of their hardware in order to maximize profit. There are three possible scenarios;

1. A miner operates only on the 'surplus' energy provided by the wind farm - they make relatively high profit per unit time (as energy is 'free') while mining but zero (mining) profit per unit time while there is no surplus energy.
2. A miner operates only on grid energy which has a non-zero cost but is available at all times.
3. A miner operates using surplus energy when possible and on grid energy when there is no surplus.

Let us compare these scenarios.
- Let the Mining reward per unit energy be M.
- Let the Energy cost per unit energy be E.
- Let Profit per unit energy be P. This is calculated as M-E.Let
- U be the mining time (as a fraction of total time).

The profit per unit time is given by P * U.

| Scenario	| Energy Source	| Energy Cost (E)	| Mining Time (U).	| Avg. Profit |
| -	| -	| -	| -	| - |
| 1 | Surplus |	0 |	X |	M*X |
| 2	| Grid	| E	| 1	| M-E |
| 3	| Surplus & Grid	| 0 Surplus & E Grid	| X Surplus & Y Grid 	| M*X + Y*(M-E) |

For the average profit of scenario 1 to equal that in scenario 2 it must be that: M*X = M-E

X is given by the product of the fraction of the time that the wind turbine is running (R) and the fraction of the time that it is required to shut off (S) when it could be generating. That is, X = R*S. I will find sources for this in the future but in my experience R is generally about 0.4. The value of S is harder to get data for but is surely below 0.1, thus X ≤ 0.04.

Given this estimate (and it is only an estimate) we can see that E = 0.96M.

Scenario 2 is more profitable than Scenario 1 if E < 0.96M. That is, if the Energy cost (Per J) is less than 96% of the Mining Income (Per J).

Obviously mining profitability changes, but to put this finding into context Jimmy Song [estimated](https://medium.com/@jimmysong/just-how-profitable-is-bitmain-a9df82c761a) that in 2017 Bitmain made about $120M/yr in mining profit on $23M/yr electricity (& data centre costs). This gives E=0.19M.

In the first scenario the miner is indeed only operating on surplus energy. However the back of the napkin calculations above show that for wind this option is far less profitable than option 2. They are only shut off when supply exceeds demand and they are the most expensive (flexible) energy source (shut off order occurs in reverse [Merit order](https://en.wikipedia.org/wiki/Merit_order). This means that the estimate of 0.1 for S is a conservative estimate.

The miner would make more profit operating the mining equipment under scenario 3. However, wind farm operators are paid to shut off their turbines, thus there is little incentive for turbine operators to waste time and energy outside their area of expertise to become miners. Gut reaction is to say that they will instead sell this energy to miners, but any miners using this energy would be switching to this intermittent energy source from the grid. Remember the only time wind turbines have 'surplus' energy is when supply exceeds demand, if miners temporarily shift away from the grid, the grid demand would drop further reducing demand leading to other wind turbines needing to shut off.

Finally, in the second and third scenario the miners add to base-load demand. As such - they are not operating solely on surplus energy - they are simply using energy like any other use case - **which is fine.**

Hydropower is often used to mine bitcoin but hydropower doesn’t have surplus supply as it forms the base-load in the grid and has a negligible unit cost thus has a very high merit order - it is never turned off, thus any mining using an existing well connected hydropower station is not using 'surplus' energy.

# Conclusion

Energy used to mine bitcoin is not wasted, there is no need to try and appease the mob by suggesting only surplus energy will be used. People are free to pay to use energy in whatever way they see fit. Miners chose to use energy to mine Bitcoin - thus it is not wasted. Read [Beautyon's](https://link.medium.com/xpTvZv1a29) work to understand this further. In the long run miners will be using renewable energy to mine, but no 'surplus' is needed for this.
