# Whitelist Info

### Deposit Whitelist Requirements

* The token address;
* The optimal percentage of Deposited LP PDV (shown below);
* A function to calculate the Pinto Denominated Value (PDV) of the token;
* The number of Stalk issued per PDV (all set to 1 upon the deployment of Pinto);
* The number of initial [Gauge Points](../advanced/gauge-system.md#gauge-points) (which determine Grown Stalk issuance across various LP tokens—all were initialized to 0 upon the deployment of Pinto);
* An oracle for calculating the price on the non-Pinto asset in the pool;
* A function to calculate how the Gauge Points for the asset should change each Season;
* A function to calculate what portion of liquidity in the pool counts towards the [Liquidity to Supply Ratio](../resources/glossary.md#liquidity-to-supply-ratio-l2sr) (_i.e._, Liquidity Weight—all were set to 100% upon the deployment of Pinto); and
* The optimal percentage of Deposited LP PDV (shown [here](../farm/silo.md#current-deposit-whitelist)).
