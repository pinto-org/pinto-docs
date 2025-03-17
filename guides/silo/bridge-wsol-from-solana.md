# Bridge WSOL from Solana

WSOL liquidity on Base is [limited](https://basescan.org/token/0x1c61629598e4a901136a81bc138e5828dc150d67), which may result in worse price execution if exchanging for WSOL on Base. To avoid this, you can mint new WSOL on Base by bridging SOL directly from the Solana network using the Portal Bridge.

Bridging has security risks, so research and evaluate third-party services before using them.

* [Moving Funds from Base to Solana](bridge-wsol-from-solana.md#moving-funds-from-base-to-solana)
* [Bridging SOL Using the Portal Bridge](bridge-wsol-from-solana.md#bridging-sol-using-the-portal-bridge)

### Moving Funds from Base to Solana

1. Go to [https://portalbridge.com/](https://portalbridge.com/) and in the 'From' selector, choose 'Base'.
2. In the 'To' selector, choose 'Solana'.
3. Select 'Connect source wallet' and 'Connect destination wallet' to connect your Base and Solana wallets. If you do not have a Solana wallet yet, [Phantom](https://phantom.app/) is a popular choice.
4. Choose which token you want to send through the Portal Bridge under the 'From' selector and which token to receive under the 'To' selector:
   * If sending and receiving different tokens, e.g. ETH to SOL or USDC to SOL, Portal Bridge will use [Mayan Swift](https://docs.mayan.finance/architecture/swift) to perform the exchange. There is a nominal fee for this method and it is subject to potential exchange slippage.
   * If sending USDC to USDC, you will have the choice under 'Routes' to use Mayan Swift or [Mayan MCTP](https://docs.mayan.finance/architecture/mctp). Mayan MCTP uses [Circle CCTP](https://www.circle.com/en/cross-chain-transfer-protocol) to bridge. There are no protocol fees for this method and you can choose any exchange once on Solana to swap the USDC to SOL, such as [Jupiter](https://jup.ag/).
5. Enter the amount to send and confirm the bridging details under 'Routes'.
6. Approve (if applicable), review and confirm the bridging transaction. After confirmation, you will now have SOL in your Solana wallet.

### Bridging SOL Using the Portal Bridge

1. Go to [https://portalbridge.com/](https://portalbridge.com/) and in the 'From' selector, choose 'Solana' and 'SOL'.
2. In the 'To' selector, choose 'Base' and 'WSOL''.
3. Select 'Connect source wallet' and 'Connect destination wallet' to connect your Solana and Base wallets.
4. Enter the amount of SOL to send and confirm the bridging details under 'Routes'.
5. Review and confirm the bridging transaction. After confirmation, you will now have WSOL in your Base wallet.
   * Because of the relative low quantity of WSOL on Base, some wallets may not show your balance. View your WSOL balance by connecting to [https://pinto.money/](https://pinto.money/) and selecting your wallet address in the upper right.
