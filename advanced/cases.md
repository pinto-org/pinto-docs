# Cases

The Case system is how Pinto evaluates its position and current state with respect to ideal equilibrium. It measures 4 axes:

1. Price, which is considered either:
   1. P > Q (time and liquidity weighted average price > $1.05);
   2. P > 1 (TWA∆P > 0); or
   3. P < 1 (TWA∆P ≤ 0);
2. [Debt level](../peg-maintenance/overview.md#debt-level) (_i.e._, Pod Rate), which is considered either:
   1. Excessively Low (Pod Rate < 3%);
   2. Reasonably Low (3% ≤ Pod Rate < 15%);
   3. Reasonably High (15% < Pod Rate ≤ 25%); or
   4. Excessively High (Pod Rate > 25%);
3. [Changing demand for Soil](../peg-maintenance/temperature.md#demand-for-soil), which is considered either:
   1. Increasing;
   2. Steady; or
   3. Decreasing; and
4. [Liquidity level](../peg-maintenance/overview.md#liquidity-level) (_i.e._, L2SR), which is considered either:
   1. Excessively Low (L2SR < 12%);
   2. Reasonably Low (12% ≤ L2SR < 40%);
   3. Reasonably High (40% < L2SR ≤ 80%); or
   4. Excessively High (L2SR > 80%).

As a result, there are 144 cases (3 × 4 × 3 × 4 = 144) in which the protocol measures itself and adjusts various parameters. Currently, only the [Maximum Temperature](../peg-maintenance/temperature.md) and the [Crop Scalar](../peg-maintenance/crop-ratio.md) are adjusted in each case. The Maximum Temperature has a minimum value of 1% and the Crop Scalar ranges from 0 to 1.

The following 144 cases are how the Maximum Temperature (in orange) and Crop Scalar (in green) are adjusted in each case:

<figure><img src="../.gitbook/assets/CleanShot 2025-01-02 at 21.22.12@2x.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/CleanShot 2025-01-02 at 21.22.32@2x.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/CleanShot 2025-01-02 at 21.22.55@2x.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/CleanShot 2025-01-02 at 21.23.07@2x.png" alt=""><figcaption></figcaption></figure>

\*When P > 1 (or P > Q) and the Pod Rate is Excessively Low, it [Rains](../peg-maintenance/flood.md). When it Rains, the Crop Scalar becomes 0 and the Crop Ratio is independently set to 33.33%. As a result, the Crop Scalar adjustments in these cases are not applicable.
