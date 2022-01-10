---
description: 'Todo: Add content manager contract description here.'
---

# Content Manager

> <mark style="color:blue;">**FUNCTIONS**</mark>
>
> content()
>
> contentStorage()
>
> accessControlManager()
>
> addAssetBatch(\_assets)
>
> registerOperators(\_operators)
>
> setHiddenUriBatch(\_assets)
>
> setPublicUriBatch(\_assets)
>
> setContractRoyalty(\_receiver_,_ \_rate)
>
> setTokenRoyaltiesBatch(\_assets)

| addAssetBatch(LibAsset.CreateData\[] \_asset)                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Adds a batch of tokens and sets their supply and uri information.                                                                                 |
| `_asset` is an array of CreateData structure objects. See [LibAsset.sol](https://docs.rawrshak.io/developers/smart-contracts/libraries/libasset). |
| Emits an `AssetsAdded` event.                                                                                                                     |
| visibility: external                                                                                                                              |
| state mutability:                                                                                                                                 |

| registerOperators(LibAsset.SystemApprovalPair\[] \_operators)                                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Updates the wallet's contract access roles.                                                                                                               |
| `_asset` is an array of SystemApprovalPair structure objects. See [LibAsset.sol](https://docs.rawrshak.io/developers/smart-contracts/libraries/libasset). |
| visibility: public                                                                                                                                        |
| state mutability:                                                                                                                                         |

| setHiddenUriBatch(LibAsset.AssetUri\[] \_assets)                                                                                                |
| ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Adds a new version of private uri to a batch of tokens.                                                                                         |
| `_asset` is an array of AssetUri structure objects. See [LibAsset.sol](https://docs.rawrshak.io/developers/smart-contracts/libraries/libasset). |
| Passes through [ContentStorage.sol](https://docs.rawrshak.io/developers/smart-contracts/content-contracts/content-storage).                     |
| visibility: external                                                                                                                            |
| state mutability:                                                                                                                               |

| setPublicUriBatch(LibAsset.AssetUri\[] \_assets)                                                                                                |
| ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Adds a new version of public uri to a batch of tokens.                                                                                          |
| `_asset` is an array of AssetUri structure objects. See [LibAsset.sol](https://docs.rawrshak.io/developers/smart-contracts/libraries/libasset). |
| Passes through [ContentStorage.sol](https://docs.rawrshak.io/developers/smart-contracts/content-contracts/content-storage).                     |
| visibility: external                                                                                                                            |
| state mutability:                                                                                                                               |

| setContractRoyalty(address \_receiver, uint24 \_rate)                                                                       |
| --------------------------------------------------------------------------------------------------------------------------- |
| Sets `_receiver` as the default royalty receiver and `_rate` as the default token royalty.                                  |
| Passes through [ContentStorage.sol](https://docs.rawrshak.io/developers/smart-contracts/content-contracts/content-storage). |
| visibility: external                                                                                                        |
| state mutability:                                                                                                           |

| setTokenRoyaltiesBatch(LibAsset.AssetRoyalties\[] \_assets)                                                                                           |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Sets new token royalty information to a batch of tokens.                                                                                              |
| `_asset` is an array of AssetRoyalties structure objects. See [LibAsset.sol](https://docs.rawrshak.io/developers/smart-contracts/libraries/libasset). |
| Passes through [ContentStorage.sol](https://docs.rawrshak.io/developers/smart-contracts/content-contracts/content-storage).                           |
| visibility: external                                                                                                                                  |
| state mutability:                                                                                                                                     |

