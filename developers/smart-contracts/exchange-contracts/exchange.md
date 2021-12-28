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

| OrdersPlaced(address from, uint256 orderId, LibOrder.OrderInput order) |
| ---------------------------------------------------------------------- |
|                                                                        |

| OrdersPlaced(address from, uint256\[] orderIds, uint256\[] amounts, LibOrder.AssetData asset, address token, uint256 totalAssetsAmount, uint256 volume) |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                                                                                                                                                         |

| OrdersDeleted(address owner, uint256 orderIds) |
| ---------------------------------------------- |
|                                                |

| OrdersClaimed(address owner, uint256\[] orderIds) |
| ------------------------------------------------- |
|                                                   |

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

| placeOrder(LibOrder.OrderInput \_order) |
| --------------------------------------- |
|                                         |
| visibility: external                    |
| state mutability:                       |

| fillBuyOrder(uint256\[] \_orderIds, uint256 amountToSell, uint256 maxSpend) |
| --------------------------------------------------------------------------- |
|                                                                             |
| visibility: external                                                        |
| state mutability:                                                           |

| fillSellOrder(uint256\[] \_orderIds, uint256 amountToBuy, uint256 maxSpend) |
| --------------------------------------------------------------------------- |
|                                                                             |
| visibility: external                                                        |
| state mutability:                                                           |

| cancelOrders(uint256\[] \_orderIds) |
| ----------------------------------- |
|                                     |
| visibility: external                |
| state mutability:                   |

| claimOrders(uint256\[] \_orderIds) |
| ---------------------------------- |
|                                    |
| visibility: external               |
| state mutability:                  |

| claimRoyalties()     |
| -------------------- |
|                      |
| visibility: external |
| state mutability:    |

| addSupportedToken(address \_token) |
| ---------------------------------- |
|                                    |
| visibility: external               |
| state mutability:                  |
