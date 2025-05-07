# Cases

The Case system is how Pinto evaluates its position and current state with respect to ideal equilibrium. It measures 4 axes:

1. Price, which is considered either:
   1. P > $$P^{\text{upper}}$$ (time and liquidity weighted average price > $1.025);
   2. P > 1 (TWA∆P > 0); or
   3. P ≤ 1 (TWA∆P ≤ 0);
2. [Debt level](../target-maintenance/overview.md#debt-level) (_i.e._, Pod Rate), which is considered either:
   1. Excessively Low (Pod Rate < 3%);
   2. Reasonably Low (3% ≤ Pod Rate < 15%);
   3. Reasonably High (15% < Pod Rate ≤ 25%);
   4. Excessively High (15% < Pod Rate ≤ 100%); or
   5. Extremely High (Pod Rate > 100%).
3. [Changing demand for Soil](../target-maintenance/temperature.md#demand-for-soil), which is considered either:
   1. Increasing;
   2. Steady; or
   3. Decreasing; and
4. [Liquidity level](../target-maintenance/overview.md#liquidity-level) (_i.e._, Liquidity Rate), which is considered either:
   1. Excessively Low (Liquidity Rate < 12%);
   2. Reasonably Low (12% ≤ Liquidity Rate < 40%);
   3. Reasonably High (40% < Liquidity Rate ≤ 80%); or
   4. Excessively High (Liquidity Rate > 80%).

Currently, only the [Maximum Temperature](../target-maintenance/temperature.md) and the [Crop Scalar](../target-maintenance/crop-ratio.md) are adjusted in each case. The Maximum Temperature has a minimum value of 1% and the Crop Scalar ranges from 0 to 1.

The following cases are how the Maximum Temperature (in orange) and Crop Scalar (in green) are adjusted in each case:

<figure><img src="../.gitbook/assets/CleanShot 2025-05-06 at 19.28.53@2x.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/CleanShot 2025-05-06 at 19.29.24@2x.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/CleanShot 2025-05-06 at 19.29.32@2x.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/CleanShot 2025-05-06 at 19.29.41@2x.png" alt=""><figcaption></figcaption></figure>

\*When P > 1 and the Pod Rate is Excessively Low, it [Rains](../target-maintenance/flood.md). When it Rains, the Crop Scalar becomes 0 and the Crop Ratio is independently set to 33.33%. As a result, the Crop Scalar adjustments in these cases are not applicable.
