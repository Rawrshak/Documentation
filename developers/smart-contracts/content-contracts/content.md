---
description: 'Todo: Add content contract description here.'
---

# Content

> <mark style="color:blue;">**EVENTS**</mark>
>
> Mint(operator, data)
>
> Burn(operator, data)

| Mint(address operator, LibAsset.MintData data)                                                        |
| ----------------------------------------------------------------------------------------------------- |
| Event emitted when the <mark style="color:blue;">`mintBatch`</mark> function is called by `operator`. |

| Burn(address operator, LibAsset.BurnData data)                                                        |
| ----------------------------------------------------------------------------------------------------- |
| Event emitted when the <mark style="color:blue;">`burnBatch`</mark> function is called by `operator`. |

> <mark style="color:blue;">**FUNCTIONS**</mark>
>
> mintBatch(\_data)
>
> burnBatch(\_data)
>
> contractUri()
>
> uri(\_tokenId)
>
> uri(\_tokenId, \_version)
>
> totalSupply(\_tokenId)
>
> maxSupply(\_tokenId)
>
> contractRoyalty()
>
> userMintNonce(\_user)
>
> royaltyInfo(\_tokenId, \_salePrice)

| mintBatch(LibAsset.MintData \_data)                                                                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Mints a batch of assets.                                                                                                                                                                                                 |
| `_data` MintData structure object. See [LibAsset.sol](https://github.com/Rawrshak/Rawrshak/blob/main/contracts/libraries/LibAsset.sol).                                                                                  |
| Emits a `Mint` event.                                                                                                                                                                                                    |
| <p>Requirements:</p><ul><li>The caller must be verified.</li><li>The specified token Id in <code>_data</code> must exist.</li><li>The maximum supply of each token will not be surpassed through this minting.</li></ul> |
| visibility: external                                                                                                                                                                                                     |
| state mutability:                                                                                                                                                                                                        |

| burnBatch(LibAsset.BurnData \_data)                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Burns a batch of assets.                                                                                                                              |
| `_data` BurnData structure object. See [LibAsset.sol](https://github.com/Rawrshak/Rawrshak/blob/main/contracts/libraries/LibAsset.sol).               |
| Emits a <mark style="color:blue;">`Burn`</mark> event.                                                                                                |
| <p>Requirements:</p><ul><li>The caller must be the owner of the tokens or approved by approved by the owner.</li><li>The tokens must exist.</li></ul> |
| visibility: external                                                                                                                                  |
| state mutability:                                                                                                                                     |

| contractUri() -> string   |
| ------------------------- |
| Returns the contract uri. |
| visibility: external      |
| state mutability: view    |

| uri(uint256 \_tokenId) -> string                        |
| ------------------------------------------------------- |
| Returns the latest public uri of token type `_tokenId`. |
| visbility: external                                     |
| state mutability: view                                  |

| uri(uint256 \_tokenId, uint256 \_version) -> string                                 |
| ----------------------------------------------------------------------------------- |
| Returns the particular public uri of token type `_tokenId` specified by `_version`. |
| visibility: external                                                                |
| state mutability: view                                                              |

| totalSupply(uint256 \_tokenId) -> uint256                                   |
| --------------------------------------------------------------------------- |
| Returns the total amount of token type `_tokenId` currently in circulation. |
| visibility: external                                                        |
| state mutability: view                                                      |

| maxSupply(uint \_tokenId) -> uint256                                              |
| --------------------------------------------------------------------------------- |
| Returns the maximum amount of token type `_tokenId` allowed to be in circulation. |
| visibility: external                                                              |
| state mutability: view                                                            |

| contractRoyalty() -> address, uint24                                             |
| -------------------------------------------------------------------------------- |
| Returns the default royalty receiver address and rate for the contract's assets. |
| visibility: external                                                             |
| state mutability: view                                                           |

| userMintNonce(address \_user) -> uint256        |
| ----------------------------------------------- |
| Returns the nonce of `_user` for this contract. |
| visibility: external                            |
| state mutability: view                          |

| royaltyInfo(uint256 \_tokenId, uint256 \_salePrice) -> address, uint256                                     |
| ----------------------------------------------------------------------------------------------------------- |
| Returns the receiver address and calculated royalty amount for token type `_tokenId` sold for `_salePrice`. |
| visibility: external                                                                                        |
| state mutability: view                                                                                      |

