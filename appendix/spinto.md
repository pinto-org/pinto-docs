# sPinto

Siloed Pinto (sPINTO) is a fungible Pinto Deposit wrapper that captures Silo yield. It leverages the ERC-20 and [ERC-4626](https://erc4626.info/) standards to achieve composability in the DeFi ecosystem and provide utility for Pinto outside of the core protocol.

sPinto also significantly lowers the barrier to participation in the protocol as users are able to accrue value in the Silo without manually managing their positions.

### How it works

Users can wrap Pinto or Pinto Deposits into sPinto [here](https://pinto.money/wrap). The Deposits within sPinto earn yield over time, via Stalk and Pinto seignorage. The wrapping user will receive an amount of sPinto that represents the amount of Pinto that they have contributed relative to the amount of Pinto held by sPinto at the time of wrap.

When a user unwraps, they will receive a portion of the Pinto Deposits held by sPinto, determined as the ratio of amount of sPinto being unwrapped relative to total sPinto supply. When unwrapping, users are guaranteed to receive at least as many Pinto Deposits as they put in, making sPinto a non-rebasing, up-only token in Pinto terms.

Users can wrap and unwrap Pinto to and from sPinto anytime, with a minimum of 1 Pinto required for wrapping.

The pool of Deposits in sPinto follows a LIFO (Last In First Out) model in Grown Stalk terms—i.e., Deposits with the least Grown Stalk are withdrawn first when unwrapping sPinto.

Note that Stalk is socialized among sPinto holders and not returned in equal proportion when unwrapping. Therefore, users wrapping sPinto directly from Silo Deposits should be wary of the Stalk cost of using older Deposits.

Mowing and Planting is performed through a claim operation that can be called directly and is called on every wrap and unwrap. Every time sPinto claims Earned Pinto, those rewards are linearly vested to sPinto holders over the course of 4 hours.

### Flood Reward Handling

When a Flood occurs, the sPinto contract claims rewards in the form of non-Pinto assets. Upon each claim, sPinto checks the Pinto price in every whitelisted Well and swaps up to 10% of each non-Pinto asset into Pinto. The swap trigger price is capped at $1.01 and must be within a manipulation resistant range.

### Upgradability

sPinto is an upgradable contract, owned by the PCM.

### Security

sPinto is being added to the Pinto bug bounty program on [Immunefi](https://immunefi.com/bug-bounty/pinto/information/) - bounty hunters are encouraged to submit bug reports regarding sPinto even before it’s formally added to the program. sPinto has been audited by Cantina and EgisSec. You can read the full audit reports here:

* [https://github.com/Egis-Security/audits/blob/main/reports/SiloedPinto.pdf](https://github.com/Egis-Security/audits/blob/main/reports/SiloedPinto.pdf)
* [https://cantina.xyz/portfolio/c7410678-05f5-4dc3-bdbd-976d11738bcd](https://cantina.xyz/portfolio/c7410678-05f5-4dc3-bdbd-976d11738bcd)

### Contracts

| Contract Name         | Address                                                                                                               |
| --------------------- | --------------------------------------------------------------------------------------------------------------------- |
| sPinto Token          | [0x00b174d66adA7d63789087F50A9b9e0e48446dc1](https://basescan.org/address/0x00b174d66adA7d63789087F50A9b9e0e48446dc1) |
| sPinto Admin          | [0x71C596E55CaE926cAaF8aa6b96Bec724923FC60D](https://basescan.org/address/0x71C596E55CaE926cAaF8aa6b96Bec724923FC60D) |
| sPinto Implementation | [0x162c9c2f956Cf171b0C1CAB3079CE6d8cC0a3fB5](https://basescan.org/address/0x162c9c2f956Cf171b0C1CAB3079CE6d8cC0a3fB5) |
