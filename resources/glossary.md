# Glossary

#### **Convert** <a href="#convert" id="convert"></a>

Changing one Deposited asset for another within the [Silo](../farm/silo.md). Read more [here](../peg-maintenance/convert.md).

#### Crop Ratio <a href="#crop-ratio" id="crop-ratio"></a>

Determines the relative benefits of holding Pinto exposure vs exposure to the LP token with the most Seeds in the Silo over time. More specifically, the ratio of [Seed](glossary.md#seeds) rewards between Pinto and the LP token with the highest [Gauge Points](glossary.md#gauge-points) per [PDV](glossary.md#pinto-denominated-value). Adjusted via the [Gauge System](glossary.md#seed-gauge-system). Read more [here](../peg-maintenance/crop-ratio.md).

#### **deltaP (**∆&#x50;**)** <a href="#deltap" id="deltap"></a>

The shortage or excess of Pinto in a liquidity pool that Pinto trades in. TWA∆P is the time-weighted version of ∆P.

#### Delta Demand <a href="#delta-demand" id="delta-demand"></a>

The ratio of the change in [Soil](glossary.md#soil) Sown into over the prior two [Seasons](glossary.md#season). Used to measure Demand for Soil.

#### **Deposit** <a href="#deposit" id="deposit"></a>

Assets on the [Deposit Whitelist](glossary.md#deposit-whitelist) can be Deposited in the [Silo](glossary.md#silo) at any time to earn [Stalk](glossary.md#stalk) and [Seeds](glossary.md#seeds). Read more [here](../farm/silo.md#deposit-whitelist).

#### **Deposit Whitelist** <a href="#deposit-whitelist" id="deposit-whitelist"></a>

The whitelist of ERC-20 tokens that can be Deposited in the [Silo](glossary.md#silo). Read more [here](../farm/silo.md#deposit-whitelist).

#### **Depot** <a href="#depot" id="depot"></a>

The component of the [Toolshed](glossary.md#toolshed) that facilitates interactions with other protocols in a single transaction. Read more [here](../farm/toolshed/depot.md).

#### **Earned Pinto** <a href="#earned-pinto" id="earned-pinto"></a>

Pinto that have been paid to a Stalkholder since the last Season they [Planted](glossary.md#plant) their [Plantable Seeds](glossary.md#plantable-seeds) (Claimed). Upon Plant, Earned Pinto are [Deposited](glossary.md#deposit).

#### **Earned Stalk** <a href="#earned-stalk" id="earned-stalk"></a>

[Stalk](glossary.md#stalk) earned from Earned Pinto. Earned Stalk automatically contribute to Stalk ownership and do not require any action to claim them.

#### **Farm** <a href="#farm" id="farm"></a>

The Pinto ecosystem. The Farm has four primary components: the [Sun](glossary.md#sun), [Silo](glossary.md#silo), [Field](glossary.md#field) and [Toolshed](glossary.md#toolshed). Read more [here](broken-reference).

#### **Farm Balance** <a href="#farm-assets" id="farm-assets"></a>

Balances stored in the Pinto protocol (but not Deposited, in Pod Orders, etc.). Farm Balances can be used in transactions on the [Farm](glossary.md#farm) and may be more gas efficient than [Wallet Balances](glossary.md#wallet-balance). Read more [here](../farm/toolshed/farm-balances.md).

#### **Farmers** <a href="#farmers" id="farmers"></a>

Users of Pinto.

#### **Field** <a href="#field" id="field"></a>

The Pinto credit facility. Read more [here](../farm/field.md).

#### **FIFO** <a href="#fifo" id="fifo"></a>

First in, first out. [Pods](glossary.md#pods) become [Harvestable](glossary.md#harvestable-pods) (redeemable for Pinto) on a FIFO basis. This means that Pods closer to the front of the [Pod Line](glossary.md#pod-line) become Harvestable before Pods farther back in the Pod Line.

#### **Flood** <a href="#flood" id="flood"></a>

If it is [Raining](glossary.md#rain) and the [Pod Rate](glossary.md#pod-rate) is less than 3% (Excessively Low), at gm there is a Flood. At the beginning of a Season where it Floods, additional Pinto are minted and sold directly into pools on the [Flood Whitelist](glossary.md#flood-whitelist). Read more [here](../peg-maintenance/flood.md).

#### Flood Whitelist

The whitelist of liquidity pools that the protocol evaluates whether to sell Pinto into or not during a [Flood](glossary.md#flood). Read more [here](../peg-maintenance/flood.md#current-flood-whitelist).

#### Gauge Points <a href="#gauge-points" id="gauge-points"></a>

Used by the [Gauge System](glossary.md#seed-gauge-system) to determine [Grown Stalk](glossary.md#grown-stalk) issuance across LP tokens on the [Deposit Whitelist](glossary.md#deposit-whitelist).

#### Germination <a href="#germination" id="germination"></a>

Germinating [Deposits](glossary.md#deposit) are Deposits that are less than 2 [gm](glossary.md#gm) calls old. Germinating Deposits can be [Withdrawn](glossary.md#withdraw) or transferred, but cannot be [Converted](glossary.md#convert). Germination exists to add flash loan and inter-block MEV manipulation resistance to the calculation of Deposited PDV. By preventing the accrual of [Earned Pinto](glossary.md#earned-beans) for 1 full [Season](glossary.md#season), the protocol further disincentivizes inorganic demand.

#### **gm** <a href="#gm" id="gm"></a>

The protocol accepts one gm function call every [Season](glossary.md#season). Upon the gm call, the protocol adjusts the Pinto supply and various incentives to facilitate low volatility. Read more [here](../farm/sun.md).

#### **Grown Stalk** <a href="#grown-stalk" id="grown-stalk"></a>

[Stalk](glossary.md#stalk) earned from [Seeds](glossary.md#seeds). Grown Stalk does not contribute to Stalk ownership until it is [Mown](glossary.md#mow) (Claimed). Mow can be called on its own, and it is also called at the beginning of any [Silo](glossary.md#silo) interaction ([Depositing](glossary.md#deposit), [Withdrawing](glossary.md#withdraw), [Converting](glossary.md#convert), etc.).

#### **Harvest** <a href="#harvest" id="harvest"></a>

Redeem Harvestable Pods for 1 Pinto each.

#### **Harvestable Pods** <a href="#harvestable-pods" id="harvestable-pods"></a>

[Pods](glossary.md#pods) that are redeemable for 1 Pinto each. Harvestable Pods must be Harvested in order to use them.

#### Liquidity to Supply Ratio (L2SR) <a href="#liquidity-to-supply-ratio-l2sr" id="liquidity-to-supply-ratio-l2sr"></a>

Represents the the Pinto liquidity level relative to the Pinto supply. The L2SR is a useful indicator of the protocol's health. Read more [here](../peg-maintenance/overview.md#liquidity-level).

#### Liquidity Weight <a href="#liquidity-weight" id="liquidity-weight"></a>

The portion of liquidity in a whitelisted liquidity pool that counts towards the [Liquidity to Supply Ratio](glossary.md#liquidity-to-supply-ratio-l2sr) calculation.

#### Maximum Temperature <a href="#maximum-temperature" id="maximum-temperature"></a>

The maximum [Temperature](glossary.md#temperature) the protocol is willing to offer during a [Season](glossary.md#season). Read more [here](../peg-maintenance/temperature.md).

#### Minting Whitelist <a href="#minting-whitelist" id="minting-whitelist"></a>

The whitelist of liquidity pools whose TWA∆P's are summated to calculate a total TWA∆P. Read more [here](../farm/sun.md#minting-whitelist).

#### Morning <a href="#morning" id="morning"></a>

The first 10 minutes of each [Season](glossary.md#season) where the [Temperature](glossary.md#temperature) approaches the [Maximum Temperature](glossary.md#maximum-temperature).

#### **Mow** <a href="#mow" id="mow"></a>

Mowing (Claiming) [Grown Stalk](glossary.md#grown-stalk) adds it to your [Stalk](glossary.md#stalk) balance. Called upon any interaction with the [Silo](glossary.md#silo).

#### **Pinto Denominated Value (PDV)** <a href="#pinto-denominated-value-pdv" id="pinto-denominated-value-pdv"></a>

The value of an asset denominated in Pinto. Used to calculate how many [Stalk](glossary.md#stalk) and [Seeds](glossary.md#seeds) are rewarded to Depositors of an asset in the [Silo](glossary.md#silo). Abbreviated as PDV.

#### **Pinto** <a href="#pinto" id="pinto"></a>

The low volatility money protocol that issues Pinto. Also used to refer to the ERC-20 token.

#### **Pinto Contract Multisig (PCM)** <a href="#pcm" id="pcm"></a>

The multisig that custodies ownership of the Pinto contract. Abbreviated as PCM. Read more [here](../appendix/upgradability.md).

#### **Pipeline** <a href="#pipeline" id="pipeline"></a>

A sandbox contract that can execute an arbitrary number of actions within the EVM from an EOA in a single transaction. Forked from [evmpipeline.org](https://evmpipeline.org).

#### **Plant** <a href="#plant" id="plant"></a>

Planting (Claiming) adds [Plantable Seeds](glossary.md#plantable-seeds) to your total [Seed](glossary.md#seeds) balance.

#### **Plantable Seeds** <a href="#plantable-seeds" id="plantable-seeds"></a>

[Seeds](glossary.md#seeds) earned in conjunction with [Earned Pinto](glossary.md#earned-beans). Plantable Seeds must be [Planted](glossary.md#plant) in order to grow [Stalk](glossary.md#stalk).

#### **Plot** <a href="#plot" id="plot"></a>

[Pods](glossary.md#pods) that grow from Pinto that were [Sown](glossary.md#sow) in the same transaction form a Plot.

#### **Pod Line** <a href="#pod-line" id="pod-line"></a>

The order in which [Pods](glossary.md#pods) will become [Harvestable](glossary.md#harvest) based on the FIFO Harvest schedule.

#### **Pod Listing** <a href="#pod-listing" id="pod-listing"></a>

An offer to sell [Pods](glossary.md#pods) on the [Pod Market](glossary.md#pod-market). Read more [here](../farm/toolshed/pod-market.md#pod-listings).

#### **Pod Market** <a href="#pod-market" id="pod-market"></a>

The decentralized, trustless market that [Pods](glossary.md#pods) can be bought and sold on. Read more [here](../farm/toolshed/pod-market.md).

#### **Pod Order** <a href="#pod-order" id="pod-order"></a>

An order to buy [Pods](glossary.md#pods) on the [Pod Market](../farm/toolshed/pod-market.md). Read more [here](../farm/toolshed/pod-market.md#pod-orders).

#### **Pod Rate** <a href="#pod-rate" id="pod-rate"></a>

The protocol debt level (Pod supply) relative to the Pinto supply. The Pod Rate is often used as a proxy for the protocol's health. Read more [here](../peg-maintenance/overview.md#debt-level).

#### **Pods** <a href="#pods" id="pods"></a>

The Pinto-native debt asset, redeemable for 1 Pinto each once they become [Harvestable](glossary.md#harvest). Read more [here](../farm/field.md#pods).

#### Rain

At the beginning of a [Season](glossary.md#season) where TWA∆P > 0 and [Pod Rate](glossary.md#pod-rate) < 3% (Excessively Low), it is Raining.

#### **Season** <a href="#season" id="season"></a>

Seasons are Pinto-native time. Every Season is approximately 1 hour. Each Season begins when the [gm](glossary.md#gm) function is successfully called on Base. Read more [here](../farm/sun.md).

#### Gauge System <a href="#seed-gauge-system" id="seed-gauge-system"></a>

The component of the [Silo](glossary.md#silo) responsible for dynamically adjusting the [Seed](glossary.md#seeds) rewards for different assets whitelisted in the Silo. Read more [here](../advanced/gauge-system.md).

#### **Seeds** <a href="#seeds" id="seeds"></a>

An illiquid token that yields 1/10000 [Grown Stalk](glossary.md#grown-stalk) every [Season](glossary.md#season).

#### **Silo** <a href="#silo" id="silo"></a>

The Pinto Deposit facility. Read more [here](../farm/silo.md).

#### **Soil** <a href="#soil" id="soil"></a>

The current number of Pinto that can be Sown in exchange for [Pods](glossary.md#pods). Read more [here](../farm/field.md#soil).

#### **Sow** <a href="#sow" id="sow"></a>

Lending to the protocol. Used in the context of Sowing Pinto, or lending Pinto to the protocol when there is [Soil](glossary.md#soil).

#### **Stalk** <a href="#stalk" id="stalk"></a>

An illiquid token that entitles the holder to a pro rata share of future Pinto mints. Read more [here](../farm/silo.md).

#### **Stalkholders** <a href="#stalkholders" id="stalkholders"></a>

Holders of the Stalk token. Stalkholders earn Pinto seigniorage.

#### Sun <a href="#sun" id="sun"></a>

The component of the [Farm](glossary.md#farm) that keeps time in [Seasons](glossary.md#season) and incentivizes cost-efficient and timely calling of the [gm](glossary.md#gm) function. Read more [here](../farm/sun.md).

#### Target Seasons to Catch Up <a href="#target-seasons-to-catch-up" id="target-seasons-to-catch-up"></a>

Determines the target number of [Seasons](glossary.md#season) for a new [Deposit](glossary.md#deposit) with an average number of [Seeds](glossary.md#seeds) to catch up to the average [Grown Stalk](glossary.md#grown-stalk) per [PDV](glossary.md#bean-denominated-value) of existing Deposits at the time of Deposit. Read more [here](../advanced/gauge-system.md).

#### **Temperature** <a href="#temperature" id="temperature"></a>

The interest rate for Sowing Pinto. Read more [here](../farm/field.md#temperature).

#### Toolshed <a href="#toolshed" id="toolshed"></a>

The Toolshed offers a suite of tools for efficient use of Pinto and other Base-native protocols. Read more [here](../farm/toolshed/).

#### **Wallet Balance** <a href="#wallet-balance" id="wallet-balance"></a>

Balances in Farmers' wallets. Can be used in the same transaction as [Farm Balances](glossary.md#farm-assets).

#### **Withdraw** <a href="#withdraw" id="withdraw"></a>

Deposited assets can be Withdrawn from the [Silo](glossary.md#silo) at any time. The number of [Stalk](glossary.md#stalk), [Seeds](glossary.md#seeds), and Stalk from Seeds rewarded for a Deposited asset must be forfeited upon its Withdrawal from the Silo. Read more [here](../farm/silo.md#withdraw).
