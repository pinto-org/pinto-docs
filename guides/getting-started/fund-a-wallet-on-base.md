# Fund a Wallet on Base

Interacting with Pinto requires a wallet on the [Base network](https://www.base.org/) with an Ethereum (ETH) balance.

* [Selecting and Funding a Wallet](fund-a-wallet-on-base.md#selecting-and-funding-a-wallet)
* [Creating a Wallet on Base with Rabby (Browser Extension)](fund-a-wallet-on-base.md#creating-a-wallet-on-base-with-rabby-browser-extension)
* [Creating a Wallet on Base with Rabby (Mobile)](fund-a-wallet-on-base.md#creating-a-wallet-on-base-with-rabby-mobile)
* [Fund your Wallet from Coinbase](fund-a-wallet-on-base.md#fund-your-wallet-from-coinbase)
* [Bridging from Other Networks](fund-a-wallet-on-base.md#bridging-from-other-networks)

### **Selecting and Funding a Wallet** <a href="#selecting-and-funding-a-wallet" id="selecting-and-funding-a-wallet"></a>

Wallets are applications that let you manage your assets on the Base network. Your wallet lets you connect to decentralized applications such as Pinto and authorize transactions. On Base, you are responsible for the security of your own funds. If you are new to decentralized finance, it strongly recommend to research best practices in wallet security before proceeding.

Pinto works with many Base-compatible wallets. Some wallets allow purchasing Ethereum directly within the wallet. Alternatively, send Ethereum from a cryptocurrency exchange to your wallet address. Make sure both sending and receiving addresses are on the Base network.

Here's how to fund a wallet using Rabby and Coinbase as an example, though the process is similar for other wallets and exchanges.

### Creating a Wallet on Base with Rabby (Browser Extension)

1. Go to [https://rabby.io/](https://rabby.io/) and select 'Download for Chrome'.
2. You will be taken to the Chrome Web Store where you can select 'Add to Chrome' and approve the installation in your browser.
3. Rabby is now installed and can be opened from your browser's extension menu (the puzzle piece icon in the top right corner).
4. To create a new wallet, select 'Create a new address' and follow the instructions. For better security, you can connect a hardware wallet instead and select 'I already have an address'.
   1. A hardware wallet protects your assets even if your computer is hacked.
   2. The hardware wallet must be supported by Rabby - check the list provided by selecting 'I already have an address'.
5. Never share your seed phrase - anyone who has it can steal your assets. Keep it offline in a secure location, as it's your only way to recover your wallet.
6. To copy your wallet address on Base, open Rabby and select the copy icon: ![](<../../.gitbook/assets/image (1).png>)

### Creating a Wallet on Base with Rabby (Mobile)

1. Download Rabby from the [App Store](https://apps.apple.com/us/app/rabby-wallet-crypto-evm/id6474381673) or [Google Play](https://play.google.com/store/apps/details?id=com.debank.rabbymobile\&hl=en_US).
2. To create a new wallet, select 'Create New Address' and follow the instructions. For better security, you can connect a hardware wallet instead and select 'I already have an address'.
   * A hardware wallet protects your assets even if your device is hacked.
   * The hardware wallet must be supported by Rabby - check the list provided by selecting 'I already have an address'.
3. Never share your seed phrase - anyone who has it can steal your assets. Keep it offline in a secure location, as it's your only way to recover your wallet.
   * If you opt for cloud backup, your wallet can be accessed by anyone who has both your cloud account credentials and the encryption password.
4. To connect to an app such as Pinto, select 'Dapps' and enter the URL (e.g. [https://pinto.money](https://pinto.money)) in the in-app browser.
5. To copy your wallet address on Base, select 'Receive', then select the displayed address.

### Fund your Wallet from Coinbase

1. Buy Ethereum on Coinbase before transferring it to your wallet. See Coinbase documentation for purchase instructions.
2. Go to [https://www.coinbase.com/assets](https://www.coinbase.com/assets).
3. Select 'Send crypto'.
4. Click the "Send" arrow and type 'Ethereum'.
5. Enter the amount to send in USD, or click the switch icon to enter it in Ethereum instead.
6. Click the 'To' arrow and under 'Send via' select 'Base'.
7. Under 'Send Ethereum on Base to' enter your wallet address on Base.
8. Select 'Preview Send' then 'Send'.
9. You have funded your wallet and are now ready to [Connect to Pinto](connect-to-pinto.md).

### Bridging from Other Networks

Bridging has security risks, so research and evaluate third-party services before using them.

1. Go to [https://jumper.exchange/](https://jumper.exchange/) and select 'Connect' to connect your wallet.
2. Under 'From' select the network and asset you want to bridge to Base.
3. Under 'To' select Base and the Pinto-native asset you plan to use with Pinto.
   * Jumper will exchange between the input and output asset as well as performing the network bridge.
4. Under "Receive," select a bridging provider and verify that the output amount provides acceptable execution.
5. Select 'Review Bridge' and 'Start Bridging' to prompt the approval and bridging transactions to your wallet.
   * If you haven't used your wallet on Base before and you're bridging assets other than ETH, you may need to bridge some ETH separately to cover gas fees while using Pinto.

