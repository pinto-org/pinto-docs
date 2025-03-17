# Audits

Pinto is a fork of [Beanstalk](https://bean.money/), which has been heavily audited. See here for audit reports of Beanstalk:

{% embed url="https://docs.bean.money/almanac/protocol/audits" %}

The following is a non-exhaustive list of changes made in Pinto since the latest version of Beanstalk (which have not been audited):

### At Deployment (November 19, 2024)

* Removed the Barn, Fertilizer, Unripe assets and various other deprecated code.
* Updated various constants to reflect the new whitelists, new token addresses, the deployment on Base, etc.
* Changed the minimum Bean reserves in a Well required to calculate the PDV of a LP token from 1000 to 10.
* Increased `L2_BLOCK_TIME` in LibDibbler.sol to 2 seconds.
* Added Shipment implementation to send Pinto to a Wallet or Farm Balance.
* Updated the Shipment Routes to reflect the Pinto distribution described [here](../farm/sun.md#shipments).
* Updated all instances of `LibArbitrum.blockNumber()` to `block.number`.
* Changed the 1% of supply minting cap per Well to max(200k Pinto, 2% of supply).
* Added a system level minting cap of max(800k Pinto, 4% of supply).
* Update the Gauge System's Stalk issuance mechanism to update the amount of Grown Stalk issued per Season only once the system's average Grown Stalk per PDV / Target Seasons to Catch Up exceeds the initialized average Grown Stalk per PDV per Season.
* Update the Gauge System's Stalk issuance mechanism such that there is a minimum Grown Stalk issued Per PDV.
* Update the default Gauge Point function to not change Gauge Points when the current % of Deposited LP PDV is within 10% of optimal.

### In PI-0: Update Parameters (November 19, 2024)

{% embed url="https://github.com/pinto-org/protocol/pull/1" %}

* Updated the Wells on the Minting Whitelist to use a new Multi Flow with more forgiving LP token supply and exchange rate cap parameters of 25% per block.
* Updated the Metadata Facet to return the correct metadata.

### In PI-1: Convert Newly Earned Pinto and Misc. Bug Fixes (November 26, 2024)

{% embed url="https://github.com/pinto-org/protocol/pull/2" %}

* Updated `plant` in order to issue Grown Stalk equal to the Seeds per PDV rewarded to Pinto in the previous Season, plus an additional 1 micro Seed, allowing newly Claimed Earned Pinto Deposited to be Converted immediately.
* Updated Pinto ↔ LP Converts to issue Grown Stalk such that the resulting Deposit is never Germinating.
* Introduced a minimum Crop Ratio during Rain and set it to 33.33%.
* Added the `initialSoil` view function, which returns the Soil supply at the beginning of the Season before its scaled by the Morning Auction.
* Updated events to emit correct values and upgrade various functions to return additional values for proper data processing by the UI and middleware.

### In PI-2: Remove Anti Lambda to Lambda Convert (November 27, 2024)

{% embed url="https://github.com/pinto-org/protocol/pull/3" %}

* Removed the Anti Lambda to Lambda (AL2L) Convert functionality from the Silo to prevent users from removing each other's Rain Stalk.

### In PI-3: Bug Fixes and Parameter Changes (December 4, 2024)

{% embed url="https://github.com/pinto-org/protocol/pull/4" %}

* Updated the Silo such that Farmers cannot lose Rain Stalk on transfer or Convert.
* Re-added Anti Lambda to Lambda (AL2L) Converts.
* Updated the gm reward to properly issue Pinto when the gm function is called 239 to 240 seconds late.
* Updated Soil issuance above peg to properly account for Pods that became Harvestable due to Flood.
* Adjusted the Soil issuance above peg multiplier on Pods that became Harvestable from 1.5x to 1.2x when the Pod Rate is Excessively Low.
* Extended the duration of the Morning from 5 to 10 minutes.
* Changed the minimum Temperature at the beginning of the Morning from 1% to 1% of the Maximum Temperature.
* Reduced all cases of the Maximum Temperature increasing by 3% to 2%.
* Lowered the Excessively Low Pod Rate threshold from 5% to 3%.

### PI-4: Demand for Soil Adjustments (December 8, 2024)

{% embed url="https://github.com/pinto-org/protocol/pull/5" %}

* Extended the period at the beginning of the Season during which demand for Soil is considered increasing if all but 1 Soil is Sown into, from 10 to 20 minutes.
* Extended the range during which demand for Soil is considered steady if all but 1 Soil is Sown into within the same time frame across the previous 2 Seasons, from 1 to 5 minutes.

### PI-5: **Soil Issuance and Parameter Changes** (January 2, 2025)

{% embed url="https://github.com/pinto-org/protocol/pull/7" %}

* Upgraded Maximum Temperature from 0 to 6 decimal precision.
* Scaled Soil issuance below peg by 1 - L2SR and set a minimum Soil issued when TWAΔP < 0 to 1% of | TWAΔP |.
* Changed the scalar on Pods that became Harvestable at the beginning of the Season for Soil issuance above peg by:
  * 0.5 to 0.25 when the Pod Rate is Excessively High;
  * 1 to 0.5 when the Pod Rate is Reasonably High; and
  * 1.5 to 1.2 when the Pod Rate is Excessively Low.
* Changed Soil issuance when the inter-block MEV manipulation resistant instantaneous ∆P (INST∆P) > 0 and TWA∆P < 0 to be 1% of | TWA∆P | scaled by:
  * 0.25 when the Pod rate is Excessively Low;
  * 0.5 when the Pod Rate is Reasonably High;
  * 1 when the Pod Rate is Reasonably Low; and
  * 1.2 when the Pod Rate is Excessively Low.
* Lowered the Maximum Temperature adjustments in several instances when P < 1 (detailed in the PR comment).
* Increase the magnitude of the Crop Scalar adjustments when P > 1, the Pod Rate is high and the L2SR is Reasonably Low (detailed in the PR comment).
* Introduced new events related to Flood and the cases.
