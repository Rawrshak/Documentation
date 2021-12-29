---
description: 'Todo: Add exchange contract description here.'
---

# Exchange

> <mark style="color:blue;">**EVENTS**</mark>
>
> OrderPlaced(from, orderId, order)
>
> OrdersFilled(from, orderIds, amounts, asset, token, totalAssetsAmount, volume)
>
> OrdersDeleted(owner, orderIds)
>
> OrdersClaimed(owner, orderIds)

| OrderPlaced(address from, uint256 orderId, LibOrder.OrderInput order)                    |
| ---------------------------------------------------------------------------------------- |
| Event emitted when the <mark style="color:blue;">`placeOrder`</mark> function is called. |

| OrdersFilled(address from, uint256\[] orderIds, uint256\[] amounts, LibOrder.AssetData asset, address token, uint256 totalAssetsAmount, uint256 volume) |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Event emitted when the functions <mark style="color:blue;">`fillBuyOrder`</mark> or <mark style="color:blue;">`fillSellOrder`</mark> are called.        |

| OrdersDeleted(address owner, uint256 orderIds)                                                        |
| ----------------------------------------------------------------------------------------------------- |
| Event emitted when the <mark style="color:blue;">`cancelOrders`</mark> function is called by `owner`. |

| OrdersClaimed(address owner, uint256\[] orderIds)                                                    |
| ---------------------------------------------------------------------------------------------------- |
| Event emitted when the <mark style="color:blue;">`claimOrders`</mark> function is called by `owner`. |

> <mark style="color:blue;">**FUNCTIONS**</mark>
>
> getOrder(id)
>
> tokenEscrow()
>
> nftsEscrow()
>
> claimableRoyalties()
>
> placeOrder(\_order)
>
> fillBuyOrder(\_orderIds, amountToSell, maxSpend)
>
> fillSellOrder(\_orderIds, anountToBuy, maxSpend)
>
> cancelOrders(\_orderIds)
>
> claimOrders(\_orderIds)
>
> claimRoyalties()
>
> addSupportedToken(\_token)

| getOrder(uint256 id) -> LibOrder.Order                                                                                                                          |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Retrieves `id`'s order information from the orders mapping in [Orderbook.sol](https://github.com/Rawrshak/Rawrshak/blob/main/contracts/exchange/Orderbook.sol). |
| visibility: external                                                                                                                                            |
| state mutability: view                                                                                                                                          |

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

| claimableRoyalties() -> address\[], uint256\[]                                             |
| ------------------------------------------------------------------------------------------ |
| Retrieves the contract address and amount of each token available for the caller to claim. |
| visibility: external                                                                       |
| state mutability: view                                                                     |

| placeOrder(LibOrder.OrderInput \_order)                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------------------- |
| Places a buy or sell order with the information `_order` on the exchange and transfers the tokens to escrow.                              |
| `_order` OrderInput structure object. See [LibOrder.sol](https://github.com/Rawrshak/Rawrshak/blob/main/contracts/libraries/LibOrder.sol) |
| emits an <mark style="color:blue;">`OrderPlaced`</mark> event.                                                                            |
| visibility: external                                                                                                                      |
| state mutability:                                                                                                                         |

| fillBuyOrder(uint256\[] \_orderIds, uint256 amountToSell, uint256 maxSpend)                                                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Fills buy orders, transferring the sold assets to escrow, and withdrawing token payments from escrow.                                                                                                                  |
| Emits an <mark style="color:blue;">`OrdersFilled`</mark> event.                                                                                                                                                        |
| <p>Requirements:</p><ul><li>Length of <code>_orderIds</code> must be greater than 0. </li><li><code>_orderIds</code> must exist.</li><li><code>_orderIds</code> must be of the same asset and token payment.</li></ul> |
| visibility: external                                                                                                                                                                                                   |
| state mutability:                                                                                                                                                                                                      |

| fillSellOrder(uint256\[] \_orderIds, uint256 amountToBuy, uint256 maxSpend)                                                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Fills sell orders, sending token payments to escrow, and withdrawing the purchased assets from escrow.                                                                                                                 |
| Emits an <mark style="color:blue;">`OrdersFilled`</mark> event.                                                                                                                                                        |
| <p>Requirements:</p><ul><li>Length of <code>_orderIds</code> must be greater than 0. </li><li><code>_orderIds</code> must exist.</li><li><code>_orderIds</code> must be of the same asset and token payment.</li></ul> |
| visibility: external                                                                                                                                                                                                   |
| state mutability:                                                                                                                                                                                                      |

| cancelOrders(uint256\[] \_orderIds)                                                                                                                                                      |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Cancels unfilled or partially filled orders and withdraws the unused tokens.                                                                                                             |
| Emits an <mark style="color:blue;">`OrdersDeleted`</mark> event.                                                                                                                         |
| <p>Requirements:</p><ul><li><code>_orderIds</code> must exist.</li><li><code>_orderIds</code> must be owned by caller.</li><li>Filled and cancelled orders cannot be canceled.</li></ul> |
| visibility: external                                                                                                                                                                     |
| state mutability:                                                                                                                                                                        |

| claimOrders(uint256\[] \_orderIds)                                                                                               |
| -------------------------------------------------------------------------------------------------------------------------------- |
| Withdraws tokens from filled buy or sell orders.                                                                                 |
| Emits an <mark style="color:blue;">`OrdersClaimed`</mark> event.                                                                 |
| <p>Requirements:</p><ul><li><code>_orderIds</code> must exist.</li><li><code>_orderIds</code> must be owned by caller.</li></ul> |
| visibility: external                                                                                                             |
| state mutability:                                                                                                                |

| claimRoyalties()                                                                           |
| ------------------------------------------------------------------------------------------ |
| Withdraws royalties available to claim from purchases of their asset made on the exchange. |
| visibility: external                                                                       |
| state mutability:                                                                          |

| addSupportedToken(address \_token)                                   |
| -------------------------------------------------------------------- |
| Adds `_token` to the list of supported ERC20 tokens on the exchange. |
| visibility: external                                                 |
| state mutability:                                                    |
