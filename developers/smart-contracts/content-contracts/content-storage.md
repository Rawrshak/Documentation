---
description: 'Todo: Add content storage description here.'
---

# Content Storage

> <mark style="color:blue;">**EVENT**</mark>
>
> AssetsAdded(parent, tokenIds, assets)

| AssetsAdded(address parent, uint256\[] tokenIds, LibAsset.CreateData\[] assets)         |
| --------------------------------------------------------------------------------------- |
| Event emitted when <mark style="color:blue;">`addAssetBatch`</mark> function is called. |

> <mark style="color:blue;">**FUNCTIONS**</mark>
>
> assetCounter()
>
> supply(\_tokenId)
>
> maxSupply(\_tokenId)
>
> uri(\_tokenId, \_version)
>
> hiddenUri(\_tokenId, \_version)
>
> getContractRoyalty()
>
> getRoyalty(\_tokenId)
>
> getLatestUriVersion(\_tokenId, \_isPublic)
>
> updateSupply(\_tokenId_,_ \_supply)
>
> addAssetBatch(\_assets)
>
> setHiddenUriBatch(\_assets)
>
> setPublicUriBatch(\_assets)
>
> setContractRoyalty(\_receiver_,_ \_rate)
>
> setTokenRoyaltiesBatch(\_assets)

| assetCounter() -> uint256                                      |
| -------------------------------------------------------------- |
| Returns the total number of token types added to the contract. |

| maxSupply(uint256 \_tokenId) -> uint256                                           |
| --------------------------------------------------------------------------------- |
| Returns the maximum amount of token type `_tokenId` allowed to be in circulation. |
| visibility: external                                                              |
| state mutability: view                                                            |

| uri(uint256 \_tokenId, uint256 \_version) -> string                                 |
| ----------------------------------------------------------------------------------- |
| Returns the version of public uri of token type `_tokenId` specified by `_version`. |
| visibility: external                                                                |
| state mutability: view                                                              |

| hiddenUri(uint256 tokenId, uint256 version) -> string                                |
| ------------------------------------------------------------------------------------ |
| Returns the version of private uri of token type `_tokenId` specified by `_version`. |
| visibility: external                                                                 |
| state mutability: view                                                               |

| getContractRoyalty() -> address, uint24                                          |
| -------------------------------------------------------------------------------- |
| Returns the default royalty receiver address and rate for the contract's assets. |
| visibility: external                                                             |
| state mutability: view                                                           |

| getRoyalty(\_tokenId) -> address, uint24                                   |
| -------------------------------------------------------------------------- |
| Returns the royalty receiver and rate for the given token type `_tokenId`. |
| visibility: external                                                       |
| state mutability: view                                                     |

| getLatestUriVersion(uint256 \_tokenId, bool \_isPublic) -> string                            |
| -------------------------------------------------------------------------------------------- |
| Returns the latest public or private uri designated by `isPublic`, of token type `_tokenId`. |
| visibility: external                                                                         |
| state mutability: view                                                                       |

| updateSupply(uint256 \_tokenId, uint256 \_supply)               |
| --------------------------------------------------------------- |
| Updates the total supply of token type `_tokenId` by `_supply`. |
| visibility: external                                            |
| state mutability:                                               |

| addAssetBatch(LibAsset.CreateData\[] \_asset)                                                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Adds a batch of tokens and sets their supply and uri information.                                                                                         |
| `_asset` is an array of CreateData structure objects. See [LibAsset.sol](https://github.com/Rawrshak/Rawrshak/blob/main/contracts/libraries/LibAsset.sol) |
| Emits an `AssetsAdded` event.                                                                                                                             |
| visibility: external                                                                                                                                      |
| state mutability:                                                                                                                                         |

| setHiddenUriBatch(LibAsset.AssetUri\[] \_assets)                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Adds a new version of private uri to a batch of tokens.                                                                                                 |
| `_asset` is an array of AssetUri structure objects. See [LibAsset.sol](https://github.com/Rawrshak/Rawrshak/blob/main/contracts/libraries/LibAsset.sol) |
| visibility: external                                                                                                                                    |
| state mutability:                                                                                                                                       |

| setPublicUriBatch(LibAsset.AssetUri\[] \_assets)                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Adds a new version of public uri to a batch of tokens.                                                                                                  |
| `_asset` is an array of AssetUri structure objects. See [LibAsset.sol](https://github.com/Rawrshak/Rawrshak/blob/main/contracts/libraries/LibAsset.sol) |
| visibility: external                                                                                                                                    |
| state mutability:                                                                                                                                       |

| setContractRoyalty(address \_receiver, uint24 \_rate)                                      |
| ------------------------------------------------------------------------------------------ |
| Sets `_receiver` as the default royalty receiver and `_rate` as the default token royalty. |
| visibility: external                                                                       |
| state mutability:                                                                          |

| setTokenRoyaltiesBatch(LibAsset.AssetRoyalties\[] \_assets)                                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Sets new token royalty information to a batch of tokens.                                                                                                      |
| `_asset` is an array of AssetRoyalties structure objects. See [LibAsset.sol](https://github.com/Rawrshak/Rawrshak/blob/main/contracts/libraries/LibAsset.sol) |
| visibility: external                                                                                                                                          |
| state mutability:                                                                                                                                             |
