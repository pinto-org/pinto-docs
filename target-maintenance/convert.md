# Convert

Conversions within the [Silo](../farm/silo.md) between Pinto and LP Deposits serve a major role in target maintenance.

Any Deposit in the Silo be Converted to any other asset on the [Deposit Whitelist](../farm/silo.md#deposit-whitelist) at any time for a gain or loss in Stalk and/or Seeds.

Seeds create marginal benefit for holding particular assets in the Silo in the form of Grown Stalk. Seed incentives for holding exposure to Pinto Deposits or the LP token with the most Seeds are determined by the [Crop Ratio](crop-ratio.md). Seed incentives for holding exposure particular LP tokens are determined by the [Gauge Points](../advanced/seed-gauge-system.md#gauge-points) and current vs. the optimal distribution of LP PDV (see [Deposit Whitelist](../farm/silo.md#deposit-whitelist) and [Gauge System](../advanced/seed-gauge-system.md) for more info).&#x20;

#### Converts between Pinto and LP Tokens

When the cumulative ∆P > 0, Deposited Pinto may be Converted to Deposited LP tokens in pools where ∆P > 0 while retaining grown Stalk from Seeds. This Conversion allows the Depositor to add Pinto to liquidity pools, which has the practical effect of selling Pinto above the target. In doing so, the protocol incentivizes Depositors to grow liquidity for Pinto at the expense of additional Pinto mints, as the price is decreased back towards the target.

When the cumulative ∆P < 0, Deposited LP tokens may be Converted to Deposited Pinto in pools where ∆P < 0 without forfeiting grown Stalk from Seeds or any Stalk due to LP impermanent loss. This Conversion allows Depositors to remove excess Pinto from liquidity pools and increase the price back towards the target without leaving the Silo, minimizing debt issuance.

Converting away from the target results in a 100% reduction in Grown Stalk of the Converted Deposit based on the amount that was Converted away from the target. For example, if 20 PDV is Converted, and only 10 of the PDV Converted is away from the target, then 50% of the Grown Stalk associated with Deposit will be burned. No penalty is applied if the Convert brings the cumulative ∆P closer to 0, except for Conversions from Pinto to LP tokens per the [Blight Factor](../resources/glossary.md#convert).

A Convert capacity mechanism exists to prevent flash loan attacks that would allow Converting away from the target without incurring the Stalk penalty: every Convert updates the amount of PDV Converted per block on a per Well and overall basis. The total capacity available before a penalty applies is based on ∆P for each corresponding pool and the cumulative ∆P.

#### Converts between LP Tokens

Deposited LP tokens can be Converted to any other Deposited LP token in the Silo at any time. The Seed rewards for each LP token adjust based on the Gauge Points and the current vs. the optimal LP PDV distribution. Read more about the Gauge System [here](../advanced/seed-gauge-system.md).

The same Stalk penalty and Convert capacity mechanism exist for Converts between LP tokens.

#### Converts to the same Deposit token

Any Deposit in the Silo can be "Converted" to the same token in order to update the Deposit's PDV (and in doing so, be credited with additonal Stalk and/or Seeds) when the PDV of the LP token _increases_ due to impermanent loss.

Similarly, any account on Base can "Convert" a Farmer's Deposit to the same token in order to update the Deposit's PDV when the PDV of the LP token _decreases_ due to impermanent loss (and in doing so, marginally increase their own Stalk ownership).

Converts to the same Deposit token do not directly contribute to target maintenance.
