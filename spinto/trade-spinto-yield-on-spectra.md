---
description: >-
  This guide will walk you through the steps to speculate on sPinto yield in
  Spectra Finance.
---

# Trade sPinto yield on Spectra

Spectra Finance is a decentralized finance (DeFi) protocol that enables users to tokenize and trade future yield, offering options such as fixing interest rates, yield trading, and earning additional returns on liquidity.&#x20;

In this guide we'll walk through:

* How you can get fixed yield for sPinto over a period of time by buying the sPinto PT (principal token).
* How you can get leveraged sPinto yield exposure by buying the sPinto YT  (yield token).
* How to provide liquidity on the sPinto Spectra pool and get exposure to sPinto yield, swap fees and additional incentives.

Note that this guide assumes that you already have sPinto in your wallet. For details on how to get sPinto, see here: [wrap-unwrap-spinto.md](wrap-unwrap-spinto.md "mention")

For more in-depth explanations about the underlying mechanisms at play, visit the Spectra docs at [https://docs.spectra.finance/](https://docs.spectra.finance/)

### Getting Fixed Yield on your sPinto

When "fixing" sPinto yield, you are forfeiting your rights to sPinto yield for a period of time in exchange for a fixed return. This enables you to "lock-in" a guaranteed yield on your sPinto regardless of the underlying Silo yield. Note that you are still exposed to the price of Pinto when doing that as the sPinto price is denominated in Pinto.&#x20;

Here is how to achieve this:

* Go to the fixed rate page on the spectra app [https://app.spectra.finance/fixed-rate](https://app.spectra.finance/fixed-rate)
* Choose Base as the chain.
* Choose "sPinto" as the pool and click on it.&#x20;

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

* Choose an input token to use. In this case, you can fix yield using plain Pinto or sPinto directly.
*   In the output section, you should see:&#x20;

    * How much of the PT (Principal token) you are getting. PT tokens:
      * Represent the initial deposit, also known as the principal.
      * Redeemable 1:1 for underlying at maturity; trading at a discount until maturity, provided no negative yield.
      * Adhere to the ERC-20 token standard.
    * How much yield you''ll get at maturity.
    * The implied APY you are getting for that period of time.&#x20;

    <figure><img src="../.gitbook/assets/image (18).png" alt="" width="375"><figcaption></figcaption></figure>
* Click on "Fix Rate" and sign the transaction in your wallet.
* You have now successfully "fixed" sPinto yield for a period of time. You will be able to redeem your PT for Pinto at maturity.
* If you wish to redeem earlier, you''ll have to sell your PT for regular sPinto in the liquidity pool. To do so, you just need to click on "Exit Position" on the same page. Note that you may incur slippage from trading when performing that action.

### Get leveraged sPinto yield exposure

When getting leveraged sPinto yield exposure you are buying the rights to the yield of a certain amount of sPinto for a period of time. If the actual yield ends up being higher than the price you paid to get it, you will make a profit. However if the yield turns out to be lower over that period of time, you will incur a loss. This strategy has more inherent risk due to the volatile nature of pinto silo yield but can produce outsized returns in the case of a pinto growth cycle over that period of time.&#x20;

Here is how to achieve this:

* Go to the yield leverage page on the spectra app [https://app.spectra.finance/trade-yield](https://app.spectra.finance/trade-yield).
* Choose base as the chain.
* Choose "sPinto" as the pool and click on it.&#x20;

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

* Choose an input token to use. In this case, you can leverage yield using plain Pinto or sPinto directly.
*   In the output section, you should see:&#x20;

    * How much of the sPinto  YT (Yield token)  you are getting. YT tokens:
      * Represent the right to future yield
      * Accrue yield for its holder
      * The value of the YT itself heads toward 0 until the expiry date
      * Adheres to ERC-20 token standard; freely transferable
    * How much leveraged yield exposure you'll get when buying the sPinto YT token.
    * The implied APY at which you are buying the YT. A lower value means the future yield is being bought for cheap.

    <figure><img src="../.gitbook/assets/image (20).png" alt="" width="375"><figcaption></figcaption></figure>
* Click on "Get Yield Leverage" and sign the transaction in your wallet.
* You have now successfully earned rights to leveraged sPinto yield for a period of time. You will be able to claim your yield as it comes in your portfolio page: [https://app.spectra.finance/portfolio](https://app.spectra.finance/portfolio).
* If you wish to exit your position earlier, you can do that in the "Exit Position" tab on the same page you bought the YT in.

### Provide Liquidity on the sPinto Spectra Pool

sPinto PTs and YT are traded via a Curve stableswap liquidity pool with the ratios in the pool determining the price of the tokens and thus, the underlying yield. To facilitate trading, you can provide liquidity on the sPinto spectra pool and earn swap fees and sPinto yield exposure. Pools are comprised of sPinto and the sPinto PT token. Due to the nature of the protocol, impermanent loss when providing liquidity on spectra is negligible. Read more on why this is the case here: [https://docs.spectra.finance/the-basics/faq](https://docs.spectra.finance/the-basics/faq)

* Go to the pool page on the spectra app [https://app.spectra.finance/pools](https://app.spectra.finance/pools)
* Choose base as the chain.
* Choose "sPinto" as the pool and click on it.&#x20;

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

* Choose an input token to use. In this case, you can LP using plain Pinto or sPinto directly.
*   In the output section, you should see:&#x20;

    * How much of the LP token you are getting. LP tokens:
      * Represent the number of liquidity provider (LP) tokens you receive in exchange for your deposit. These tokens are proof of your share in the pool and can be used to redeem your portion of the pool's assets, plus any accrued swap fees.
    * How much of the YT token you are getting.
      * Yield Tokens result from the yield tokenization process; however, they are not part of the pool composition. LP token holders remain entitled to fees from Yield Token (YT) swaps as they are driven by flash swaps utilizing the pool. Read more about output composition when providing liquidity in the Spectra FAQs here: [https://docs.spectra.finance/the-basics/faq#pool-creation](https://docs.spectra.finance/the-basics/faq#pool-creation)
      * You can sell YTs (subject to slippage) or continue earning sPinto yield by holding them.
    * How much of the pool share you will own.
    * New implied APY as a result of adding liquidity.

    <figure><img src="../.gitbook/assets/image (22).png" alt="" width="375"><figcaption></figcaption></figure>
* Click on "Add Liquidity" and sign the transaction in your wallet.
* You have now successfully provided liquidity for the sPinto Spectra pool. You will be able to redeem your LP tokens for sPinto at any time. In the meantime, you will be earning yield from fees and sPinto YT if you keep it. Keep track of all of your positions at the portfolio tab here: [https://app.spectra.finance/portfolio](https://app.spectra.finance/portfolio)
* If you wish to remove liquidity earlier than maturity just go to the same page where you added the liquidity in the "Remove" tab and specify how much of the LP tokens you want to redeem.
