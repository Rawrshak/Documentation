# Orderbook

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

| exists(uint256 \_orderId) -> bool                           |
| ----------------------------------------------------------- |
| Verifies whether the order `_orderId` has ever been placed. |
| visibility: external                                        |
| state mutability: view                                      |

| ordersLength() -> uint256                                                 |
| ------------------------------------------------------------------------- |
| Returns the total number of orders that have been placed on the exchange. |
| visibility: external                                                      |
| state mutability: view                                                    |

| verifyOrdersExist(uint256\[] \_orderIds) -> bool                                                                                                               |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Runs a loop of the <mark style="color:blue;">`exists`</mark> function to verify that all the orders in `_orderIds` exist and have been placed on the exchange. |
| visibility: external                                                                                                                                           |
| state mutability: view                                                                                                                                         |

| verifyAllOrdersData(uint256\[] \_orderIds, bool \_isBuyOrder) -> bool                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Verifies whether all the orders in `_orderIds` reference the same asset and token payment. And it checks that all the orders' buy/sell order type matches `_isBuyOrder`. |
| visibility: external                                                                                                                                                     |
| state mutability: view                                                                                                                                                   |

| verifyOrderOwners(uint256\[] \_orderIds, address \_owner) -> bool         |
| ------------------------------------------------------------------------- |
| Verifies whether the owner of the orders in `_orderIds` matches `_owner`. |
| visibility: external                                                      |
| state mutability: view                                                    |

| verifyOrdersReady(uint256\[] \_orderIds) -> bool                            |
| --------------------------------------------------------------------------- |
| Verifies whether all the orders in `_orderIds` are still available to fill. |
| visibility: external                                                        |
| state mutability: view                                                      |

| getOrderAmounts(uint256\[] \_orderIds, uint256 amountToFill, uint256 maxSpend) -> uint256\[], uint256                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Returns the amount of the asset to be filled from each order in `_orderIds`. The sum of which cannot exceed `amountToFill`, and the cumulative price cannot exceed `maxSpend`. |
| visibility: external                                                                                                                                                           |
| state mutability: view                                                                                                                                                         |

| getPaymentTotals(uint256\[] \_orderIds, uint256\[] \_amounts) -> uint256, uint256\[]                                    |
| ----------------------------------------------------------------------------------------------------------------------- |
| Returns the token payment to be paid for each order in `orderIds` and the cumulative payment for the entire fill order. |
| visibility: external                                                                                                    |
| state mutability: view                                                                                                  |

| getOrder(uint256 \_orderId) -> LibOrder.Order                                                                       |
| ------------------------------------------------------------------------------------------------------------------- |
| Returns the order information of `_orderId`.                                                                        |
| Order structure object. See [LibOrder.sol](https://docs.rawrshak.io/developers/smart-contracts/libraries/liborder). |
| visibility: external                                                                                                |
| state mutability: view                                                                                              |

| placeOrder(LibOrder.OrderInput \_order) -> uint256                                                                                |
| --------------------------------------------------------------------------------------------------------------------------------- |
| Places an order on the exchange with order information `_order` and returns the assigned order Id.                                |
| `_order` OrderInput structure object. See [LibOrder.sol](https://docs.rawrshak.io/developers/smart-contracts/libraries/liborder). |
| <p>Requirements:</p><ul><li>The token payment must be on the list of supported ERC20 tokens.</li></ul>                            |
| visibility: external                                                                                                              |
| state mutability:                                                                                                                 |

| fillOrders(uint256\[] \_orderIds, uint256\[] \_amounts)                                             |
| --------------------------------------------------------------------------------------------------- |
| Updates the order information of `_orderIds` as to the amount of assets filled and its order state. |
| visibility: external                                                                                |
| state mutability:                                                                                   |

| cancelOrders(uint256\[] \_orderIds)                                                                              |
| ---------------------------------------------------------------------------------------------------------------- |
| Updates the order state of `_orderIds` to "CANCELLED".                                                           |
| <p>Requirement:</p><ul><li>The order state of the orders must either be "READY" or "PARTIALLY_FILLED".</li></ul> |
| visibility: external                                                                                             |
| state mutability:                                                                                                |

| claimOrders(uint256\[] \_orderIds)                                                                                  |
| ------------------------------------------------------------------------------------------------------------------- |
| Updates the order state of `_orderIds` to "CLAIMED" if the order is completely filled and the owner has claimed it. |
| visibility: external                                                                                                |
| state mutability:                                                                                                   |
