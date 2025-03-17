# Sell Pods

Pods can be exchanged in a trustless fashion on the Pod Market. Read [Pod Market](../../farm/toolshed/pod-market.md) first for an introduction to Pod Market mechanics, [Pod Listings](../../resources/glossary.md#pod-listing) and [Pod Orders](../../resources/glossary.md#pod-order).

* [List Pods](sell-pods.md#list-pods)
* [Fill Pod Order](sell-pods.md#fill-pod-order)

Note: The Pod Market is not available yet on the mobile UI.

### List Pods <a href="#list-pods" id="list-pods"></a>

1. Make sure you are on [https://pinto.money/](https://pinto.money/) and [connect your wallet](../getting-started/connect-to-pinto.md).
2. Navigate to the 'Pod Market' page.
3. Select 'Sell Pods' then select the 'List' tab.
   * The 'Select Plot' dropdown shows all your Plots. Select the Plot that has the Pods you would like to List and enter the number of Pods to List.
   * 'Amount I want for each Pod' is how much to sell each Pod for, denominated in Pinto.
   * If the Pod Line moves forward by the amount in 'Expires In', the Pod Listing will automatically expire.
4. Under 'Send proceeds to', select 'Wallet Balance' or 'Farm Balance'. Selecting Wallet Balance sends the proceeds to your wallet. Selecting Farm Balance keeps the proceeds stored in Pinto.
5. A transaction preview will appear below the inputs.
6. Select 'List Pods'.
7. Confirm the transaction in your wallet and your hardware wallet, if applicable. You should verify that the transaction is interacting with the [correct contract](../../resources/contracts.md) before signing it.
8. After the transaction has been confirmed by the network, your Pod Listing will be shown on the 'Pod Market' page under the 'My Activity' tab, where you can check the status of your Pod Listing or cancel it.
9. When your Pod Listing is filled, the location of your Pinto will depend on the option selected in Step 4:
   * If 'Wallet Balance' was selected, the Pinto will be in your wallet.
   * If 'Farm Balance' was selected, view your balances by selecting your wallet address in the upper right, then select 'Farm Balance'.

### Fill Pod Order <a href="#fill-pod-order" id="fill-pod-order"></a>

1. Make sure you are on [https://pinto.money/](https://pinto.money/) and [connect your wallet](../getting-started/connect-to-pinto.md).
2. Navigate to the 'Pod Market' page.
3. Select 'Sell Pods' then select the 'Fill' tab. This view displays all the active Pod Orders, sorted by ascending [Place in Line](../../resources/glossary.md#pod-line).
   * 'Amount' is the number of Pods left to be sold to the Pod Order.
   * Any Pods within the Pod Line range listed under 'Place in Line' are eligible to be sold to the Pod Order.
   * The 'Price' is the number of Pinto offered per Pod.
4. Select a Pod Order to view details or to sell Pods to a Pod Order.
5. Under the 'Fill' modal, select the Plot you would like to use to Fill the Pod Order, and enter the number of Pods you would like to sell. You may sell up to the 'Amount' to the Pod Order.
6. Under 'Destination', select 'Wallet Balance' or 'Farm Balance'. Selecting Wallet Balance sends the proceeds to your wallet. Selecting Farm Balance keeps the proceeds stored in Pinto.
7. A transaction preview will appear below the inputs.
8. Select 'Sell Pods'.
9. Confirm the transaction in your wallet and your hardware wallet, if applicable. You should verify that the transaction is interacting with the [correct contract](../../resources/contracts.md) before signing it.
10. After the transaction has been confirmed by the network, the location of your proceeds will depend on the option selected in Step 6:
    * If 'Wallet Balance' was selected, the Pinto will be in your wallet.
    * If 'Farm Balance' was selected, view your balances by selecting your wallet address in the upper right, then select 'Farm Balance'.
