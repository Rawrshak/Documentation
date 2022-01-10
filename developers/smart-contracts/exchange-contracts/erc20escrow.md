# Erc20Escrow

> <mark style="color:blue;">**EVENTS**</mark>
>
> ClaimedRoyalties(owner, tokens, amounts)
>
> AddedTokenSupports(token)

| ClaimedRoyalties(address owner, address\[] tokens, uint256\[] amounts)                       |
| -------------------------------------------------------------------------------------------- |
| Event emitted when the <mark style="color:blue;">`claimRoyalties`</mark> function is called. |

| AddedTokenSupport(address token)                                                                 |
| ------------------------------------------------------------------------------------------------ |
| Event emitted when the <mark style="color:blue;">`addSupportedTokens`</mark> function is called. |

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
> withdraw(\_orderId, \_receiver, \_amount)
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

| escrowedTokensByOrder(uint256 \_orderId) -> uint256                       |
| ------------------------------------------------------------------------- |
| Returns the amount of tokens currently escrowed for the given `_orderId`. |
| visibility: external                                                      |
| state mutability: view                                                    |

| claimableTokensByOwner(address \_owner) -> address\[], uint256\[]                              |
| ---------------------------------------------------------------------------------------------- |
| Returns the token contract addresses and corresponding amounts available to claim by `_owner`. |
| visibility: external                                                                           |
| state mutability: view                                                                         |

| isTokenSupported(address \_token) -> bool                                            |
| ------------------------------------------------------------------------------------ |
| Returns true or false based on whether token type `_token` is supported by Rawrshak. |
| visibility: external                                                                 |
| state mutability: view                                                               |

| addSupportedTokens(address \_token)                                  |
| -------------------------------------------------------------------- |
| Adds `_token` to the list of supported ERC20 tokens on Rawrshak.     |
| Emits an <mark style="color:blue;">`AddedTokenSupport`</mark> event. |
| visibility: external                                                 |
| state mutability:                                                    |

| deposit(address \_token, uint256 \_orderId, address \_sender, uint256 \_amount) |
| ------------------------------------------------------------------------------- |
| Transfers `_amount` of token type `_token` from `_sender` to escrow.            |
| visibility: external                                                            |
| state mutability:                                                               |

| withdraw(uint256 \_orderId, address \_receiver, uint256 \_amount)                                                         |
| ------------------------------------------------------------------------------------------------------------------------- |
| Withdraws `amount` of tokens from escrow to `receiver`.                                                                   |
| <p>Requirement:</p><ul><li>The amount of tokens escrowed must be greater than or equal to <code>_amount</code>.</li></ul> |
| visibility: external                                                                                                      |
| state mutability:                                                                                                         |

| transferRoyalty(address \_token, address \_sender, address \_owner, uint256 \_amount) |
| ------------------------------------------------------------------------------------- |
| Transfers creator royalties from `_sender` to escrow.                                 |
| visibility: external                                                                  |
| state mutability:                                                                     |

| transferRoyalty(uint256 \_orderId, address \_to, uint256 \_amount)                                                        |
| ------------------------------------------------------------------------------------------------------------------------- |
| Transfers creator royalties deducted from escrowed buy orders to escrow.                                                  |
| <p>Requirement:</p><ul><li>The amount of tokens escrowed must be greater than or equal to <code>_amount</code>.</li></ul> |
| visibility: external                                                                                                      |
| state mutability:                                                                                                         |

| transferPlatformFee(address \_token, address \_sender, address \_feesEscrow, uint256 \_amount) |
| ---------------------------------------------------------------------------------------------- |
| Transfers platform fees from `_sender` to `_feesEscrow`.                                       |
| visibility: external                                                                           |
| state mutability:                                                                              |

| transferPlatformFee(uint256 \_orderId, address \_feesEscrow, uint256 \_amount) |
| ------------------------------------------------------------------------------ |
| Transfers platform fees deducted from escrowed buy orders to `_feesEscrow`.    |
| visibility: external                                                           |
| state mutability:                                                              |

| claimRoyalties(address \_owner)                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- |
| Withdraws any claimable tokens to \_owner, and updates the records to reflect that there are no more tokens remaining to claim. |
| Emits a <mark style="color:blue;">`ClaimedRoyalties`</mark> event.                                                              |
| visibility: external                                                                                                            |
| state mutability:                                                                                                               |
