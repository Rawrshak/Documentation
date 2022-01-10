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

| escrowedAmounts(uint256 \_orderId) -> uint256                   |
| --------------------------------------------------------------- |
| Returns the amount of assets escrowed for the given `_orderId`. |
| visibility: external                                            |
| state mutability: view                                          |

| escrowedAsset(uint256 \_orderId) -> address, uint256               |
| ------------------------------------------------------------------ |
| Returns the content address and token Id for the given `_orderId`. |
| visibility: external                                               |
| state mutability: view                                             |

| deposit(uint256 \_orderId, address \_sender, uint256 \_amount, LibOrder.AssetData \_assetData) |
| ---------------------------------------------------------------------------------------------- |
| Transfers `amount` of assets from `_sender` to escrow.                                         |
| visibility: external                                                                           |
| state mutability:                                                                              |

| withdraw(uint256 orderId, address \_receiver, uint256 \_amount) |
| --------------------------------------------------------------- |
| Withdraws `_amount` of assets from escrow to `_receiver`.       |
| visibility: external                                            |
| state mutability:                                               |

| withdrawBatch(uint256\[] orderIds, address \_receiver, uint256\[] amounts) |
| -------------------------------------------------------------------------- |
| Withdraws a batch of assets from escrow to `_receiver`.                    |
| visibility: external                                                       |
| state mutability:                                                          |
