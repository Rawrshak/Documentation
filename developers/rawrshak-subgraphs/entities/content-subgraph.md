# Content Subgraph

The Content Subgraph contains indexed information about content contracts, the assets, and users.

### Contents Optimistic Kovan GraphiQL&#x20;

{% embed url="https://thegraph.com/hosted-service/subgraph/gcbsumid/contents-optimistic-kovan" %}
Try querying the Content Subgraph!
{% endembed %}

### Schemas

#### Entities

<details>

<summary>Content Contract</summary>

```
type Content @entity {
  id: ID!
  factory: ContentFactory!
  manager: ContentManager!
  contractAddress: Bytes!
  contractUri: String!
  assets: [Asset!]!
  assetsCount: BigInt!
  royaltyReceiver: Account!
  royaltyRate: Int!
  minters: [Minter!]
  mintersCount: Int!
  name: String
  game: String
  creator: String
  creatorAddress: String
  owner: Account!
  tags: [Tag!]!
  tagsCount: Int!
}
```

</details>

<details>

<summary>Asset</summary>

```
type Asset @entity{
  id: ID!
  tokenId: BigInt!
  parentContract: Content!
  currentSupply: BigInt!
  maxSupply: BigInt!
  balances: [AssetBalance!]
  ownersCount: BigInt!
  royaltyReceiver: Account
  royaltyRate: Int!
  latestHiddenUriVersion: BigInt!
  latestPublicUriVersion: BigInt!
  latestPublicUri: String
  transactions: [Transaction!]!
  transactionsCount: BigInt!
  mintCount: BigInt!
  burnCount: BigInt!
  name: String
  type: String
  subtype: String
  tags: [Tag!]!
  tagsCount: Int!
  imageUri: String
}
```

</details>

<details>

<summary>Asset Balance</summary>

```
type AssetBalance @entity {
  id: ID!
  asset: Asset!
  owner: Account!
  amount: BigInt!
  parentContract: Content!
  type: String
  subtype: String
}
```

</details>

<details>

<summary>Tag</summary>

```
type Tag @entity {
  id: ID!
  contents: [Content!]
  assets: [Asset!]
}
```

</details>

<details>

<summary>Account</summary>

```
type Account @entity {
  id: ID!
  address: Bytes!
  assetBalances: [AssetBalance!]!
  transactions: [Transaction!]!
  transactionsCount: BigInt!
  transactionsAsOperator: [Transaction!]!
  transactionsAsOperatorCount: BigInt!
  mintCount: BigInt!
  burnCount: BigInt!
  uniqueAssetCount: BigInt!
  approvals: [Approval!]
  minters: [Minter!] 
  contentManagers: [ContentManager!]
  contents: [Content!]
}
```

</details>

<details>

<summary>Transaction</summary>

```
type Transaction @entity {
  id: ID!
  operator: Account!
  user: Account!
  transactionType: TransactionType!
  assets: [Asset!]! 
  assetAmounts: [TransactionAssetAmount!]!
  blockNumber: BigInt!
  timestamp: BigInt!
  gasUsed: BigInt!
  gasPrice: BigInt!
}
```

</details>

<details>

<summary>Transaction Asset Amount</summary>

```
type TransactionAssetAmount @entity {
  id: ID!
  asset: Asset!
  amount: BigInt!
}
```

</details>

<details>

<summary>Approval</summary>

```
type Approval @entity {
  id: ID!
  content: Content!
  operator: Account!
  user: Account!
}
```

</details>

<details>

<summary>Minter</summary>

```
type Minter @entity {
  id: ID!
  content: Content!
  operator: Account!
}
```

</details>

#### Enums

<details>

<summary>Transaction Type</summary>

```
enum TransactionType {
  Mint
  Burn
}
```

</details>
