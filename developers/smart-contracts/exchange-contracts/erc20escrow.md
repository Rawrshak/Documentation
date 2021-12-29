# 🚧 Erc20Escrow

> <mark style="color:blue;">**EVENTS**</mark>
>
> ClaimedRoyalties(owner, tokens, amounts)
>
> AddedTokenSupports(token)

| ClaimedRoyalties(address owner, address\[] tokens, uint256\[] amounts) |
| ---------------------------------------------------------------------- |
|                                                                        |

| AddedTokenSupports(address token) |
| --------------------------------- |
|                                   |

> <mark style="color:blue;">**FUNCTIONS**</mark>
>
> escrowedTokensByOrder(\_orderId)
>
> claimableTokensByOwner(\_owner)
>
> isTokenSupported(\_token)
>
> addSupportedTokens(\_token)
>
> deposit(\_token, \_orderId, \_sender, \_amount)
>
> withdraw(\_orderId, \_user, \_amount)
>
> transferRoyalty(\_token, \_sender, \_owner, \_amount)
>
> transferRoyalty(\_orderId, \_to, \_amount)
>
> transferPlatformFee(\_token, \_sender, \_feesEscrow, \_amount)
>
> transferPlatformFee(\_orderId, \_feesEscrow, \_amount)
>
> claimRoyalties(\_owner)

| escrowedTokensByOrder(uint256 \_orderId) -> uint256 |
| --------------------------------------------------- |
|                                                     |
| visibility: external                                |
| state mutability: view                              |

| claimableTokensByOwner(address \_owner) -> address\[], uint256\[] |
| ----------------------------------------------------------------- |
|                                                                   |
| visibility: external                                              |
| state mutability: view                                            |

| isTokenSupported(address \_token) -> bool |
| ----------------------------------------- |
|                                           |
| visibility: external                      |
| state mutability: view                    |

| addSupportedTokens(address \_token) |
| ----------------------------------- |
|                                     |
| visibility: external                |
| state mutability:                   |

| deposit(address \_token, uint256 \_orderId, address \_sender, uint256 \_amount) |
| ------------------------------------------------------------------------------- |
|                                                                                 |
| visibility: external                                                            |
| state mutability:                                                               |

| withdraw(uint256 \_orderId, address \_user, uint256 \_amount) |
| ------------------------------------------------------------- |
|                                                               |
| visibility: external                                          |
| state mutability:                                             |

| transferRoyalty(address \_token, address \_sender, address \_owner, uint256 \_amount) |
| ------------------------------------------------------------------------------------- |
|                                                                                       |
| visibility: external                                                                  |
| state mutability:                                                                     |

| transferRoyalty(uint256 \_orderId, address \_to, uint256 \_amount) |
| ------------------------------------------------------------------ |
|                                                                    |
| visibility: external                                               |
| state mutability:                                                  |

| transferPlatformFee(address \_token, address \_sender, address \_feesEscrow, uint256 \_amount) |
| ---------------------------------------------------------------------------------------------- |
|                                                                                                |
| visibility: external                                                                           |
| state mutability:                                                                              |

| transferPlatformFee(uint256 \_orderId, address \_feesEscrow, uint256 \_amount) |
| ------------------------------------------------------------------------------ |
|                                                                                |
| visibility: external                                                           |
| state mutability:                                                              |

| claimRoyalties(address \_owner) |
| ------------------------------- |
|                                 |
| visibility: external            |
| state mutability:               |
