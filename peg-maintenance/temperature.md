# Temperature

Pinto relies on a decentralized set of creditors to maintain a minimally volatile price. Anytime the protocol is willing to issue debt, it issues [Soil](../farm/field.md#soil). Soil represents the number of Pinto that the protocol is currently willing to borrow. Loans to the protocol are issued with a fixed interest rate, known as Temperature. If the Temperature is 500%, 1 Pinto can be Sown in exchange for 6 Pods. Once those Pods become Harvestable, they can be Harvested in exchange for 6 Pinto.

At the beginning of each [Season](../farm/sun.md), the protocol changes the Maximum Temperature depending on its position ([price](overview.md#decentralized-price-oracle) and [debt level](overview.md#debt-level)) and current state ([direction](temperature.md#direction) and [acceleration](temperature.md#acceleration)) with respect to its [ideal equilibrium](overview.md#ideal-equilibrium).

The Temperature increases during the [Morning](temperature.md#morning) (first 10 minutes) of each Season according to a Dutch auction.

### **Direction** <a href="#direction" id="direction"></a>

The current state of Pinto is in part determined by the direction of change with respect to ideal equilibrium.

The direction of change of the protocol with respect to ideal equilibrium is considered either toward or away from ideal equilibrium, based on the current debt level and price.

When P > 1 (more specifically, when TWA∆P > 0), debt is paid back. Therefore, if there is more debt than optimal, the protocol is moving toward the ideal equilibrium. If there is less debt than optimal, the protocol is moving away from the ideal equilibrium.≈

When P < 1, debt can only increase or remain constant. Therefore, if there is more debt than optimal, the protocol is moving away from ideal equilibrium. If there is less debt than optimal, the protocol is moving toward ideal equilibrium.

<figure><img src="../.gitbook/assets/CleanShot 2024-12-21 at 12.46.57@2x.png" alt=""><figcaption></figcaption></figure>

### **Demand for Soil** <a href="#demand-for-soil" id="demand-for-soil"></a>

Demand for Soil is a factor in the acceleration of Pinto with respect to ideal equilibrium, which affects Maximum Temperature changes. Demand for Soil is considered decreasing, steady or increasing.

* The number of Sown Pinto each Season (​$$u_t$$) indicated demand for Soil over the course of that Season.
* The rate of change in the number of Sown Pinto each Season (Delta Demand) is calculated as the number of Sown Pinto in the previous Season ($$u_{t−1}$$​) divided by the number of Sown Pinto two Seasons ago ($$u_{t-2}$$​).

Based on this ratio of the number of Sown Pinto over the prior two Seasons, or Delta Demand:

* If Delta Demand < 95%, demand for Soil is decreasing.
* If 95% ≤ Delta Demand < 105%, demand for Soil is steady.
* If 105% ≤ Delta Demand, demand for Soil is increasing.

However, when there is between 0 and 1 Soil remaining at the end of any Season, the Delta Demand ratio is not used. Instead, the protocol checks the following conditions to determine the current demand for Soil:

* After a Season in which there was >1 Soil remaining, if there is at most 1 Soil remaining at the end of the latest Season, demand for Soil is increasing.
* When there is at most 1 Soil remaining in consecutive Seasons, the difference in time it takes for all but 1 Soil to be Sown over the previous two Seasons (where $$s_{t-2}$$ and  are the times in which all but Soil was Sown in Seasons $$t-2$$ and $$t-1$$, respectively) can provide a more accurate measurement:
  * If all but 1 Soil was Sown in the first 20 minutes of the previous Season (_i.e._, $$s_{t-1} < 20$$ minutes), demand for Soil is increasing.
  * If all but 1 Soil was not Sown in the first 20 minutes of the previous Season, the protocol compares $$s_{t-2}$$ and $$s_{t-1}$$.
    * If it took more than 5 minutes longer for all but 1 Soil to be Sown in Season $$t-1$$ than Season $$t-2$$ (_i.e._,  minutes), demand for Soil is decreasing.
    * If it took more than 5 minutes longer for all but 1 Soil to be Sown in Season $$t-2$$ than Season $$t-1$$ (_i.e._, $$s_{t-2} - s_{t-1} > 5$$ minutes), demand for Soil is increasing.
    * Otherwise, demand for Soil is steady.

### **Acceleration** <a href="#acceleration" id="acceleration"></a>

The current state of the protocol with respect to ideal equilibrium is in part determined by the acceleration of change.

The acceleration of the protocol affects the magnitude of Maximum Temperature changes and is considered decelerating, steady or accelerating based on price and the demand for Soil.

<figure><img src="../.gitbook/assets/CleanShot 2024-11-24 at 12.09.59@2x.png" alt=""><figcaption></figcaption></figure>

### **Current and Optimal State** <a href="#current-and-optimal-state" id="current-and-optimal-state"></a>

Based on a combination of the protocol's direction and acceleration, the protocol has six potential current states:

* Accelerating away from ideal equilibrium;
* Accelerating toward ideal equilibrium;
* Steady away from ideal equilibrium;
* Steady toward ideal equilibrium;
* Decelerating away from ideal equilibrium; and
* Decelerating toward ideal equilibrium.

The protocol's optimal state is that which moves it toward ideal equilibrium in the healthiest fashion, given the current position.

When the debt level is excessively high or low, an optimal state is accelerating toward ideal equilibrium. When the debt level is reasonably high or low, an optimal state is either steady or decelerating toward ideal equilibrium.

Considering the current state and the debt level, the protocol adjusts the Maximum Temperature to move toward the optimal state:

<figure><img src="../.gitbook/assets/CleanShot 2024-12-21 at 13.27.05@2x.png" alt=""><figcaption></figcaption></figure>

See [Cases](../advanced/cases.md) to see all the cases in which the Maximum Temperature changes.

### Morning <a href="#morning" id="morning"></a>

During the Morning of each Season (the first 10 minutes), the Temperature increases logarithmically from 1% of the Maximum Temperature in the block of a successful gm function call up to the Maximum Temperature over the course of 10 minutes. During times of short-term excess demand for Soil, the Morning results in the protocol paying significantly less to attract creditors.
