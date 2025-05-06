# Economics

Pinto is designed from economic first principles to create a useful trustless fiat currency. Over time, trustlessness, stability and liquidity increase, while carrying costs decrease but remain competitive. The following principles inspire Pinto:

* [Low concentration of ownership](economics.md#ownership-concentration);
* [Strong credit](economics.md#strong-credit);
* [The marginal rate of substitution](economics.md#marginal-rate-of-substitution);
* [Low friction](economics.md#low-friction);
* [Equilibrium](economics.md#equilibrium); and
* [Incentive structures determine behaviors of financially motivated actors](economics.md#incentives).

### Ownership Concentration <a href="#ownership-concentration" id="ownership-concentration"></a>

A design that lowers the [Gini coefficient](https://en.wikipedia.org/wiki/Gini_coefficient) of Pinto and Stalk over time is essential to censorship resistance.

Older Deposits have their Stalk from Seeds diluted relative to newer Deposits every Season. Therefore, newly minted Pinto are more widely distributed over time.

Pinto does not require a pre-mine. The first 1000 Pinto are created when the `init` function is called to deploy the protocol.

### Strong Credit <a href="#strong-credit" id="strong-credit"></a>

Pinto is credit based and only fails if it can no longer attract creditors. A reasonable level of debt, strong credit history and competitive interest rate attract creditors.

The protocol changes the [Temperature](../peg-maintenance/temperature.md) to return the Pod Rate to the [optimal Pod Rate](../peg-maintenance/overview.md#debt-level) while regularly crossing the Pinto price over its value peg. The protocol acts more aggressively when the Pod Rate is excessively high or low.

The protocol never defaults on debt (although in the event of the protocol no longer attracting creditors, the loan maturity date would become infinitely far in the future—see [Disclosures](../resources/disclosures.md)). The protocol is willing to issue Pods every Season.

### Marginal Rate of Substitution <a href="#marginal-rate-of-substitution" id="marginal-rate-of-substitution"></a>

There are a wide variety of opportunities Pinto has to compete with for creditors. Therefore, the protocol does not define an optimal Temperature, but instead [adjusts it to move closer to ideal equilibrium](../peg-maintenance/overview.md#ideal-equilibrium).

### Low Friction <a href="#low-friction" id="low-friction"></a>

Minimizing the cost of using Pinto and barriers to the [Farm](broken-reference) maximizes utility for users and appeal to creditors. The [Depot](../farm/toolshed/depot.md) realizes the full benefits of composability on Base.

The [FIFO](../resources/glossary.md#fifo) Pod Harvest schedule allows smaller [Sowers](../farm/field.md) to participate in peg maintenance and decreases the benefit of large scale price manipulation. The combination of non-expiry, the FIFO Harvest schedule, transferability and a [liquid secondary market](../farm/toolshed/pod-market.md) enables Sowers to Sow Pinto as efficiently as possible.

By maximizing the efficiency of the Soil market, the protocol minimizes its cost to attract creditors, the durations and magnitudes of price deviations below its value peg, and excess Pod issuance.

### Equilibrium <a href="#equilibrium" id="equilibrium"></a>

Equilibrium is a state of equivalent marginal quantity supplied and demanded. The protocol affects the supply of and demand for Pinto to regularly cross the equilibrium price of 1 Pinto over its value peg.

While the protocol can [arbitrarily increase the Pinto supply](../peg-maintenance/overview.md#bean-supply) when the price is above its value peg, the protocol cannot arbitrarily decrease the Pinto supply when the price is below it. The protocol relies on the codependence between the equilibria of Pinto and Soil, as well as [Conversions](../peg-maintenance/convert.md), to work around this limitation.

In order to Sow Pinto, they must be acquired (_i.e._, marginal demand for Soil affects marginal demand for Pinto). The marginal demand for Soil and Pinto are functions of the Temperature and the Pinto price. By [changing the Temperature](../peg-maintenance/temperature.md), the protocol affects decreases in the Pinto supply and changes in demand for Pinto.

### Incentives <a href="#incentives" id="incentives"></a>

Pinto-native financial incentives consistently increase trustlessness, stability and liquidity over time by coordinating independently financially motivated actors (_i.e._, Stalkholders and Sowers).

[The Stalk System](../farm/silo.md#the-stalk-system) incentivizes (1) leaving assets Deposited in the Silo continuously by creating opportunity cost to Withdraw assets from the Silo, (2) adding value to liquidity pools with Pinto by [rewarding more Seeds to at least 1 Deposited LP token](../peg-maintenance/crop-ratio.md) than Deposited Pinto, and (3) returning the Pinto price to its value peg by allowing Conversions within the Silo without forfeiting Stalk.

Anyone with Stalk stands to profit from future growth of the Pinto supply, but are not owed anything by the protocol.

When the Pinto price is below $1, there is an incentive to Withdraw assets from the Silo. The Stalk System reduces this incentive significantly.

When the Pinto price is above $1, there is an incentive to buy Pinto to earn a portion of the upcoming seigniorage. This is exacerbated when the Pod Rate is lower. The commitment to automatically return the Pinto price to its value peg and distribute proceeds from the sale to current Stalkholders based on Stalk ownership when it began Raining ([Flood](../peg-maintenance/flood.md)) removes this incentive entirely during Seasons where the previous Season's Pod Rate was excessively low, and reduces it significantly otherwise.

Thus, Pinto consistently increases trustlessness, stability and liquidity over time.
