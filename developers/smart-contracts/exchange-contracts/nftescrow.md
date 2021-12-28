# NftEscrow

> <mark style="color:blue;">**FUNCTIONS**</mark>
>
> escrowedAmounts(\_orderId)
>
> escrowedAsset(\_orderId)
>
> deposit(\_orderId, \_sender, \_amount, \_assetData)
>
> withdraw(orderId, \_receiver, amount)
>
> withdrawBatch(orderIds, \_receiver, amounts)

| escrowedAmounts(uint256 \_orderId) -> uint256 |
| --------------------------------------------- |
|                                               |
| visibility: external                          |
| state mutability: view                        |

| escrowedAsset(uint256 \_orderId) -> address, uint256 |
| ---------------------------------------------------- |
|                                                      |
| visibility: external                                 |
| state mutability: view                               |

| deposit( uint256 \_orderId, address \_sender, uint256 \_amount, LibOrder.AssetData \_assetData) |
| ----------------------------------------------------------------------------------------------- |
|                                                                                                 |
| visibility: external                                                                            |
| state mutability:                                                                               |

| withdraw(uint256 orderId, address \_receiver, uint256 amount) |
| ------------------------------------------------------------- |
|                                                               |
| visibility: external                                          |
| state mutability:                                             |

| withdrawBatch(uint256\[] orderIds, address \_receiver, uint256\[] amounts) |
| -------------------------------------------------------------------------- |
|                                                                            |
| visibility: external                                                       |
| state mutability:                                                          |
