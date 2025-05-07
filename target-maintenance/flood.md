# Flood

The Pinto protocol sells newly minted Pinto on the open market during long run increases in demand for Pinto when [increasing the Pinto supply](overview.md#bean-supply), [lowering the Maximum Temperature](temperature.md) and [lowering the Crop Ratio](crop-ratio.md) have not crossed the Pinto price over its value target.

At the beginning of a [Season](../farm/sun.md) where TWA∆P > 0 and [Pod Rate](overview.md#debt-level) < 3% (Excessively Low), it is Raining. At the beginning of a Season in which it Rains, the [Crop Ratio](crop-ratio.md) is set to 33.33%. If at the beginning of a Season it continues to Rain and the cumulative ∆P > 0, it Floods.

At the beginning of a Season during a Flood, the protocol mints additional Pinto and sells them directly in pools on the [Flood Whitelist](flood.md#current-flood-whitelist) with the highest Pinto price at the end of the previous Season until the liquidity weighted price is $1.&#x20;

At the beginning of each Season in which it Floods, up to 0.1% of the Pinto supply worth of Pods that grew from Pinto Sown before it began to Rain become Harvestable.

In total, during a gm call in which it Floods, the following Pinto are minted:

1. Cumulative ∆P at the end of the previous Season, which are minted and sold directly in pools on the Flood Whitelist;
2. Up to 0.1% of the Pinto supply worth of Pods;
3. TWA∆P per the [target maintenance mechanism](overview.md) (as with non-Flood gm calls); and
4. The gm reward (as with non-Flood gm calls).

Proceeds from the sale are distributed to Stalkholders at the beginning of Season in proportion to their Stalk holdings when it began to Rain (i.e., **Stalk minted after it began to Rain does not contribute towards ownership of the Flood proceeds**).&#x20;

#### **Current Flood Whitelist**

<table><thead><tr><th width="269">Name</th><th>Base Address</th></tr></thead><tbody><tr><td><a href="https://pinto.exchange/#/wells/8453/0x3e11001cfbb6de5737327c59e10afab47b82b5d3">PINTO:WETH Well</a></td><td><a href="https://basescan.org/address/0x3e11001CfbB6dE5737327c59E10afAB47B82B5d3">0x3e11001CfbB6dE5737327c59E10afAB47B82B5d3</a></td></tr><tr><td><a href="https://pinto.exchange/#/wells/8453/0x3e111115a82df6190e36adf0d552880663a4dbf1">PINTO:cbETH Well</a></td><td><a href="https://basescan.org/address/0x3e111115A82dF6190e36ADf0d552880663A4dBF1">0x3e111115A82dF6190e36ADf0d552880663A4dBF1</a></td></tr><tr><td><a href="https://pinto.exchange/#/wells/8453/0x3e11226fe3d85142b734abce6e58918d5828d1b4">PINTO:cbBTC Well</a></td><td><a href="https://basescan.org/address/0x3e11226fe3d85142B734ABCe6e58918d5828d1b4">0x3e11226fe3d85142B734ABCe6e58918d5828d1b4</a></td></tr><tr><td><a href="https://pinto.exchange/#/wells/8453/0x3e1133ac082716ddc3114bbefeed8b1731ea9cb1">PINTO:USDC Well</a></td><td><a href="https://basescan.org/address/0x3e1133aC082716DDC3114bbEFEeD8B1731eA9cb1">0x3e1133aC082716DDC3114bbEFEeD8B1731eA9cb1</a></td></tr><tr><td><a href="https://pinto.exchange/#/wells/8453/0x3e11444c7650234c748d743d8d374fce2ee5e6c9">PINTO:WSOL Well</a></td><td><a href="https://basescan.org/address/0x3e11444c7650234c748D743D8d374fcE2eE5E6C9">0x3e11444c7650234c748D743D8d374fcE2eE5E6C9</a></td></tr></tbody></table>
