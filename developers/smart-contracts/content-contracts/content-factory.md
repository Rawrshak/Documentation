---
description: 'Todo: Add content factory contract description here.'
---

# Content Factory

> <mark style="color:blue;">**EVENT**</mark>
>
> ContractsDeployed(content, contentManager)

| ContractsDeployed(address content, address contentManager)                                     |
| ---------------------------------------------------------------------------------------------- |
| Event emitted when the <mark style="color:blue;">`createContracts`</mark>  function is called. |

> <mark style="color:blue;">**FUNCTIONS**</mark>
>
> updateContracts(\_content, \_contentManager, \_contentStorage, \_accessControlManager)
>
> contentExists(\_content)
>
> contentManagerExists(\_contentManager)
>
> createContracts(\_contractRoyaltyAccount, \_contractRoyaltyRate, \_contractUri)

| updateContracts(address \_content, address \_contentManager, address \_contentStorage, address \_accessControlManager) |
| ---------------------------------------------------------------------------------------------------------------------- |
| Updates contract implementations with `_content`, `_contentManager`, `_contentStorage`, and `accessControlManager`.    |
| <p>Requirements:</p><ul><li>Address parameters cannot be address zero.</li></ul>                                       |
| visibility: public                                                                                                     |
| state mutability:                                                                                                      |

| contentExists(address \_content) -> bool               |
| ------------------------------------------------------ |
| Queries whether the contract address`_content` exists. |
| visibility: public                                     |
| state mutability: view                                 |

| contentManagerExists(address \_contentManager) -> bool         |
| -------------------------------------------------------------- |
| Queries whether the contract address `_contentManager` exists. |
| visibility: public                                             |
| state mutability: view                                         |

| createContracts(address \_contractRoyaltyAccount, uint24 \_contractRoyaltyRate, string \_contractUri) |
| ----------------------------------------------------------------------------------------------------- |
| Deploys new content contracts onto the blockchain and initializes the contract royalties and uri.     |
| Emits a `ContractsDeployed` event.                                                                    |
| visibility: external                                                                                  |
| state mutability:                                                                                     |
