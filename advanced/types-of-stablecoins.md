# Types of Stablecoins

The three axes in [the previous section](stablecoin-overview.md) (value source, convertibility and network nativity) present a classification of 8 potential stablecoin types, some of which currently lack successful implementations:

* [Non-network-native exogenous value convertible stablecoin protocols](types-of-stablecoins.md#non-network-native-exogenous-value-convertible-stablecoin-protocols)
  * _Examples: USD Coin, Tether, BinanceUSD_
* [Network-native exogenous value convertible stablecoin protocols](types-of-stablecoins.md#network-native-exogenous-value-convertible-stablecoin-protocols)
  * _Examples: WETH, Liquity, MakerDAO, Abracadabra_
* [Non-network-native exogenous value non-convertible stablecoin protocols](types-of-stablecoins.md#non-network-native-exogenous-value-non-convertible-stablecoin-protocols)
  * _Examples: N/A_
* [Network-native exogenous value non-convertible stablecoin protocols](types-of-stablecoins.md#network-native-exogenous-value-non-convertible-stablecoin-protocols)
  * _Examples: Olympus_
* [Non-network-native endogenous value convertible stablecoin protocols](types-of-stablecoins.md#non-network-native-endogenous-value-convertible-stablecoin-protocols)
  * _Examples: N/A_
* [Network-native endogenous value convertible stablecoin protocols](types-of-stablecoins.md#network-native-endogenous-value-convertible-stablecoin-protocols)
  * _Examples: Terra_
* [Non-network-native endogenous value non-convertible stablecoin protocols](types-of-stablecoins.md#non-network-native-endogenous-value-non-convertible-stablecoin-protocols)
  * _Examples: US Dollars_
* [Network-native endogenous value non-convertible stablecoin protocols](types-of-stablecoins.md#network-native-endogenous-value-non-convertible-stablecoin-protocols)
  * _Examples: Pinto, Beanstalk, Ampleforth_

Additionally, implementations of exogenous value convertible stablecoin protocols with fractional reserves are considered:

* [Non-network-native exogenous value fractional reserve convertible stablecoin protocols](types-of-stablecoins.md#non-network-native-exogenous-value-fractional-reserve-convertible-stablecoin-protocols)
  * _Examples: Bank Notes_
* [Network-native exogenous value fractional reserve convertible stablecoin protocols](types-of-stablecoins.md#network-native-exogenous-value-fractional-reserve-convertible-stablecoin-protocols)
  * _Examples: Frax_

### Exogenous Value Stablecoins <a href="#exogenous-value-stablecoins" id="exogenous-value-stablecoins"></a>

#### **Non-network-native exogenous value convertible stablecoin protocols**

_Examples:_ [_USD Coin_](https://www.circle.com/en/usdc)_,_ [_Tether_](https://tether.to/en/)_,_ [_BinanceUSD_](https://www.binance.com/en/busd)

Non-network-native exogenous value convertible stablecoin protocols issue tokens that are supposedly collateralized by, and require a custodian that facilitates the convertibility to, non-network-native exogenous value worth at least 100% of total outstanding protocol liabilities. These protocols function as low-volatility permissioned bridges between their respective networks and the rest of the world.

Users of non-network-native exogenous value convertible stablecoins sacrifice trustlessness and carry: third parties custody the non-network-native assets, can freeze the network-native assets unilaterally and can retain yield earned on collateral. The absence of protocol-native opportunities for carry limits liquidity.

_Trustlessness:_ Permissioned

_Carrying Costs:_ Non-competitive as compared to the asset being pegged to, but best among exogenous value convertible stablecoins

_Volatility:_ Best among exogenous value stablecoins, but frictions around convertibility remain significant, leading to imperfect peg maintenance

_Liquidity:_ Best among exogenous value stablecoins, but limited by opportunity cost of using off-chain collateral as capital

#### **Network-native exogenous value convertible stablecoin protocols**

_Examples:_ [_WETH_](https://coinmarketcap.com/academy/article/what-is-wrapped-ethereum-weth)_,_ [_Liquity_](https://www.liquity.org/)_,_ [_MakerDAO_](https://makerdao.com/)_,_ [_Abracadabra_](https://abracadabra.money/)

Network-native exogenous value convertible stablecoin protocols use excess network-native collateral to remove most points of centralization. Overcollateralization removes most risk associated with the volatility of the collateral but by necessity requires the introduction of rent payments in order to prevent the value of the stablecoin from trending towards the value of the underlying collateral. The combination of collateral requirements and rent payments significantly limits the potential liquidity of these stablecoins.

[Liquity](https://www.liquity.org/) is an ideal simple iteration of this type of stablecoin protocol, without any points of centralization and with protocol-native positive carry (via [the Stability Pool](https://docs.liquity.org/faq/stability-pool-and-liquidations)). In order to remove rent payments, Liquity does not target an exact price for its stablecoin, LUSD. The potential supply of LUSD is limited by the value of trustless network-native value.

_Trustlessness:_ Can be totally permissionless; collateral distribution is the primary determinant of trustlessness

_Carrying Costs:_ Non-competitive as compared to the asset being pegged to, unless at the expense of volatility

_Volatility:_ Very low volatility when factoring in frictions around convertibility, unless in order to improve the competitivity of carrying costs

_Liquidity:_ Limited by available network-native collateral, particularly trustless network-native collateral

#### **Non-network-native exogenous value non-convertible stablecoin protocols**

_Examples: N/A_

Convertibility is the main source of low price volatility and confidence in the custodian. Therefore, it is unlikely that a non-network-native exogenous value non-convertible stablecoin protocol will find product market fit.

_Trustlessness:_ Permissioned

_Carrying Costs:_ Non-competitive as compared to the asset being pegged to

_Volatility:_ Speculation on the trustworthiness of the custodian of collateral will be higher due to the lack of convertibility, which should lead to more price volatility

_Liquidity:_ Limited by opportunity cost of using off-chain collateral as capital, but less so because the custodian is unencumbered by the limited asset allocations necessary to facilitate convertibility

#### **Network-native exogenous value non-convertible stablecoin protocols**

_Examples:_ [_Olympus_](https://www.olympusdao.finance/) _(convertible under certain market conditions)_

Convertibility is the main source of low price volatility. The main benefit of collateralization is low price volatility, the majority of which is forfeited in the absence of convertibility. Therefore, it is unlikely that a network-native exogenous value non-convertible stablecoin protocol will find product market fit.

_Trustlessness:_ Can be totally permissionless; collateral distribution is the primary determinant of trustlessness

_Carrying Costs:_ Non-competitive as compared to the asset being pegged to, but potentially better than network-native exogenous value convertible stablecoin protocols because of the ability to take more risk with the underlying collateral at the cost of volatility

_Volatility:_ There exists some tradeoff between carrying costs and volatility, dependent on protocol design

_Liquidity:_ Limited by available network-native collateral, particularly trustless network-native collateral

#### **Non-network-native exogenous value fractional reserve convertible stablecoin protocols**

_Examples: Bank Notes (not implemented on any decentralized networks to date)_

Credit-based non-network-native exogenous value convertible stablecoin protocols most closely resemble traditional bank notes. The introduction of fractional reserves to create competitive carrying costs is a well documented historical phenomenon. The lending out of collateral creates yield that can be passed onto the users of the fractional reserve notes. However, the combination of convertibility and fractional reserves creates an asset liability duration mismatch that can lead to complete collapse. Fractional reserves are another example of currencies trading volatility for carry.

_Trustlessness:_ Permissioned

_Carrying Costs:_ Competitive as compared to the asset being pegged to, at the expense of tail risk in volatility

_Volatility:_ Low volatility when factoring in frictions around convertibility; exposure to bank runs

_Liquidity:_ Limited by available collateral

#### **Network-native exogenous value fractional reserve convertible stablecoin protocols**

_Examples:_ [_Frax_](https://frax.finance/)

The use of fractional reserves by network-native exogenous value convertible stablecoin protocols has been used in an attempt to help remediate the negative effect on carrying costs of collateral requirements. However, the network-native nature of the system makes lowering the collateralization ratio difficult without spurring a bank run. While fractional reserve implementations of network-native exogenous value convertible stablecoins offer competitive carrying costs as compared to non-fractional reserve implementations, they do so at the cost of tail risk in volatility.

_Trustlessness:_ Can be totally permissionless; collateral distribution is the primary determinant of trustlessness

_Carrying Costs:_ Can be competitive as compared to the asset being pegged to at lower collateralization ratios

_Volatility:_ Low volatility when factoring in frictions around convertibility; exposure to bank runs

_Liquidity:_ Limited by available network-native collateral, particularly trustless network-native collateral

#### **Summary**

Convertibility to exogenous value is the primary source of low price volatility, but it comes at the cost of competitive carrying costs and liquidity. In most implementations, trustlessness is sacrificed for deeper liquidity.

Despite the shortcomings of exogenous value convertible stablecoin implementations, demand for their USD implementations continues to [increase rapidly](https://defillama.com/stablecoins).

However, despite this rapid increase in supply, the [borrowing rates on exogenous value convertible USD stablecoins](https://app.aave.com/markets/) have historically been higher than [borrowing rates on USD](https://www.newyorkfed.org/markets/reference-rates/effr). Non-competitive carrying costs are structural due to the opportunity costs associated with requirements of exogenous value collateral. Attempts to improve carrying costs through the introduction of fractional reserves have failed to do so.

Businesses built on trustless primitives cannot compete with businesses built on centralized systems due to non-competitive carrying costs on low-volatility network-native trustless assets.

### Endogenous Value Stablecoins <a href="#endogenous-value-stablecoins" id="endogenous-value-stablecoins"></a>

#### **Non-network-native endogenous value convertible stablecoin protocols**

_Examples: N/A_

It is difficult for network-native protocols to create and facilitate the conversion to non-network-native value. Therefore, it is unlikely that non-network-native endogenous value convertible stablecoin protocols find product market fit.

In theory, this would be like a private company issuing a stablecoin that is convertible to company stock at market price.

_Trustlessness:_ Permissioned

_Carrying Costs:_ Can be competitive as compared to the asset being pegged to, but the issuer must create more than enough endogenous value to facilitate the carry

_Volatility:_ Likely to maintain a tight peg due to convertibility, but exposed to collapse in the instance the issuer’s endogenous value source falters, or is expected to falter

_Liquidity:_ Limited by the endogenous value of the issuer

#### **Network-native endogenous value convertible stablecoin protocols**

_Examples:_ [_Terra_](https://www.allcryptowhitepapers.com/terra-whitepaper/)

To date, implementations of network-native endogenous value convertible stablecoin protocols have failed to regularly cross their stablecoin price over their value peg. This is primarily due to the fluctuation in value of endogenous value. The convertibility to endogenous value typically correlates with decreases in endogenous value, which creates excess reflexivity. It is unclear whether network-native endogenous value convertible stablecoin protocols can succeed.

_Trustlessness:_ Permissionless

_Carrying Costs:_ Can be competitive as compared to the asset being pegged to, but the issuer must create more than enough endogenous value to facilitate the carry

_Volatility:_ Likely to maintain a tight peg due to convertibility, but exposed to collapse in the instance the issuer’s endogenous value source falters, or is expected to falter

_Liquidity:_ Limited by the endogenous value of the issuer

#### **Non-network-native endogenous value non-convertible stablecoin protocols**

_Examples: US Dollars_

The current financial system (_i.e._, fiat money) can be thought of as an implementation of credit-based non-network-native endogenous value non-convertible stablecoin protocols, where the fiat money is pegged to a time-weighted discount of its current purchasing power. The non-network-native nature of the credit of the issuer introduces significant sacrifices to trustlessness.

_Trustlessness:_ Permissioned

_Carrying Costs:_ Very competitive

_Volatility:_ Determined by a variety of factors; sufficiently low volatility is a prerequisite to adoption

_Liquidity:_ Limited by the creditworthiness of the issuer

#### **Network-native endogenous value non-convertible stablecoin protocols**

_Examples:_ [_Pinto_](https://pinto.money)_,_ [_Beanstalk_](http://bean.money/)_,_ [_Ampleforth_](https://www.ampleforth.org/)

Rebasing stablecoin protocols (_e.g._, [Ampleforth)](https://www.ampleforth.org/) have shown efficacy at crossing stablecoin prices over their value pegs, but without the regularity, low volatility or liquidity necessary to create utility. Extreme negative carrying costs during decreases in demand exacerbate difficulty of use.

The value of fiat currency is derived from its utility and the credit of its issuer. Utility of fiat currency is a function of trustlessness, carrying costs, stability and liquidity. Decentralized credit can be used to issue a permissionless fiat stablecoin with competitive carrying costs, low volatility and deep liquidity.

Credit-based network-native endogenous value non-convertible stablecoin protocols are network-native implementations of fiat currency. The value of such assets derive from the credit of its issuer, which exists in a network-native capacity. The network-native nature of the credit creates value in a trustless fashion. The creation of endogenous value through credit facilitates competitive carrying costs. A strong series of network-native incentives and diverse network of creditors can create price stability and deep liquidity without collateral requirements.

Credit-based network-native endogenous value non-convertible stablecoin protocols present an opportunity to achieve trustlessness, competitive carrying costs, low price volatility and deep liquidity. The use of network-native credit can eliminate the negative carrying costs and reduce the excess price volatility associated with rebasing stablecoin protocols.

#### **Summary**

Convertibility to endogenous value prioritizes low price volatility at the expense of long term sustainability.

Rebasing tokens have shown some efficacy and peg maintenance, but not enough to create utility. The introduction of network-native credit can reduce volatility.

The current financial system runs on credit-based non-network-native endogenous value non-convertible stablecoin protocols.

Implementations of network-native endogenous value non-convertible stablecoin protocols present a viable option for the creation of trustless currency with competitive carrying costs, low price volatility and deep liquidity that can facilitate the competition between businesses built on decentralized primitives against businesses built on centralized ones.
