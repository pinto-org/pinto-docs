# Tractor

Maintaining and optimizing a position in Pinto requires manual intervention (Mowing, Planting, Harvesting Pods and Depositing the Pinto, etc.). Smaller Farmers do not necessarily have the resources to automate the execution of their Pinto transactions, and existing generalized function call systems (i.e., smart contract accounts, Pipeline) only support the use of assets from the sender of the transaction.

Tractor is a peer-to-peer transaction marketplace that allows third parties to perform pre-authorized\
actions through the protocol on behalf of a user.

Blueprints are off-chain data structures that are [EIP-712](https://eips.ethereum.org/EIPS/eip-712) signed to verify the intent of the publishing Farmer. Blueprints allow Farmers to define arbitrary sequences of on-chain function calls, which can be executed permissionlessly by other Farmers known as Operators.

The Pinto UI currently supports the following Tractor use cases:

* [Sowing via Deposits](https://x.com/pintodotmoney/status/1914728533320237207)
