# Overview

Pinto faces the fundamental limitation that it cannot fix the Pinto price at its value target of $1, but instead must encourage widespread participation in target maintenance through protocol-native financial incentives. Low volatility is a function of how regularly the price of 1 Pinto oscillates across its target and the magnitude of price deviations from it.

The protocol has five direct target maintenance tools available:

1. Increase the [Pinto supply](overview.md#bean-supply);
2. Change the [Soil supply](overview.md#soil-supply);
3. Change the [Temperature](temperature.md);
4. Change the [Crop Ratio](crop-ratio.md); and
5. Sell Pinto ([Flood](flood.md)).

At the beginning of every [Season](https://docs.bean.money/almanac/farm/sun), Pinto evaluates its position (i.e., price, debt level and liquidity level) and current state (i.e., direction and acceleration) with respect to ideal equilibrium, and dynamically adjusts the Pinto supply, Soil supply, Temperature and Crop Ratio to move closer to ideal equilibrium.

[Conversions](convert.md) within the Silo between Pinto and LP Deposits serve a major role in target maintenance.

### **Ideal Equilibrium** <a href="#ideal-equilibrium" id="ideal-equilibrium"></a>

The protocol is in ideal equilibrium when the Pinto price, debt level and the liquidity level are all at their optimal levels. In practice, this requires that four conditions are met:

1. The price of Pinto is regularly oscillating around its value target;
2. The debt level is optimal;
3. The liquidity level is optimal; and
4. Demand for Soil is steady.

In order to return to ideal equilibrium, the protocol affects the supply of and demand for Pinto in response to the Pinto price, the debt level, the liquidity level and changing demand for Soil. It does so by adjusting the Pinto supply, Soil supply, Temperature and Crop Ratio.

Pinto supply increases primarily affect the Pinto price. Soil supply impacts the Pinto supply and the debt level. Temperature changes primarily affect demand for Soil. Crop Ratio changes primarily affect demand for Conversions between Pinto and LP token Deposits.

In order to make the proper adjustments, the protocol reassesses the states of both the Pinto and Soil markets at the beginning of each Season.

In practice, maintaining ideal equilibrium is impossible. Deviations from ideal equilibrium are normal and expected. As the protocol grows, the durations and magnitudes of deviations are expected to decrease.

### **Price Level** <a href="#decentralized-price-oracle" id="decentralized-price-oracle"></a>

Pinto's core objective is to oscillate the price of Pinto above and below its $1 target. The protocol infers the liquidity and time weighted price of 1 Pinto by calculating TWA∆P.

The protocol can be in 3 different states with respect to its price (not including optimal):

* Reasonably low price: Price < $1
* Optimal price: Price = $1
* Reasonably high price: $1 < Price ≤ $1.025
* Excessively high price: Price > $1.025

### **Debt Level** <a href="#debt-level" id="debt-level"></a>

The Pod Rate represents the protocol debt level relative to the Pinto supply. The Pod Rate is often used as a proxy for the protocol's health. If the Pinto supply is 1000 and there are 2000 [Pods](../farm/field.md#pods), the Pod Rate is 200%.

The protocol defines a handful of Pod Rate ranges that it uses as an input to determine how to change the Temperature:

* Excessively low debt: Pod Rate < 3%
* Reasonably low debt: 3% ≤ Pod Rate < 15%
* Optimal level of debt: Pod Rate = 15%
* Reasonably high debt: 15% < Pod Rate ≤ 25%
* Excessively high debt: Pod Rate > 25%

### Liquidity Level <a href="#liquidity-level" id="liquidity-level"></a>

The Liquidity Rate represents the protocol liquidity level relative to the Pinto supply. The Liquidity Rate is a useful indicator of the protocol's health.

In the context of the Liquidity Rate, liquidity is defined as the sum of the USD values of the non-Pinto assets in each pool on the [Deposit Whitelist](../farm/silo.md#deposit-whitelist). If there is $8M of non-Pinto liquidity in pools on the Deposit Whitelist and the Pinto supply is 16M, the Liquidity Rate is 50%.

The protocol can be in 4 different states in relation to its Liquidity Rate:

* Excessively low liquidity: Liquidity Rate < 12%;
* Reasonably low liquidity: 12% ≤ Liquidity Rate < 40%;
* Optimal level of liquidity: Liquidity Rate = 40%
* Reasonably high liquidity: 40% < Liquidity Rate ≤ 80%; or
* Excessively high liquidity: Liquidity Rate > 80%.

### **Pinto Supply** <a href="#bean-supply" id="bean-supply"></a>

At the beginning of each Season, the protocol increases the Pinto supply by TWA∆P if there was a time weighted average shortage of Pinto across the pools on the Minting Whitelist over the previous Season. Essentially, the protocol will mint the number of Pinto that need to be sold in the pools on the Minting Whitelist to return the Pinto price to $1.

Stalkholders and Pod holders each receive slightly less than half of new Pinto mints. See [Shipping Routes](../farm/sun.md#shipping-routes) for more information on the distribution of new Pinto mints.

### **Soil Supply** <a href="#soil-supply" id="soil-supply"></a>

When TWA∆P < 0, the Soil supply is based on the Liquidity Rate and [Cultivation Factor](../resources/glossary.md#cultivation-factor). The protocol increases the Cultivation Factor (and thus Soil issuance, a la the "snowball" effect)) when Pinto is Sown in all Soil in the previous Season. Conversely, if Pinto is not Sown in all Soil in the previous Season, the protocol decreases the Cultivation Factor more aggressively than it increases it. See [Section 12.3.1](https://pinto.money/pinto.pdf#subsubsection.12.3.1) of the whitepaper for complete formulas.

When TWA∆P ≥ 0, the protocol is still willing to issue debt in order to measure changing demand for [Soil](../farm/field.md#soil). The Soil supply is based on the number of Pods that become Harvestable at the beginning of the Season, the Temperature (see [Morning](temperature.md#morning) section), and the debt level. A greater number of Pods becoming Harvestable increases the Soil supply. Higher Temperature and debt level decrease the Soil supply. See [Section 7.12](https://pinto.money/pinto.pdf#subsection.7.12) of the whitepaper for complete formulas.
