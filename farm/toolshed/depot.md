# Depot

Current complex interactions with EVM-native protocols are tedious, cumbersome and expensive. The Depot facilitates complex, gas-efficient interactions with other protocols on Base in a single transaction. The Depot contains [Pipeline](https://evmpipeline.org).

Pipeline allows anyone to perform an arbitrary series of actions in the EVM in a single transaction by using [0xb1bE0001f5a373b69b1E132b420e6D9687155e80](https://basescan.org/address/0xb1bE0001f5a373b69b1E132b420e6D9687155e80) as a sandbox for execution.

The following functions can be called via Pipeline:

* `pipe(...)`
* `multiPipe(...)`
* `advancedPipe(...)`
