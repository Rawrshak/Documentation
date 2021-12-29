# 🚧 Orderbook

> <mark style="color:blue;">**FUNCTIONS**</mark>
>
> exists(\_orderId)
>
> ordersLength()
>
> verifyOrdersExist(\_orderIds)
>
> verifyAllOrdersData(\_orderIds, \_isBuyOrder)
>
> verifyTokenPayment(\_orderIds, \_isBuyOrder)
>
> verifyOrderOwners(\_orderIds, \_owner)
>
> verifyOrdersReady(\_orderIds)
>
> getOrderAmounts(\_orderIds, amountToFill, maxSpend)
>
> getPaymentTotals(\_orderIds_, \__amounts)
>
> getOrder(\_orderId)
>
> placeOrder(\_order)
>
> fillOrders(\_orderIds, \_amounts)
>
> cancelOrders(\_orderIds)
>
> claimOrders(\_orderIds)

| exists(uint256 \_orderId) -> bool |
| --------------------------------- |
|                                   |
| visibility: external              |
| state mutability: view            |

| ordersLength() -> uint256 |
| ------------------------- |
|                           |
| visibility: external      |
| state mutability: view    |

| verifyOrdersExist(uint256 \_orderIds) -> bool |
| --------------------------------------------- |
|                                               |
| visibility: external                          |
| state mutability: view                        |

| verifyAllOrdersData(uint256\[] \_orderIds, bool \_isBuyOrder) -> bool |
| --------------------------------------------------------------------- |
|                                                                       |
| visibility: external                                                  |
| state mutability: view                                                |

| verifyTokenPayment(uint256\[] \_orderIds, bool \_isBuyOrder) -> bool |
| -------------------------------------------------------------------- |
|                                                                      |
| visibility: external                                                 |
| state mutability: view                                               |

| verifyOrderOwners(uint256\[] \_orderIds, address \_owner) -> bool |
| ----------------------------------------------------------------- |
|                                                                   |
| visibility: external                                              |
| state mutability: view                                            |

| verifyOrdersReady(uint256\[] \_orderIds) -> bool |
| ------------------------------------------------ |
|                                                  |
| visibility: external                             |
| state mutability: view                           |

| getOrderAmounts(uint256\[] \_orderIds, uint256 amountToFill, uint256 maxSpend) -> uint256\[], uint256 |
| ----------------------------------------------------------------------------------------------------- |
|                                                                                                       |
| visibility: external                                                                                  |
| state mutability: view                                                                                |

| getPaymentTotals(uint256\[] \_orderIds, uint256\[] \_amounts) -> uint256, uint256\[] |
| ------------------------------------------------------------------------------------ |
|                                                                                      |
| visibility: external                                                                 |
| state mutability: view                                                               |

| getOrder(uint256 \_orderId) -> LibOrder.Order |
| --------------------------------------------- |
|                                               |
| visibility: external                          |
| state mutability: view                        |

| placeOrder(LibOrder.OrderInput \_order) -> uint256 |
| -------------------------------------------------- |
|                                                    |
| visibility: external                               |
| state mutability:                                  |

| fillOrders(uint256\[] \_orderIds, uint256\[] \_amounts) |
| ------------------------------------------------------- |
|                                                         |
| visibility: external                                    |
| state mutability:                                       |

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
