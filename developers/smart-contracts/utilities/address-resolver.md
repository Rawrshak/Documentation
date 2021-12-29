# Address Resolver

> <mark style="color:blue;">**EVENT**</mark>
>
> AddressRegistered(id, contractAddress)

| AddressRegistered(bytes4 id, address contractAddress)                                                                     |
| ------------------------------------------------------------------------------------------------------------------------- |
| Event emitted for each address registered when the <mark style="color:blue;">`registerAddress`</mark> function is called. |

> <mark style="color:blue;">**FUNCTIONS**</mark>
>
> getAddress(\_id)
>
> getAddressWithCheck(\_id)
>
> registerAddress(\_ids, \_addresses)

| getAddress(bytes4 \_id) -> address                          |
| ----------------------------------------------------------- |
| Queries the registry for the address associated with `_id`. |
| visibility: external                                        |
| state mutability: view                                      |

| getAddressWithCheck(\_id) -> address                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------ |
| Queries the registry for the address associated with `_id`, additionally checking whether the address is not the zero address. |
| visibility: external                                                                                                           |
| state mutability: view                                                                                                         |

| registerAddress(bytes4\[] \_ids, address\[] \_addresses)                                                                                     |
| -------------------------------------------------------------------------------------------------------------------------------------------- |
| Registers key-value pairs using `_ids` and `_addresses` to the registry mapping. This can only be accessed by the Rawrshak development team. |
| Emits an <mark style="color:blue;">`addressRegistered`</mark> event for each address registered.                                             |
| <p>Requirements:</p><ul><li>The length of <code>_ids</code> must equal the length of <code>_addresses</code>.</li></ul>                      |
| visibility: external                                                                                                                         |
| state mutability:                                                                                                                            |
