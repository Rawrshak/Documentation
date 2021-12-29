# LibAsset

> <mark style="color:blue;">**STRUCTURE OBJECTS**</mark>
>
> CreateData
>
> MintData
>
> BurnData
>
> Asset
>
> AssetUri
>
> AssetRoyalties
>
> SystemApprovalPair

```solidity
struct CreateData {
    string publicDataUri;
    string hiddenDataUri;
    uint256 maxSupply;
    address royaltyReceiver;
    uint24 royaltyRate;
}
```

```solidity
struct MintData {
    address to;
    uint256[] tokenIds;
    uint256[] amounts;
    uint256 nonce;
    address signer;
    bytes signature;
}
```

```solidity
struct BurnData {
    address account;
    uint256[] tokenIds;
    uint256[] amounts;
}
```

```solidity
struct Asset {
    string[] dataUri;
    uint256 version;
}
```

```solidity
struct AssetUri {
    uint256 tokenId;
    string uri;
}
```

```solidity
struct AssetRoyalties {
    uint256 tokenId;
    address royaltyReceiver;
    uint24 royaltyRate;
}
```

```solidity
struct SystemApprovalPair {
        address operator;
        bool approved;
    }
```

```solidity
struct SystemApprovalPair {
    address operator;
    bool approved;
}
```
