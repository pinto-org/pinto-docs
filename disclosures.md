# Disclosures

This document is kept up to date, but a version was uploaded to Arweave prior to the deployment of Pinto [here](https://arweave.net/AZYRdhsRn8FPacI2kh4fw75NeoCmavZ0F4yq0HX2r08).

**Before interacting with Pinto, consider reading the following disclosures.**

Pinto is an experiment and interacting with it involves many risks. Before interacting with Pinto, you should review the relevant documentation to make sure you understand how Pinto works, as well as information about the current state of Pinto. The following disclosures are not exhaustive. This GitBook and participating in discussion in the [Pinto community](https://pinto.money/discord) can help to understand the protocol. Before participating in the protocol, everyone should do their own research, investigation and analysis.

#### **1. PINTO IS A FORK OF BEANSTALK. THE PINTO PEG MAINTENANCE MECHANISM IS VERY SIMILAR TO BEANSTALK'S, WITH SOME EXCEPTIONS.** <a href="#beanstalk-fork" id="beanstalk-fork"></a>

Pinto is a fork of [Beanstalk](https://bean.money). Ultimately, this means that the peg maintenance mechanism and implementation of Pinto closely resemble those of Beanstalk. Both the Pinto and Beanstalk peg maintenance mechanisms are experiments and have many risks (see [#4](disclosures.md#no-lender-of-last-resort), [#5](disclosures.md#no-price-guarantee) and [#6](disclosures.md#no-maturity-date-risk)).

A non-exhaustive list of the contract changes made to Pinto since the most recent version of Beanstalk are documented [here](resources/audits.md).

#### **2. THERE IS NO MAXIMUM PINTO SUPPLY. THE PINTO SUPPLY CAN GROW INFINITELY THROUGH DEMAND-BASED AND ONE-OFF MINTING.** <a href="#no-maximum-supply" id="no-maximum-supply"></a>

The Pinto supply increases every Season where the time weighted average price of 1 Pinto is greater than $1 over the previous Season. Enough Pinto are minted such that if all the newly minted Pinto were sold, the price would return to $1 (with the exception of mints related to the [gm reward](disclosures.md#gm-incentivization-risk) and [Flood](peg-maintenance/flood.md)). The distribution of new Pinto is documented [here](farm/sun.md#shipments).

The Pinto supply is uncapped and grows as demand for Pinto increases. Pinto can also be minted arbitrarily in a one-off fashion (see [#3](disclosures.md#no-pre-mine)).

More information:

* [Pinto Mint Distribution](farm/sun.md#shipments)
* [Pinto Supply Documentation](peg-maintenance/overview.md#bean-supply)

#### **3. PINTO DID NOT HAVE A PRE-MINE OR PRE-SALE. ALL PINTO HAVE BEEN MINTED IN ACCORDANCE WITH EITHER THE MINTING SCHEDULE OR ONE-OFF MINTS PERMITTED IN THE UPGRADABILITY DOCS.** <a href="#no-pre-mine" id="no-pre-mine"></a>

Pinto did not have a pre-mine or pre-sale of any kind. The first 1000 Pinto were minted when the `init` function was called to deploy the protocol. Pinto launched without the need to raise capital.&#x20;

Apart from demand-based minting, Pinto can also be minted in a one-off fashion according to the permitted upgrades in the [Upgradability](appendix/upgradability.md) docs.

More information:

* [Permitted Pinto Upgrades](appendix/upgradability.md)

#### **4. PINTO RELIES ON THIRD PARTIES TO PROVIDE CREDIT TO RETURN THE PINTO PRICE TO ITS PEG. THERE IS NO LENDER OF LAST RESORT.** <a href="#no-lender-of-last-resort" id="no-lender-of-last-resort"></a>

Pinto uses a credit based model, allowing anyone to lend Pinto to the protocol to participate in peg maintenance. The protocol burns any Pinto it borrows. As a consequence, the ability of the protocol to return the price of Pinto to its peg relies on the availability of willing creditors, which is not guaranteed. The economic design of Pinto fails if it can no longer attract creditors.

More information:

* [Field Documentation](farm/field.md)

#### **5. THE PROTOCOL DOES NOT GUARANTEE THE PINTO PRICE. INSTEAD THE PROTOCOL INCENTIVIZES THE REGULAR OSCILLATION OF THE PINTO PRICE ABOVE AND BELOW ITS PEG THROUGH PROTOCOL-NATIVE INCENTIVES.** <a href="#no-price-guarantee" id="no-price-guarantee"></a>

Pinto is not collateralized and the protocol offers no guarantee of the value of Pinto. Pinto is in an early stage and various parts of its economic design will continue to be improved through forks (see [Fork Migration System](appendix/upgradability.md#fork-migration-system)).

The protocol tries to incentivize the regular oscillation of the Pinto price above and below its peg. While the protocol's incentives are designed to return the price of Pinto to its peg, the timing of oscillations is indeterminate. The price will almost never be exactly equal to its peg. Crossing the peg in the past is no guarantee of it happening again in the future.

More information:

* [Peg Maintenance Documentation](peg-maintenance/overview.md)

#### **6. PINTO-NATIVE DEBT DOES NOT HAVE A MATURITY DATE AND THEREFORE MAY NEVER BECOME REDEEMABLE FOR PINTO.** <a href="#no-maturity-date-risk" id="no-maturity-date-risk"></a>

The protocol borrows Pinto from lenders in exchange for Pods. Pinto loans have fixed interest rates but do not have fixed maturity dates.

Pods are repaid when the time weighted average price of 1 Pinto is greater than $1 over the previous Season, but there is no guarantee this will continue until all Pods become redeemable (see [#4](disclosures.md#no-lender-of-last-resort)).

More information:

* [Economics Documentation](advanced/economics.md)

#### **7. THE PINTO CONTRACT IS OWNED BY THE PINTO CONTRACT MULTISIG. THE MULTISIG CAN MAKE ARBITRARY CHANGES TO PINTO WITH 5-OF-9 SIGNATURES FROM THE ANONYMOUS SIGNERS. THERE IS NO GUARANTEE THE MULTISIG SOLELY ENACTS THE UPGRADES PERMITTED IN THE UPGRADABILITY DOCS.** <a href="#multisig-risk" id="multisig-risk"></a>

Ownership of the Pinto contract is held by a 5-of-9 multisig known as the Pinto Contract Multisig (PCM). There is no guarantee the PCM solely enacts the upgrades permitted in the [Upgradability docs](appendix/upgradability.md).&#x20;

More information:

* [Permitted Pinto Upgrades](appendix/upgradability.md)

#### **8. A VULNERABILITY IN ETHEREUM OR BASE COULD RESULT IN A LOSS OF FUNDS. PINTO ASSUMES THE SECURITY OF ETHEREUM AND BASE.** <a href="#network-risk" id="network-risk"></a>

Ethereum is the largest smart contract blockchain by market capitalization, total value deposited, and dollar denominated transaction value. Base is one of the largest Ethereum L2s by TVL. In general, open source networks with large amounts of value on them and long track records indicate security, but there is no guarantee. Pinto assumes the security of Ethereum and Base.

#### **9. A VULNERABILITY IN PINTO EXCHANGE OR ITS COMPONENTS COULD RESULT IN A LOSS OF FUNDS. PINTO ASSUMES THE SECURITY OF PINTO EXCHANGE AND ITS CORRESPONDING COMPONENTS.** <a href="#pinto-exchange-risk" id="pinto-exchange-risk"></a>

Pinto trade in Wells on the [Pinto Exchange](https://pinto.exchange). Well LP tokens are whitelisted in the Silo and used by the protocol to determine how many Pinto and/or Soil to mint. Pinto Exchange and the corresponding components that Pinto uses (the Constant Product 2 Well Function, the Stable 2 Well Function, the Well Implementation, Multi Flow, etc.) were [audited](https://docs.pinto.exchange/resources/audits) (as [Basin](https://basin.exchange)). There is no guarantee that Pinto Exchange or its components are secure. Pinto assumes the security of Pinto Exchange and its corresponding components.

More information:

* [Pinto Exchange Docs](https://docs.pinto.exchange)

#### **10. A VULNERABILITY IN PIPELINE COULD RESULT IN A LOSS OF FUNDS. PINTO ASSUMES THE SECURITY OF PIPELINE.** <a href="#pipeline-risk" id="pipeline-risk"></a>

Through Pinto, users can perform complex, gas-efficient interactions with other Base-native protocols, like Pipeline. Pipeline is a sandbox contract allows anyone to perform an arbitrary series of actions in the EVM in a single transaction.

Pipeline has been [audited](https://github.com/BeanstalkFarms/Beanstalk-Audits?tab=readme-ov-file#ecosystem-reports), but there is no guarantee that Pipeline is secure. Pinto assumes the security of Pipeline.

More information:

* [Pipeline Whitepaper](https://evmpipeline.org/pipeline.pdf)
* [Depot Documentation](farm/toolshed/depot.md)

#### **11. THE PINTO PRICE IS DERIVED FROM THE VALUE OF ASSETS IT TRADES AGAINST IN DECENTRALIZED AMMS. THERE IS NO GUARANTEE ANY OF THESE ASSETS RETAIN VALUE.** <a href="#non-pinto-asset-risk" id="non-pinto-asset-risk"></a>

The value of Pinto is derived from the non-Pinto assets (WETH, cbETH, cbBTC, WSOL and USDC) trading against it in decentralized liquidity pools. Each of these assets have their own set of associated risks, unique to the asset. Pinto implicitly assumes risk associated with these assets.

#### **12. BECAUSE PINTO DERIVE THEIR VALUE FROM THE ASSETS THEY TRADE AGAINST, AND NOT COLLATERAL, IT IS NOT POSSIBLE FOR ALL PINTO HOLDERS TO EXIT AT A DOLLAR OF VALUE FOR EVERY PINTO.** <a href="#not-everyone-can-exit-at-a-dollar" id="not-everyone-can-exit-at-a-dollar"></a>

Pinto are not redeemable for any other asset; they can only be traded for another asset that Pinto are trading against. As Pinto holders sell their Pinto, there is less and less value trading against Pinto. Thus, unlike collateralized stablecoins, it is not possible for the Pinto supply to scale down to zero with every Pinto holder getting a dollar of value for every Pinto sold.

#### **13. PINTO REQUIRES TRUSTLESS AND RELIABLE ACCESS TO A MANIPULATION RESISTANT PRICE ORACLE FOR A DOLLAR. PINTO USES A CHAINLINK DATA FEED TO DETERMINE THE PRICE OF A DOLLAR. THERE IS RISK ASSOCIATED WITH CHAINLINK THAT CAN COMPROMISE ITS INTEGRITY AS AN ACCURATE PRICE ORACLE.** <a href="#oracle-risk" id="oracle-risk"></a>

Pinto's core objective is to oscillate the price of a Pinto above and below its dollar peg. To do this, the protocol must be able to reliably measure the price of a dollar on-chain without trusting a centralized third-party to provide it. A disruption in the reliability of various Chainlink data feeds could impact Pinto minting, resulting in adverse consequences for the protocol.

More information:

* [Price Oracle Documentation](peg-maintenance/overview.md#decentralized-price-oracle)

#### **14. PINTO REQUIRES THAT THE GM FUNCTION IS CALLED AT THE TOP OF EACH HOUR ON BASE. FAILURE TO SUCCESSFULLY INCENTIVIZE THE CALLING OF THE GM FUNCTION COULD HAVE AN ADVERSE AFFECT ON THE PROTOCOL'S ABILITY TO OSCILLATE THE PINTO PRICE ABOVE AND BELOW ITS PEG.** <a href="#gm-incentivization-risk" id="gm-incentivization-risk"></a>

Pinto and/or Soil are minted upon a successful call of the gm function. The protocol covers the cost of the gm function by awarding the sender of an accepted gm function call with newly minted Pinto. The failure of the protocol to successfully incentivize the calling of gm would effectively result in the failure of the protocol to influence the size of the Pinto supply, and thereby the Pinto price.

More information:

* [Sun Documentation](farm/sun.md)

#### **15. THE PINTO CONTRACTS ARE OPEN SOURCE. ANYONE CAN VIEW THE SOURCE CODE AND ATTEMPT TO FIND VULNERABILITIES.** <a href="#open-source-risk" id="open-source-risk"></a>

The Pinto contracts are open source and deployed on Base. There may be bugs, flaws, or other unintended consequences from using open source code to govern irreversible financial transactions on a decentralized network. These issues may lead to a loss of funds if present and discovered by malicious actors.

More information:

* [Pinto on GitHub](https://github.com/pinto-org/protocol)

#### **16. PINTO IS AUDITED BUT AUDITS CANNOT GUARANTEE SECURITY. IT IS ANTICIPATED THAT FUTURE CODE WILL NOT BE AUDITED BEFORE BEING COMMITTED.** <a href="#audit-risk" id="audit-risk"></a>

Security is paramount to Pinto's success. The version of Pinto currently deployed on Base is heavily audited (via [Beanstalk](https://docs.bean.money/almanac/protocol/audits)), but there is no guarantee that Pinto is secure.

In the future, it is anticipated that the code will be upgraded per the [Upgradability documentation](appendix/upgradability.md). There is always additional risk associated with implementing any new code.

There is no guarantee that interacting with Pinto through the Pinto UI is secure. Any issues could lead to a loss of funds.

More information:

* [Beanstalk Audits](https://docs.bean.money/almanac/protocol/audits)
* [Permitted Pinto Upgrades](appendix/upgradability.md)

#### **17. THE PINTO USER INTERFACE CAN BE CENSORED AS IT IS HOSTED ON A CLOUD PROVIDER.** <a href="#ui-provider-risk" id="ui-provider-risk"></a>

The Pinto UI hosted at [pinto.money](https://pinto.money) is hosted on Netlify, a privately held United States based cloud provider. Netlify could censor the UI at will, or a technical disruption could prevent access. In either scenario, Pinto would not be accessible from a web browser until Pinto contributors could deploy the UI elsewhere (or once the UI is open source, until other parties could use the open source code to deploy their own UI to interact with the Pinto contracts).

There have been multiple instances of Netlify getting compromised, resulting in phishing attacks. There is no guarantee that the Pinto UI will not be subjected to similar attacks.

#### **18. THE PINTO USER INTERFACE DEPENDS ON VARIOUS DATA PROVIDERS FOR DISPLAYING ONCHAIN DATA. THERE IS NO GUARANTEE THAT THE DATA FROM THESE PROVIDERS IS ACCURATE OR AVAILABLE.** <a href="#data-provider-risk" id="data-provider-risk"></a>

The Pinto UI hosted at [pinto.money](https://pinto.money) depends on Alchemy, 0x, the Pinto Subgraph Proxy and the Pinto Subgraphs for displaying various onchain data.

The Pinto UI uses:

* Alchemy, a privately held United States based RPC provider, to query various onchain data;
* 0x, a privately held United States based exchange API provider, to get swap quotes and route trades efficiently;
* the Pinto Subgraph Proxy, hosted on Digital Ocean, a public United States based cloud provider, to route traffic between multiple different subgraphs; and
* the Pinto Subgraphs, hosted on Alchemy and the Graph Network.

Any of these companies could censor access to data or a technical disruption could prevent access altogether.

#### **19. REGULATORY INTEREST IN STABLECOINS AND DECENTRALIZED FINANCE WILL RESULT IN NEW INDUSTRY REGULATIONS. THE IMPACT OF FUTURE REGULATIONS ON PINTO IS UNCERTAIN.** <a href="#regulatory-risk" id="regulatory-risk"></a>

In alignment with the ethos of DeFi, Pinto has been designed to be permissionless and censorship resistant, without the requirement for any trust-providing intermediary.

It is unclear what regulations, if any, governments will attempt to impose on DeFi. Therefore, it is impossible to predict how any new government regulations of DeFi will affect Pinto, or any of the protocols or networks Pinto relies on as part of its ecosystem.[\
](https://docs.bean.money/almanac)
