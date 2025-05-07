# Pod Market

The Pod Market is a peer-to-peer marketplace that allows [Pods](../field.md#pods) to be bought and sold in a trustless fashion without trading fees. The Pod Market creates liquidity for Pods through an onchain order book.

Sellers can list Pods or fill open Pod Orders placed by buyers.

Buyers can order Pods or fill open Pod Listings placed by sellers.

### **Pod Listings** <a href="#pod-listings" id="pod-listings"></a>

Pods from Pinto Sown in a single transaction form a Plot. Anyone with a Plot can list a whole or partial Plot for sale in exchange for Pinto. This is known as a Pod Listing. Pod Listings have the following inputs:

| Pod Listing Inputs       | Example                          |
| ------------------------ | -------------------------------- |
| Plot                     | Place in Line: 140M, Pods: 4,000 |
| Position within the Plot | 2,000 to 4,000                   |
| Price per Pod            | 0.80 Pinto                       |
| Expiration               | 30M Pods                         |

#### _Plot_

Farmers may own multiple Plots. Plots are identified by their place in the Pod Line.

#### _Position within the Plot_

As Pods are Harvested on a First In, First Out (FIFO) basis, if less than a whole Plot is listed, the seller must choose which Pods within the Plot to list. A seller can list any contiguous set of Pods within a Plot. If only a portion of a Plot is listed, the seller must choose which subset of Pods within that Plot are for sale. In the example above, the last 2,000 Pinto in the Plot are Listed, while the first 2,000 (i.e. Pods 0 thru 2,000) remain in the seller’s possession.

#### _Price per Pod_

The sale price of each Pod, denominated in Pinto.

#### _Expiration_

The number of Pods that can Harvest before the expiration of the Pod Listing. Setting this input to 30M Pods would remove this Pod Listing from the Pod Market once 30M Pods are Harvested after the creation of the Pod Listing.

A Pod Listing can be cancelled at any time until it is entirely filled. Plots can only be listed in a single Pod Listing at a time. Pod Listings are automatically cancelled if the owner of the Plot transfers or re-lists any Pods in the Plot.

A Pod Listing can be entirely or partially filled at any time by a buyer. If the Pod Listing is partially filled, the rest of the Pod Listing remains listed.

### **Pod Orders** <a href="#pod-orders" id="pod-orders"></a>

A Pod Order is an offer to buy Pods at a given price, before a given place in the Pod Line. Any seller may fill a Pod Order by selling Pods according to the terms of the Pod Order.

Anyone with Pinto can Order Pods by creating a Pod Order. Pod Orders have the following inputs:

| Pod Order Inputs                       | Example    |
| -------------------------------------- | ---------- |
| Maximum number of Pods to be purchased | 4,000 Pods |
| Price per Pod                          | 0.80 Pinto |
| Maximum place in the Pod Line          | 140M       |

#### _Maximum number of Pods to be purchased_

Because Pod Orders can be partially or entirely filled at any time by a seller, a Pod Order defines the maximum number of Pods the buyer would like to purchase at a given price.

#### _Price per Pod_

The price to be paid for each Pod, denominated in Pinto.

#### _Maximum place in the Pod Line_

A Pod Order with a maximum place in the Pod Line of 140M could be filled by any Pods with a position in the Pod Line of 140M or earlier. In general, Pods closer to the front of the Pod Line are more valuable, as they become Harvestable for Pinto sooner due to the FIFO Harvest schedule.

A Pod Order can be cancelled at any time until it is filled. To facilitate instant clearance, Pinto are locked in a Pod Order until it is entirely filled or cancelled. If the Pod Order is partially filled, the rest of the Pod Order remains listed.
