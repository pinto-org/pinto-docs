# Seed Gauge System

Seeds generate opportunity cost for Withdrawing assets that have been Deposited in the [Silo](../farm/silo.md) for longer and marginal benefit for holding particular assets in the Silo in the form of Grown Stalk. The Gauge System adjusts the Seeds per PDV (Pinto Denominated Value) reward for holding different Deposited tokens in the Silo.

There are 3 primary tools that Pinto has at its disposal as a result of the Gauge System:

1. [The Target Seasons to Catch Up](seed-gauge-system.md#grown-stalk-inflation-rate), which determines the target number of Seasons for a new Deposit with an average number of Seeds to catch up to the average Grown Stalk per PDV of existing Deposits (at the time of Deposit);
2. Pinto vs LP Seed distribution, or more specifically, the [Crop Ratio](../target-maintenance/crop-ratio.md), which determines the relative benefits of holding Pinto exposure vs exposure to the LP token with the most Seeds in the Silo over time; and
3. LP vs LP Seed distribution, which determines relative benefits of holding a given non-Pinto asset in the Silo over time.

#### Grown Stalk Inflation Rate <a href="#grown-stalk-inflation-rate" id="grown-stalk-inflation-rate"></a>

The Grown Stalk per PDV for a Deposit can be thought of as the age of that Deposit—the longer the Deposit has been in the Silo, the higher its Grown Stalk is relative to its PDV. Thus, the average Grown Stalk per PDV is a measure for how old Deposits are across the entire Silo relative to the total PDV in the Silo.

The Gauge System enables Pinto to target an amount of Grown Stalk per PDV that should be issued each Season. In particular, the protocol sets the target number of Seasons for a new Deposit with an average number of Seeds to catch up to the average Grown Stalk per PDV of existing Deposits at the time of Deposit — or in other words, the Target Seasons to Catch Up. The Target Seasons to Catch Up is currently set to 4320 Seasons, or \~6 months.

The Target Seasons to Catch Up has no effect until at least that many Seasons have passed since the deployment of Pinto. There is a minimum Grown Stalk issuance per PDV of 2, and the Grown Stalk issuance per PDV is initialized at deployment to 3. After 4320 Seasons have passed, the Grown Stalk issuance per PDV stays 3 until the actual average Grown Stalk per PDV reaches this threshold.

#### **Gauge Points** <a href="#gauge-points" id="gauge-points"></a>

Gauge Points determine how the Grown Stalk issued in a Season should be distributed between LP tokens on the [Deposit Whitelist](../farm/silo.md#deposit-whitelist). Only whitelisted LP tokens have Gauge Points. Gauge Points can range from 0 to 1000.

Every Season, Pinto calculates the new number of Gauge Points for a LP token by calling each whitelisted LP token's Gauge Point function. All whitelisted LP tokens use the same Gauge Point function.

The Gauge Point function changes the Gauge Points for a whitelisted LP token as follows:

* If the current % of Deposited LP PDV is within 10% of optimal (normalized to the optimal allocation), the Gauge Points remain constant (i.e., if PINTOUSDC LP's optimal allocation is 25%, if the current allocation ranges from 22.5% to 32.5%, the Gauge Points remain constant);
* If the current % of Deposited LP PDV is outside of this constant range and greater than optimal, the Gauge Points decrease; and
* If the current % of Deposited LP PDV is outside of this constant range and less than optimal, the Gauge Points increase.

See the [Pinto Dune](https://dune.com/pintomoney/pinto) to view the current vs. optimal allocations and distribution of Gauge Points.

#### **Crop Ratio** <a href="#crop-ratio" id="crop-ratio"></a>

Gauge Points per PDV is the amount of Gauge Points allocated to a whitelisted LP token divided by the total PDV of that LP token Deposited in the Silo. The whitelisted LP token with the largest Gauge Points per PDV is used to determine the distribution of Grown Stalk to Pinto in the Silo in order to ensure that at least 1 LP token always receives at least as much Grown Stalk as Deposited Pinto. Ensuring that 1 whitelisted LP token (_i.e._, the LP token with the highest Gauge Points per PDV) is always allocated at least as many Seeds as Pinto ensures that the protocol never incentivizes holding Pinto over providing liquidity.

See [Crop Ratio](../target-maintenance/crop-ratio.md) for more info.
