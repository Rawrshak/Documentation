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

| claimableRoyalties(address \_user) -> address\[], uint256\[] |
| ------------------------------------------------------------ |
|                                                              |
| visibility: external                                         |
| state mutability: view                                       |

| payableRoyalties(LibOrder.AssetData \_asset, uint256 \_total) -> address, uint256, uint256 |
| ------------------------------------------------------------------------------------------ |
|                                                                                            |
| visibility: external                                                                       |
| state mutability: view                                                                     |

| claimRoyalties(address \_user) |
| ------------------------------ |
|                                |
| visibility: external           |
| state mutability:              |

| transferRoyalty(address \_sender, address \_token, address \_receiver, uint256 \_royaltyFee) |
| -------------------------------------------------------------------------------------------- |
|                                                                                              |
| visibility: external                                                                         |
| state mutability:                                                                            |

| transferRoyalty(uint256 \_orderId, address \_receiver, uint256 \_royaltyFee) |
| ---------------------------------------------------------------------------- |
|                                                                              |
| visibility: external                                                         |
| state mutability:                                                            |

| transferPlatformFee(address \_sender, address \_token, uint256 \_total) |
| ----------------------------------------------------------------------- |
|                                                                         |
| visibility: external                                                    |
| state mutability:                                                       |

| transferPlatformFee(address \_token, uint256 \_orderId, uint256 \_total) |
| ------------------------------------------------------------------------ |
|                                                                          |
| visibility: external                                                     |
| state mutability:                                                        |
