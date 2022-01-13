# Unity SDK

The Rawrshak Unity SDK is an unity asset package that contains libraries that help the game developer integrate their game to blockchain technologies and the Rawrshak platform infrastructure. The Rawrshak Unity SDK has a dependency on ChainSafe's Gaming SDK and WalletConnect for Unity.&#x20;

### WalletConnect Integration and Wallet Management

The WalletConnect integration allows gamers to use their mobile wallets to interact with Unity games. It allows game developers to simply push transaction requests to the mobile wallet. The Wallet Management library enables the game developer to easily query and filter assets in a gamer's wallet.&#x20;

### Asset Minter

{% hint style="danger" %}
This is still under development and not yet included in the Unity SDK.
{% endhint %}

The Asset Minter library gives the game the ability to mint assets unlocked by the user and automatically sends it to the gamer's wallet.

### Asset Downloader

The Asset Downloader library gives the developer the ability to easily download metadata and assets from Arweave (or other decentralized storage) or IPFS. It also caches the asset for future use if necessary.

### Asset Loader

The Asset Loader library gives the developer the ability to easily load and instantiate an asset in a player's wallet. Once the asset has been downloaded, the asset loader can instantiate the asset and replace the placeholder asset.

### Subgraph Data Queries

The GraphQL library allows the developer to use the provided graphql queries in order to get more information about an asset that is not easily attainable from the blockchain queries. The Graph's infrastructure is used to index relationships between objects.&#x20;

The developer can also create their own queries if there is specific information in the subgraph that they need. They can create their own in-game dashboards using these custom queries.&#x20;

{% hint style="info" %}
Please refer to the [Rawrshak Subgraph ](../../rawrshak-subgraphs/entities/)pages for more information.
{% endhint %}
