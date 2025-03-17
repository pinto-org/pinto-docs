# Upgradability

This document has been uploaded to Arweave [here](https://arweave.net/AaSqPd4AogBeP70DwUb3Y9v--gLCdOpj6hT8qe-fZ7Y).

***

### PCM

**The Pinto Contract Multisig (PCM)** is the owner of the Pinto contract. The PCM has the exclusive and unilateral ability to upgrade Pinto. It is expected that the PCM transfers ownership of Pinto to the null address, relinquishing these abilities from the PCM as soon as it is prudent to do so.

The PCM is deployed using [Safe](https://safe.global/), the most battle-tested multisig contract on Base. Its m-of-n configuration is 5-of-9. PCM Signers are an anonymous and diverse set of Pinto friends and contributors.

The PCM is address [0x2cf82605402912C6a79078a9BBfcCf061CbfD507](https://basescan.org/address/0x2cf82605402912C6a79078a9BBfcCf061CbfD507) on Base:

{% embed url="https://app.safe.global/transactions/queue?safe=base:0x2cf82605402912C6a79078a9BBfcCf061CbfD507" %}

### No Governance

Pinto does not have governance. While Pinto is the first Beanstalk fork, additional development must be completed in order to create a generalized fork system that replaces the need for contract upgrades. In the meantime, limited upgrades to Pinto may be implemented by the Pinto Contract Multisig (PCM), the owner of the Pinto contract.

**The PCM will only make changes to Pinto that:**

* Fix bugs or security vulnerabilities (including dewhitelisting an LP token for which the non-Pinto asset has collapsed);
* Change parameters until 2 weeks after the first time the Pinto supply reaches 500M (_e.g._, Target Seasons to Catch Up, Pod Rate and L2SR thresholds, Deposit Whitelist, optimal LP PDV distribution, etc.);
* Mint Pinto to fund a bug bounty program according to the schedule [outlined below](upgradability.md#bug-bounty-mint-schedule);
* Add a [Shipping Route](../farm/sun.md#shipping-routes) that pays back old Beanstalk holders after the Pinto supply reaches 1 billion ([see details here](old-beanstalk-holders.md)); or
* Implement a [Fork Migration System](upgradability.md#fork-migration-system).

### **Bug Bounty Mint Schedule**

The PCM will fund a bug bounty program by minting Pinto according to the following schedule:

* Mint 0 Pinto to fund a bug bounty program until the Pinto supply reaches 10M for the first time;
* Mint 500k Pinto to fund a bug bounty program once the supply reaches 10M for the first time;
* Mint Pinto to top up the bug bounty program to 2M Pinto once the supply reaches 25M for the first time;
* Mint Pinto to top up the bug bounty program to 3M Pinto once the supply reaches 50M for the first time;
* Mint Pinto to top up the bug bounty program to 5M Pinto once the supply reaches 100M for the first time;
* Mint Pinto to top up the bug bounty program to 10M Pinto once the supply reaches 250M for the first time;
* Mint Pinto to top up the bug bounty program to 20M Pinto once the supply reaches 500M for the first time; and
* Mint Pinto to top up the bug bounty program to 30M Pinto once the supply reaches 1B for the first time.

The details of the bug bounty program are at the discretion of the PCM. The PCM has the ability to select a separate committee to operate the bug bounty program on its behalf.

The Pinto Immunefi Committee Multisig (PICM) that custodies the Pinto for bug bounties is address [0xA8d8BD1745bA40D8B673f690c26BeB9440372b8f](https://basescan.org/address/0xA8d8BD1745bA40D8B673f690c26BeB9440372b8f?__cf_chl_tk=3FQQwh3N6Ak_fWpNN4WVSieEEGi71OoHdiGAdXAtlKI-1734812745-1.0.1.1-YqRF.sGFA9gCyDmoVfq36wjGWHGHtT2QUUjkvrRHw7M) on Base:

{% embed url="https://app.safe.global/transactions/queue?safe=base:0xA8d8BD1745bA40D8B673f690c26BeB9440372b8f" %}

### **Fork Migration System**

#### **Summary**

Implement a Fork Migration System that allows Farmers to migrate assets from one or more Pinto deployments (Source Pinto) to another (a Destination Pinto) under conditions defined by the Destination Pinto.

#### **Context**

Forks and upgrades both allow protocols to be modified:

* Upgrades: Occurs when there is some native mechanism in the software that allows the rules of the existing instantiation of the system to be changed. As there is still only 1 instance of the system, participants are forced into the upgrade.
* Forks: Occurs when a set of participants decide to change the rules of the protocol such that a new instance of the system is created. Each participant has the option to keep using the old system or switch to the new one.

Forks give participants complete agency while upgrades minimize fragmentation.

A powerful property of governance in networks like Bitcoin and Ethereum is that there is a guarantee that the rules of the system will not change without participants opting into the changes. Bitcoin miners who did not update their software to Bitcoin Cash remained on Bitcoin. Ethereum nodes that did not update their software to facilitate the fork that reorganized Ethereum post-DAO hack remained on ETH Classic. When juxtaposed against smart contract upgrades, where the rules can be changed for participants who did not opt into it, social consensus seems preferable for a base money.

Furthermore, because smart contracts do not have a strong relationship with network validators, it is harder for smart contracts to coordinate a reorganization via social consensus in the instance of a flaw (e.g., Ethereum did not reorganize post-2022 Beanstalk exploit). Therefore, even though there is friction in the form of lost network effects, it seems the optimal governance model for smart contracts is to make them non-upgradable and to make migrating to future implementations (or forks) as frictionless as possible such that there can be a Lindy effect around safe implementations to use without slowing down innovation.

While this solution likely creates more overhead for developers to support backward compatibility, it also provides more similar properties for users of smart contracts as it does for users of systems based on social consensus.

#### Problem

_Counting Votes_

It is unclear how to count votes in the fairest way possible. Because of the ability to use infinite addresses, without a unique identity system there is no way to ensure that each participant only votes once.

Therefore, the only viable option for voting in smart contract-based governance for contracts with value stored in them is for the weights in participation in governance to be value-based in some capacity (e.g., the Stalk System). While the Stalk System is designed to dampen the effect of participants with more value in the system, it's imperfect with respect to ownership concentration.

There do not seem to be constructions of on-chain voting systems that are battle-tested with significant value in them, and the primary problem with a DAO-based system is that it allows the majority to force changes (or a lack of changes) on the minority.

_Forks_

As is stands, there is significant friction involved in migrating assets from one Pinto deployment to another version of Pinto. Without a standard interface and system for migrations between forks, any Destination Pinto that would like to accept migrations would have to implement a bespoke solution based on approving the Destination Pinto to spend Farmer's Source Pinto assets.

#### Solution

The Fork Migration System allows Farmers to migrate assets from one or more Source Pinto to a Destination Pinto under conditions defined by the Destination Pinto.
