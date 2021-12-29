# LibOrder

> <mark style="color:blue;">**STRUCTURE OBJECTS**</mark>
>
> AssetData
>
> Order
>
> OrderInput

```solidity
struct AssetData {
    address contentAddress;
    uint256 tokenId;
}
```

```solidity
struct Order {
    AssetData asset;
    address owner;
    address token;
    uint256 price;
    uint256 amountOrdered;
    uint256 amountFilled;
    bool isBuyOrder;
    OrderState state;
}
```

```solidity
struct OrderInput {
    AssetData asset;
    address owner;
    address token;
    uint256 price;
    uint256 amount;
    bool isBuyOrder;
}
```

> <mark style="color:blue;">**ENUMBERABLES**</mark>
>
> OrderState

```solidity
enum OrderState {
    READY,
    PARTIALLY_FILLED,
    FILLED,
    CLAIMED,
    CANCELLED
}
```
