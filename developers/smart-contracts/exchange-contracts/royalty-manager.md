# Royalty Manager

> <mark style="color:blue;">**FUNCTIONS**</mark>
>
> claimableRoyalties(\_user)
>
> payableRoyalties(\_asset, \_total)
>
> claimRoyalties(\_user)
>
> transferRoyalty(\_sender, \_token, \_receiver, \_royaltyFee)
>
> transferRoyalty(\_orderId, \_receiver, \_royaltyFee)
>
> transferPlatformFee(\_sender, \_token, \_total)
>
> transferPlatformFee(\_token_,_ \_orderId, \_total)

| claimableRoyalties(address \_user) -> address\[], uint256\[]                                  |
| --------------------------------------------------------------------------------------------- |
| Returns the token contract addresses and corresponding amounts available to claim by `_user`. |
| visibility: external                                                                          |
| state mutability: view                                                                        |

| payableRoyalties(LibOrder.AssetData \_asset, uint256 \_total) -> address, uint256, uint256                             |
| ---------------------------------------------------------------------------------------------------------------------- |
| Returns the royalty fees and the total remaining token payment after the exchange and royalty fees have been deducted. |
| visibility: external                                                                                                   |
| state mutability: view                                                                                                 |

| claimRoyalties(address \_user)                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------ |
| Withdraws any claimable tokens to \_user, and updates the records to reflect that there are no more tokens remaining to claim. |
| Emits a <mark style="color:blue;">`ClaimedRoyalties`</mark> event.                                                             |
| visibility: external                                                                                                           |
| state mutability:                                                                                                              |

| transferRoyalty(address \_sender, address \_token, address \_receiver, uint256 \_royaltyFee) |
| -------------------------------------------------------------------------------------------- |
| Transfers creator royalties from `_sender` to escrow.                                        |
| visibility: external                                                                         |
| state mutability:                                                                            |

| transferRoyalty(uint256 \_orderId, address \_receiver, uint256 \_royaltyFee)                                                  |
| ----------------------------------------------------------------------------------------------------------------------------- |
| Transfers creator royalties deducted from escrowed buy orders to escrow.                                                      |
| <p>Requirement:</p><ul><li>The amount of tokens escrowed must be greater than or equal to <code>_royaltyFee</code>.</li></ul> |
| visibility: external                                                                                                          |
| state mutability:                                                                                                             |

| transferPlatformFee(address \_sender, address \_token, uint256 \_total) |
| ----------------------------------------------------------------------- |
| Transfers platform fees from `_sender` to stakers, if any.              |
| visibility: external                                                    |
| state mutability:                                                       |

| transferPlatformFee(address \_token, uint256 \_orderId, uint256 \_total)      |
| ----------------------------------------------------------------------------- |
| Transfers platform fees deducted from escrowed buy orders to stakers, if any. |
| visibility: external                                                          |
| state mutability:                                                             |
