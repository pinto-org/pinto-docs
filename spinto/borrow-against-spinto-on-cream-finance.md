---
description: >-
  This guide will walk you through the steps to borrow and leverage against your
  sPinto on Cream Finance borrowing and lending markets.
---

# Borrow against sPinto on Cream Finance

### Step 1: Wrap your pinto into sPinto from the Pinto UI

* Navigate to Pinto UI, go to [https://pinto.money/wrap](https://pinto.money/wrap), connect your wallet and choose an amount of Pinto to wrap from your existing Silo Deposits. The UI will automatically wrap your Pinto Deposits with the least amount of Grown Stalk.
* If you don’t have Pinto Deposited in the Silo, use any of the available tokens in your wallet and the UI will automatically swap them into Pinto and wrap them into sPinto.
* After approving and wrapping, you should now see sPinto tokens appear in your wallet.

<figure><img src="../.gitbook/assets/image (1).png" alt="" width="375"><figcaption></figcaption></figure>

### Step 2: Borrow USDC against your sPinto on Cream

* Now that you acquired sPinto, lets put it as collateral so you can borrow against it on Cream.
* Go to [https://app.cream.finance/](https://app.cream.finance/).
* Connect your wallet and change your network to “Base” on the top right of the screen

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

* Choose "sPinto" as a supply asset (left) and click on it

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

* Choose the amount you wish to supply.
* Click on “Approve” and sign the transaction on the popup.

<figure><img src="../.gitbook/assets/image (4).png" alt="" width="375"><figcaption></figcaption></figure>

* Then click on "Supply" to supply sPinto to the market.
* Next, you need to make your sPinto a collateral asset by clicking on the toggle on the right and signing the required transaction. Wait a few seconds and you should see the toggle turned on.

<figure><img src="../.gitbook/assets/image (5).png" alt="" width="563"><figcaption></figcaption></figure>

* Now you are ready to borrow USDC against your sPinto collateral. Choose "USDC" as a borrow asset on the right.

<figure><img src="../.gitbook/assets/image (6).png" alt="" width="375"><figcaption></figcaption></figure>

* Use the slider to choose a USDC borrow amount.&#x20;
* Note the Borrow APY. This is the interest you would be paying annually for your USDC loan.
* The loan to value ratio max for sPinto is 75%. This means that _if the Pinto price decreases such that your loan is worth more than 75% of your collateral you will get **liquidated**_. It also means that you can borrow up to 75% of the USD value of the sPinto being used as collateral. ie $1000 of sPinto can borrow 750 USDC.
* **Collateral Up:** When sPinto accrues value (from new Pinto mints) your collateral value will automatically increase and risk of liquidation decrease. If there are significant mints it will be safe to return and borrow more _without adding additional collateral_.
* **Collateral Down:** sPinto will never decrease in terms of Pinto, but if the Pinto/USD price decreases your collateral will be worth less relative to the USDC loan. This is the only way to get liquidated.

<figure><img src="../.gitbook/assets/image (7).png" alt="" width="375"><figcaption></figcaption></figure>

* This page lets you set your borrow amount as a percentage _of the maximum borrow amount_. So 75% on this page is \~56% of the value of your collateral (75% max LTV \* 75% borrow). So 75% here means that you will get liquidated if Pinto decreases in value by 25% with no new mints.
* When you’re ready to borrow the USDC just click on “Borrow” and sign the transaction in your wallet.
* You have now borrowed against your sPinto collateral, meaning you are long sPinto while your collateral asset is increasing in value due to silo yield, thus, repaying your loan if the Silo APY is above your loan interest rate.

### Step 3: Repeat to get Leveraged Long sPinto exposure.

* With that USDC loan, you can go and purchase pinto on the pinto UI again [https://pinto.money/swap](https://pinto.money/swap) and rewrap it into sPinto.
* Then you can supply that sPinto as collateral again on Cream and repeat the same process, meaning you get leveraged exposure to sPinto and sPinto yield.
* The formula to figure out max leverage exposure is `1/(1-LTV)` meaning with an 75% LTV, you could leverage sPinto 4x. Note that this increases liquidation risk meaning if the price of Pinto drops significantly, cream will seize your collateral and sell it, meaning you will incur a loss.

### Notes

#### Borrow sPinto Against any collateral asset on Cream

* If you do the process above in reverse, you can borrow sPinto against some other collateral asset, meaning, you'll be effectively shorting sPinto, with the risk of  your loan increasing in value due to either the sPinto price increasing or sPinto yield being distributed. Be careful when doing this as there these 2 factors might work against you.

#### Borrow interest and kinks

* Keep an eye out on the borrow APY (your loan interest rate). This depends on market utilization of USDC. If utilization goes above 90% (or \~16% interest rate/ borrow APY) then the interest rate skyrockets because of the shape of the interest rate curve and sPinto yield might not be enough to offset this.

<figure><img src="../.gitbook/assets/image (8).png" alt="" width="563"><figcaption></figcaption></figure>

* sPinto utilizes the stable interest rate curve on Cream. For more information visit: [https://docs.cream.finance/lending/interest-rate-model](https://docs.cream.finance/lending/interest-rate-model)
