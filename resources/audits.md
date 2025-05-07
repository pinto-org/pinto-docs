# Audits



<figure><img src="../.gitbook/assets/Group 2.png" alt=""><figcaption></figcaption></figure>

To date, the Pinto ecosystem and its predecessor Beanstalk have undergone 20 audits. These audits include both full-protocol and audits of specific features. Additionally, the Pinto ecosystem is secured by a 1,200,000 Pinto bug bounty program through Immunefi.

{% embed url="https://immunefi.com/bug-bounty/pinto/" %}

## Inherited Security

Pinto was forked from Beanstalk after BIP-50 was deployed. From this, Pinto inherits the audits and security efforts of Beanstalk on the vast majority of the protocol code. Detailed information about the audit history of Beanstalk can be found at the link below.

{% embed url="https://docs.bean.money/almanac/protocol/audits" %}

## Improvements Beyond Beanstalk

Pinto implemented minor changes on top of Beanstalk, as well as several incremental upgrades since launch:

* [PI-0: Update Pump Parameters](https://github.com/pinto-org/protocol/pull/1) (November 19, 2024)
* [PI-1: Convert Newly Earned Pinto and Misc. Bug Fixes](https://github.com/pinto-org/protocol/pull/2) (November 26, 2024)
* [PI-2: Remove Anti Lambda to Lambda Convert](https://github.com/pinto-org/protocol/pull/3) (November 27, 2024)
* [PI-3: Bug Fixes and Parameter Changes](https://github.com/pinto-org/protocol/pull/4) (December 4, 2024)
* [PI-4: Demand for Soil Adjustments](https://github.com/pinto-org/protocol/pull/5) (December 8, 2024)
* [PI-5: Soil Issuance and Parameter Changes](https://github.com/pinto-org/protocol/pull/7) (January 2, 2025)
* [PI-6: Soil Issuance Below Value Target and Crop Ratio Changes](https://github.com/pinto-org/protocol/pull/8) (March 12, 2025)
* [PI-7: Convert Down Penalty](https://github.com/pinto-org/protocol/pull/33) (March 25, 2025)
* [PI-8: Misc. Efficiency Improvements](https://github.com/pinto-org/protocol/pull/54) (April 17, 2025)
* [PI-9: Helper Function Bug Fix](https://github.com/pinto-org/protocol/pull/77) (April 18, 2025)

Helper functions added in PI-8 were audited by [Egis](https://www.egissec.com/) (report [here](https://arweave.net/W7cfGzLVsTAEb65AR4wYfFLOl5Nm3EMy0Sg3Dk7C7e0)).

[Cantina](https://cantina.xyz/welcome) has audited all PIs since deployment (report coming soon).

***

[sPinto](../spinto/) is an extension of Pinto built entirely external to the protocol contracts. sPinto was audited by both Egis and Cantina before launch. The audit reports can be referenced [here](https://github.com/Egis-Security/audits/blob/main/reports/SiloedPinto.pdf) and [here](https://cantina.xyz/portfolio/c7410678-05f5-4dc3-bdbd-976d11738bcd).
