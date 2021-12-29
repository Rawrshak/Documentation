# Exchange Subgraph

The Exchange Subgraph contains indexed information about exchange, exchange volumes, asset volumes, the orders, developer royalties, etc.

### Exchange Optimistic Kovan GraphiQL&#x20;

{% embed url="https://thegraph.com/hosted-service/subgraph/gcbsumid/exchange-optimistic-kovan" %}
Try querying the Exchange Subgraph!
{% endembed %}

### Schemas

#### Entities

<details>

<summary>Exchange</summary>

```
type Exchange @entity {
  id: ID!
  orders: [Order!]!
  numOfOrders: BigInt!
  numOfBuyOrders: BigInt!
  numOfSellOrders: BigInt!
}
```

</details>

<details>

<summary>Token Escrow</summary>

```
type TokenEscrow @entity {
  id: ID!
  supportedTokens: [Token!]
}
```

</details>

<details>

<summary>Token</summary>

```
type Token @entity {
  id: ID!
  address: Bytes!
  escrow: TokenEscrow!
  totalVolume: BigInt!
  dailyData: [TokenDayData!]
}
```

</details>

<details>

<summary>Account</summary>

```
type Account @entity {
  id: ID!
  address: Bytes!
  orders: [Order!]!
  numOfOpenBuyOrders: BigInt!
  numOfOpenSellOrders: BigInt!
  numOfFilledOrders: BigInt!
  numOfCancelledOrders: BigInt!
  volume: BigInt!
  volumeAsBuyer: BigInt!
  volumeAsSeller: BigInt!
  dailyData: [AccountDayData!]
  claimedRoyalties: [UserRoyalty!]
}
```

</details>

<details>

<summary>User Royalty</summary>

```
type UserRoyalty @entity {
  id: ID!
  user: Account!
  token: Token!
  claimedAmount: BigInt!
}
```

</details>

<details>

<summary>Order</summary>

```
type Order @entity {
  id: ID!
  exchange: Exchange!
  asset: Asset!
  owner: Account!
  type: OrderType!
  price: BigInt!
  amountOrdered: BigInt!
  amountFilled: BigInt!
  status: OrderStatus!
  createdAtTimestamp: BigInt!
  filledAtTimestamp: BigInt!
  cancelledAtTimestamp: BigInt!
  lastClaimedAtTimestamp: BigInt!
  orderFills: [OrderFill!]
}
```

</details>

<details>

<summary>Order Fill</summary>

```
type OrderFill @entity {
  id: ID!
  filler: Account!
  order: Order!
  amount: BigInt!
  pricePerItem: BigInt!
  totalPrice: BigInt!
  token: Token!
}
```

</details>

<details>

<summary>Asset</summary>

```
type Asset @entity {
  id: ID!
  tokenId: BigInt!
  parentContract: Bytes!
  orders: [Order!] @derivedFrom(field: "asset")
  assetVolumeTransacted: BigInt!
}
```

</details>

<details>

<summary>Token Day Data</summary>

```
type TokenDayData @entity {
  id: ID!
  token: Token!
  volume: BigInt!
  startTimestamp: Int!
}
```

</details>

<details>

<summary>Account Day Data</summary>

```
type AccountDayData @entity {
  id: ID!
  account: Account!
  token: Token!
  volume: BigInt!
  volumeAsBuyer: BigInt!
  volumeAsSeller: BigInt!
  startTimestamp: Int!
}
```

</details>

#### Enums

<details>

<summary>Order Type</summary>

```
enum OrderType {
    Buy
    Sell
}
```

</details>

<details>

<summary>Order Status</summary>

```
enum OrderStatus {
  Ready
  PartiallyFilled
  Filled
  Cancelled
  Claimed
}
```

</details>
