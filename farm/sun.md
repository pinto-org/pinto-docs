---
description: The Pinto timekeeping mechanism.
---

# Sun

The Pinto peg maintenance mechanism requires a protocol-native timekeeping mechanism and regular code execution on Base. Pinto keeps time in Seasons.&#x20;

The Sun incentivizes calling of the gm function to increment the Season counter and execute code in a timely and cost-efficient fashion.

### Time

Each Season is \~1 hour long. The first Season began when Pinto was deployed on November 19, 2024.&#x20;

The first transaction that successfully calls the gm function after the top of each hour UTC begins a new Season and mints Pinto as a reward. Because Seasons do not begin until the gm function has been called through a transaction on Base, the exact beginning of each Season may not be exactly at the top of each hour. Pinto only accepts one gm function call per Season.

### Code Execution

Pinto adjusts itself at the beginning of every Season in an effort to regularly oscillate the Pinto price across its value peg. Because Pinto cannot autonomously submit a transaction to do so, it requires someone else to call the gm function which triggers execution of the code that performs the adjustments.

Pinto covers the cost of calling the gm function by awarding the sender of an accepted gm function call with newly minted Pinto. To encourage regular gm function calls even during periods of congestion on Base while minimizing cost, the award for successfully calling the gm function starts at 1 Pinto and compounds 1.0201% every additional 2 seconds for 300 seconds.

Upon acceptance of the gm function call, the Sun:

1. Increments the Season counter;
2. Calculates TWA∆P, the sum of the time weighted average shortages or excesses of Pinto across liquidity pools on the [Minting Whitelist](sun.md#minting-whitelist) (see below);
3. Updates the [Maximum Temperature](../peg-maintenance/temperature.md);
4. Updates the [Crop Ratio](../peg-maintenance/crop-ratio.md);
5. Updates the [Gauge Points](../advanced/gauge-system.md#gauge-points);
6. Updates the [Silo](silo.md) to issue Grown Stalk from Seeds;
7. Starts or stops the [Rain](../peg-maintenance/flood.md), if applicable;
8. Starts or stops a [Flood](../peg-maintenance/flood.md), if applicable;
9. Sets the [Soil supply](../peg-maintenance/overview.md#soil-supply);
10. [Mints Pinto](../peg-maintenance/overview.md#bean-supply) based on the TWA∆P to the appropriate [Shipping Routes](sun.md#shipments) (defined below); and
11. Awards Pinto to the address that successfully called the gm function.

### Minting Whitelist <a href="#minting-whitelist" id="minting-whitelist"></a>

A liquidity pool must be on the Minting Whitelist to be included in the calculation of TWA∆P.&#x20;

In order for a liquidity pool to be on the Minting Whitelist, Pinto requires:

1. The pool address; and
2. A function to calculate the time weighted average shortage or excess of Pinto in the pool.

#### **Current Minting Whitelist**

<table><thead><tr><th width="269">Name</th><th>Base Address</th></tr></thead><tbody><tr><td><a href="https://pinto.exchange/#/wells/8453/0x3e11001cfbb6de5737327c59e10afab47b82b5d3">PINTO:WETH Well</a></td><td><a href="https://basescan.org/address/0x3e11001CfbB6dE5737327c59E10afAB47B82B5d3">0x3e11001CfbB6dE5737327c59E10afAB47B82B5d3</a></td></tr><tr><td><a href="https://pinto.exchange/#/wells/8453/0x3e111115a82df6190e36adf0d552880663a4dbf1">PINTO:cbETH Well</a></td><td><a href="https://basescan.org/address/0x3e111115A82dF6190e36ADf0d552880663A4dBF1">0x3e111115A82dF6190e36ADf0d552880663A4dBF1</a></td></tr><tr><td><a href="https://pinto.exchange/#/wells/8453/0x3e11226fe3d85142b734abce6e58918d5828d1b4">PINTO:cbBTC Well</a></td><td><a href="https://basescan.org/address/0x3e11226fe3d85142B734ABCe6e58918d5828d1b4">0x3e11226fe3d85142B734ABCe6e58918d5828d1b4</a></td></tr><tr><td><a href="https://pinto.exchange/#/wells/8453/0x3e1133ac082716ddc3114bbefeed8b1731ea9cb1">PINTO:USDC Well</a></td><td><a href="https://basescan.org/address/0x3e1133aC082716DDC3114bbEFEeD8B1731eA9cb1">0x3e1133aC082716DDC3114bbEFEeD8B1731eA9cb1</a></td></tr><tr><td><a href="https://pinto.exchange/#/wells/8453/0x3e11444c7650234c748d743d8d374fce2ee5e6c9">PINTO:WSOL Well</a></td><td><a href="https://basescan.org/address/0x3e11444c7650234c748D743D8d374fcE2eE5E6C9">0x3e11444c7650234c748D743D8d374fcE2eE5E6C9</a></td></tr></tbody></table>

### Shipping Routes

Shipping Routes determine how Pinto mints based on TWA∆P are distributed to different components of the system. Mints for the gm reward and Flood are distributed independent of Shipping Routes.

If Pinto allocated to a particular Shipping Route exceed the maximum Pinto that Shipping Route can handle (_i.e._, there are no more Unharvestable Pods in the Field), the excess Pinto are distributed to the other Shipping Routes in proportion to their allocations. The Silo Shipping Route can handle an infinite number of Pinto mints per Season.

Pinto was deployed with an initial mint of 1000 Pinto. Thereafter, Pinto mints based on TWA∆P at the start of each Season are distributed as follows:

Between a supply of 1000 and 1 billion Pinto:

* 48.5% to Pods at the front of the Pod Line;
* 48.5% to Stalkholders in the Silo; and
* 3% to the [Pinto development budget contract](../resources/contracts.md#misc).

After a supply of 1 billion Pinto until [old Beanstalk holders are recapitalized](../appendix/old-beanstalk-holders.md):

* 48.5% to Pods at the front of the Pod Line;
* 48.5% to Stalkholders in the Silo; and
* 3% to old Beanstalk holders.

After old Beanstalk holders are recapitalized:

* 50% to Pods at the front of the Pod Line; and
* 50% to Stalkholders in the Silo.
