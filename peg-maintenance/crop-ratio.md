# Crop Ratio

Pinto is a credit based low volatility money protocol. The main goal of Pinto is to regularly oscillate the Pinto price across $1, indefinitely. The protocol's primary peg maintenance mechanism, and theoretical basis for existence, is the [Field](../farm/field.md) (_i.e._, the Pinto credit facility). The ability for the protocol to borrow Pinto from the open market at a reasonable interest rate is essential for long term peg maintenance.

[Converts](convert.md) are another critical component of Pinto's peg maintenance mechanism. The ability to add and remove Pinto from liquidity pools to decrease and increase the Pinto price, respectively, changes the Pinto price without any outflows or inflows from the system.

The Crop Ratio is the ratio of the Seeds per PDV reward between Deposited Pinto and the Deposited LP token with the most Seeds (which is determined by the LP token with the highest Gauge Points per PDV — see [Gauge System](../advanced/gauge-system.md#crop-ratio)).

In order to adjust the Crop Ratio, in practice the protocol adjusts a scalar (the Crop Scalar, $$L$$) between 0 and 1, where 0 results in the minimum Crop Ratio ($$Y$$) and 1 results in the maximum Crop Ratio ($$Z$$). Therefore, the peg maintenance mechanism can adjust the Crop Ratio independently of the minimum and maximum values (which are currently set to 50% and 100%, respectively).

$$
CropRatio = Y + L(Z - Y)
$$

Note that in any Season where it is [Raining](flood.md), the Crop Scalar becomes 0 and the Crop Ratio is independently set to 33.33%.&#x20;

At the beginning of each [Season](../farm/sun.md), the protocol changes the Crop Scalar depending on its position ([price](overview.md#decentralized-price-oracle), [debt level](overview.md#debt-level) and [liquidity level](overview.md#liquidity-level)) with respect to its [ideal equilibrium](overview.md#ideal-equilibrium).

Considering the current state and the liquidity level, the protocol adjusts the Crop Scalar to move toward the optimal state:

### Excessively Low L2SR <a href="#excessively-low-l2sr" id="excessively-low-l2sr"></a>

<figure><img src="../.gitbook/assets/CleanShot 2024-12-21 at 13.28.56@2x.png" alt=""><figcaption></figcaption></figure>

No matter the L2SR, when P > Q (where Q = $1.05), the protocol should maximally incentivize Converting to LP Deposits by aggressively decreasing the Crop Ratio. By decreasing the Crop Scalar by 0.5 each Season, the Crop Ratio returns to the minimum value within 2 Seasons.

When L2SR is excessively low, in all cases, the protocol should be similarly aggressive in incentivizing Conversions to LP Deposits by quickly reaching the minimum Crop Ratio.

### Reasonably Low L2SR <a href="#reasonably-low-l2sr" id="reasonably-low-l2sr"></a>

<figure><img src="../.gitbook/assets/CleanShot 2024-12-21 at 13.32.46@2x.png" alt=""><figcaption></figcaption></figure>

When the L2SR is reasonably low and Pod Rate is low, the protocol should be similarly aggressive in reaching the minimum Crop Ratio given that, at the margin, the protocol would rather take on debt than lose liquidity. When the L2SR is reasonably low and Pod Rate is high, the protocol should gradually increase the Crop Ratio when P > 1 (to incentivize Conversions above peg) and gradually decrease it when P < 1 (to incentivize Conversions below peg). By changing the scalar by 0.01 each Season, the Crop Ratio can change from the maximum to the minimum value (or vice versa) within 100 Seasons.

### Reasonably High L2SR <a href="#reasonably-high-l2sr" id="reasonably-high-l2sr"></a>

<figure><img src="../.gitbook/assets/CleanShot 2024-12-21 at 13.30.57@2x.png" alt=""><figcaption></figcaption></figure>

When L2SR is reasonably high and P < 1, the protocol should similarly gradually increase the Crop Ratio to incentivize Converting from LP Deposits to Pinto Deposits, and vice versa when P > 1.

### Excessively High L2SR <a href="#excessively-high-l2sr" id="excessively-high-l2sr"></a>

<figure><img src="../.gitbook/assets/CleanShot 2024-12-21 at 13.34.00@2x.png" alt=""><figcaption></figcaption></figure>

When L2SR is excessively high, the protocol should be more willing to accept a loss of liquidity rather than an increase in debt level at the margin. Therefore, it should adjust the Crop Scalar just as it does when L2SR is reasonably high, except it can be slightly more aggressive when P < 1 and the Pod Rate is high. By increasing the Crop Scalar by 0.02, the Crop Ratio can change from the minimum to the maximum value within 50 Seasons.

See [Cases](../advanced/cases.md) to see all the cases in which the Crop Scalar changes.
