# Sow Pinto

When there is [Soil](../../resources/glossary.md#soil) in the [Field](../../farm/field.md), Farmers can lend their Pinto to the protocol for an interest rate known as the [Temperature](../../peg-maintenance/temperature.md).

1. Make sure you are on [https://pinto.money/](https://pinto.money/) and [connect your wallet](../getting-started/connect-to-pinto.md).
2. Navigate to the 'Field' page.
3. The amount of Pinto that can be Sown for Soil is shown under 'Available Soil'. Pods will be issued in accordance with the 'Current Temperature'.
   * The Soil supply is set by the Pinto peg maintenance mechanism. See [Soil Supply ](../../peg-maintenance/overview.md#soil-supply)for additional information.
   * During the first ten minutes of each Season, the Temperature ramps from 1% to 100% of the Maximum Temperature in a Dutch auction known as the Morning Auction.
4. Select the 'Sow' tab.
5. There is a dropdown menu to select the token you would like to use to buy and Sow Pinto.
6. Enter the amount of the selected token you want to use to buy and Sow Pinto.
   * The Soil available when preparing to buy and Sow Pinto may not still be available at the time the transaction is confirmed by the network.&#x20;
   * If a transaction is submitted to Sow a greater amount of Soil than is available, the remaining Soil will be Sown, and all remaining Pinto from the transaction will be sent to your [Farm Balance](../../resources/glossary.md#farm-assets).
   * If you are Sowing during the Morning Auction, the number of Pods to be received will increase in real time on the UI with the increasing Temperature.
   * The actual amount of Pods you receive depends upon Soil availability and the Temperature at the time your transaction is confirmed.
7. You may select a slippage tolerance or minimum acceptable Temperature by selecting the gear icon. The default slippage tolerance is 0.1%.
   * The transaction will revert if it doesn't meet the specified conditions.
8. If an approval is not necessary, skip to Step 10. For all other cases, select 'Approve Spending'. This allows the Pinto contract to spend the asset, but does not use it yet.
9. Confirm the approval transaction in your wallet, and your hardware wallet, if applicable. You should verify that the transaction is interacting with the [correct contract](../../resources/contracts.md) before signing it.
10. Select 'Sow'.
11. Confirm the transaction in your wallet and your hardware wallet, if applicable. You should verify that the transaction is interacting with the [correct contract](../../resources/contracts.md) before signing it.
12. After the transaction has been confirmed by the network, your Pods will appear in the 'My Pods' table at the bottom of the 'Field' page.
