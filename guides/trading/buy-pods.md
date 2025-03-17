# Buy Pods

Pods can be exchanged in a trustless fashion on the Pod Market. Read [Pod Market](../../farm/toolshed/pod-market.md) first for an introduction to Pod Market mechanics, [Pod Listings](../../resources/glossary.md#pod-listing) and [Pod Orders](../../resources/glossary.md#pod-order).

* [Fill Pod Listing](buy-pods.md#fill-pod-listing)
* [Order Pods](buy-pods.md#order-pods)

Note: The Pod Market is not available yet on the mobile UI.

### Fill Pod Listing <a href="#fill-pod-listing" id="fill-pod-listing"></a>

1. Make sure you are on [https://pinto.money/](https://pinto.money/) and [connect your wallet](../getting-started/connect-to-pinto.md).
2. Navigate to the 'Pod Market' page.
3. Open Pod Listings appear below the 'Listings' tab. This view displays all the Pod Listings, sorted by ascending [Place in Line](../../resources/glossary.md#pod-line).
   * The 'Amount' is the number of Pods left to be purchased from the Pod Listing.
   * The 'Place in Line' is the position in the Pod Line when the Pods in the Pod Listing will start to become Harvestable.
   * The 'Price' is the number of Pinto requested per Pod.
   * If the Pod Line moves forward by the amount in the 'Expires In' field, the Pod Listing will automatically expire.
4. Select a Pod Listing to view details and to buy Pods from a Pod Listing.
5. Under the 'Fill Using' component, select the token you would like to use to buy Pods, and enter the amount you would like to buy. You may buy up to the 'Amount' of Pods available from the Pod Listing.
6. A transaction preview will appear below the inputs.
7. You may select a slippage tolerance by selecting the gear icon. The default slippage tolerance is 0.1%.
8. If an approval is not necessary, skip to Step 10. For all other cases, select 'Approve Spending'. This allows the Pinto contract to spend the asset, but does not use it yet.
9. Confirm the approval transaction in your wallet, and your hardware wallet, if applicable. You should verify that the transaction is interacting with the [correct contract](../../resources/contracts.md) before signing it.
10. Select 'Buy Pods'.
11. Confirm the transaction in your wallet and your hardware wallet, if applicable. You should verify that the transaction is interacting with the [correct contract](../../resources/contracts.md) before signing it.
12. After the transaction has been confirmed by the network, your Pods will appear in the 'My Pods' table at the bottom of the 'Field' page.

### Order Pods <a href="#order-pods" id="order-pods"></a>

1. Make sure you are on [https://pinto.money/](https://pinto.money/) and [connect your wallet](../getting-started/connect-to-pinto.md).
2. Navigate to the 'Pod Market' page.
3. Select 'Buy Pods'. 'Order' is selected by default, allowing you to create a Pod Order.
   * 'I want to order Pods with a Place in Line up to' is the maximum [Place in Line](../../resources/glossary.md#pod-line) at which you are willing to buy Pods at the specified price. Any Pods at a lower Place in Line than the maximum Place in Line will be eligible to Fill the Pod Order.
   * 'Amount I am willing to pay for each Pod' is how much you will pay for each Pod, denominated in Pinto.
   * 'Order Using' specifies the amount and the asset to be used to buy Pods. This amount will be locked in the Pod Order to allow for instant settlement. Pod Orders may be partially filled.
4. A transaction preview will appear below the inputs.
5. You may select a slippage tolerance by selecting the gear icon. The default slippage tolerance is 0.1%.
6. If an approval is not necessary, skip to Step 8. For all other cases, select 'Approve Spending'. This allows the Pinto contract to spend the asset, but does not use it yet.
7. Confirm the approval transaction in your wallet, and your hardware wallet, if applicable. You should verify that the transaction is interacting with the [correct contract](../../resources/contracts.md) before signing it.
8. Select 'Order Pods'.
9. Confirm the transaction in your wallet and your hardware wallet, if applicable. You should verify that the transaction is interacting with the [correct contract](../../resources/contracts.md) before signing it.
10. After the transaction has been confirmed by the network, your Pod Order will be shown on the 'Pod Market' page under the 'My Activity' tab, where you can check the status of your Pod Order or cancel it.
