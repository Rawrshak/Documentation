# Execution Manager

> <mark style="color:blue;">**FUNCTIONS**</mark>
>
> tokenEscrow()
>
> nftsEscrow()
>
> verifyToken(\_token)
>
> placeBuyOrder(\_orderId, \_token, \_sender, \_tokenAmount)
>
> placeSellOrder(\_orderId, \_sender,  \_asset, \_assetAmount)
>
> executeBuyOrder(\_user, \_orderIds, \_paymentPerOrder, \_amounts, \_asset)
>
> executeSellOrder(\_user, \_orderIds, \_paymentPerOrder, \_amounts, \_token)
>
> cancelOrders(\_orderIds)
>
> claimOrders(\_user, \_orderIds)
>
> addSupportedToken(\_token)

| tokenEscrow() -> address              |
| ------------------------------------- |
| Retrieves a token's contract address. |
| visibility: external                  |
| state mutability: view                |

| nftsEscrow() -> address                            |
| -------------------------------------------------- |
| Retrieves a non-fungible token's contract address. |
| visibility: external                               |
| state mutability: view                             |

| verifyToken(address \_token) -> bool                                 |
| -------------------------------------------------------------------- |
| Verifies whether the payment token entered is supported by Rawrshak. |
| visibility: external                                                 |
| state mutability: view                                               |

| placeBuyOrder(uint256 \_orderId, address \_token, address \_sender, uint256 \_tokenAmount)                               |
| ------------------------------------------------------------------------------------------------------------------------ |
| Transfers `_tokenAmount` of `_token` from `_sender` to the Erc20Escrow contract and updates the escrowedByOrder mapping. |
| visibility: external                                                                                                     |
| state mutability:                                                                                                        |

| placeSellOrder(uint256 \_orderId, address \_sender, LibOrder.AssetData \_asset, uint256 \_assetAmount)                      |
| --------------------------------------------------------------------------------------------------------------------------- |
| Transfers `_assetAmount` of `_asset` to the NftEscrow contract and updates the escrowedAssets and escrowedAmounts mappings. |
| visibility: external                                                                                                        |
| state mutability:                                                                                                           |

| executeBuyOrder(address \_user, uint256\[] \_orderIds, uint256\[] \_paymentPerOrder, uint256\[] \_amounts, LibOrder.AssetData \_asset)                      |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Transfers assets to escrow to be claimed by buyers and withdraws token payment from escrow to `_user`, updating necessary records.                          |
| <p>Requirement:</p><ul><li>The length of <code>_orderIds</code> must equal the length of <code>_paymentPerOrder</code> and <code>_amounts</code>.</li></ul> |
| visibility: external                                                                                                                                        |
| state mutability:                                                                                                                                           |

| executeSellOrder(address user, uint256\[] \_orderIds, uint256\[] \_paymentPerOrder, uint256\[] \_amounts, address \_token)                                  |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Transfers token payment to escrow to be claimed by sellers and withdraws purchased assets to `_user`, updating necessary records.                           |
| <p>Requirement:</p><ul><li>The length of <code>_orderIds</code> must equal the length of <code>_paymentPerOrder</code> and <code>_amounts</code>.</li></ul> |
| visibility: external                                                                                                                                        |
| state mutability:                                                                                                                                           |

| cancelOrders(uint256\[] \_orderIds)                                                                                                                                                                                                    |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| For buy orders, this function withdraws unused token payments and claims purchased assets (if any, from partial fills). For sell orders, this function withdraws unsold assets and claims token payments (if any, from partial fills). |
| visibility: external                                                                                                                                                                                                                   |
| state mutability:                                                                                                                                                                                                                      |

| claimOrders(address \_user, uint256\[] \_orderIds)                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------- |
| Withdraws escrowed assets from filled or partially filled orders. Updates order state to "CLAIMED" if the order is completely filled. |
| visibility: external                                                                                                                  |
| state mutability:                                                                                                                     |

| addSupportedToken(address \_token)                                                                                    |
| --------------------------------------------------------------------------------------------------------------------- |
| Adds `_token` to the list of supported ERC20 tokens on Rawrshak.                                                      |
| Emits an <mark style="color:blue;">`AddedTokenSupport`</mark> event.                                                  |
| Passes through [Erc20Escrow.sol](https://docs.rawrshak.io/developers/smart-contracts/exchange-contracts/erc20escrow). |
| visibility: external                                                                                                  |
| state mutability:                                                                                                     |
