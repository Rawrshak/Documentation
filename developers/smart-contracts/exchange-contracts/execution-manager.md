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

| tokenEscrow() -> address |
| ------------------------ |
|                          |
| visibility: external     |
| state mutability: view   |

| nftsEscrow() -> address |
| ----------------------- |
|                         |
| visibility: external    |
| state mutability: view  |

| verifyToken(address \_token) -> bool |
| ------------------------------------ |
|                                      |
| visibility: external                 |
| state mutability: view               |

| placeBuyOrder(uint256 \_orderId, address \_token, address \_sender, uint256 \_tokenAmount) |
| ------------------------------------------------------------------------------------------ |
|                                                                                            |
| visibility: external                                                                       |
| state mutability:                                                                          |

| placeSellOrder(uint256 \_orderId, address \_sender, LibOrder.AssetData \_asset, uint256 \_assetAmount) |
| ------------------------------------------------------------------------------------------------------ |
|                                                                                                        |
| visibility: external                                                                                   |
| state mutability:                                                                                      |

| executeBuyOrder(address \_user, uint256\[] \_orderIds, uint256\[] \_paymentPerOrder, uint256\[] \_amounts, LibOrder.AssetData \_asset) |
| -------------------------------------------------------------------------------------------------------------------------------------- |
|                                                                                                                                        |
| visibility: external                                                                                                                   |
| state mutability:                                                                                                                      |

| executeSellOrder(address user, uint256\[] \_orderIds, uint256\[] \_paymentPerOrder, uint256\[] \_amounts, address \_token) |
| -------------------------------------------------------------------------------------------------------------------------- |
|                                                                                                                            |
| visibility: external                                                                                                       |
| state mutability:                                                                                                          |

| cancelOrders(uint256\[] \_orderIds) |
| ----------------------------------- |
|                                     |
| visibility: external                |
| state mutability:                   |

| claimOrders(address \_user, uint256\[] \_orderIds) |
| -------------------------------------------------- |
|                                                    |
| visibility: external                               |
| state mutability:                                  |

| addSupportedToken(address \_token) |
| ---------------------------------- |
|                                    |
| visibility: external               |
| state mutability:                  |
