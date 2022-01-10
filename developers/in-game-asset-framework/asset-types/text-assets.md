# Text Assets

The Text Asset metadata framework creates a guide for text-based NFTs such as Titles and Lore. It contains the necessary information and specific requirements. This text asset metadata framework should go in the <mark style="color:blue;">`assetProperties`</mark> <mark style="color:blue;"></mark><mark style="color:blue;"></mark> object in the Asset Metadata schema.

Text NFTs can be used to convey in-game achievements and unlockable information about in-game content. They may also be used as keys for unlockable content or materials for crafting.&#x20;

## Metadata

### Schema

```
{
    "title": "Asset Properties",
    "type": "object",
    "properties": {
        "title": {
            "type": "string",
            "description": "In-game name of the text asset."
        },
        "description": {
            "type": "string",
            "description": "Description of the asset which this token represents."
        }
    }
}
```

## Subtypes

We define three Text-based NFT frameworks, each with a different use case. Gamers should expect them to be used in a game for its designated use. However, these <mark style="color:blue;">`subtypes`</mark> are merely guides for game developers. They are free to use these text assets however they like in their own game.

{% hint style="info" %}
If a game developer decides to use a text asset differently in their game, they need to notify gamers to change their expectation of how these assets are used for the game.
{% endhint %}

### Title Subtype

Titles are used by gamers to show off their achievements. They can attach titles directly to their wallets as Primary or Secondary titles. Titles are used by players to brag about achievements and show off their unique status.&#x20;

#### Requirement

* `title` must be below 40 characters
* `description` must be below 500 characters

#### Sample

```
{
    ...
    "assetProperties": 
    {
        "title": "Original Community Member",
        "description": "The earliest of Rawrshak community members.",
    },
    ...
}
```

### Lore Subtype

Lore assets can be used as unlockable information. They are used by game developers to add more background information to characters, places, events, or any content. These are used to build a richer world through collectibles and unlockable content.&#x20;

#### Requirement

* `title` must be below 40 characters
* `description` must be below 5000 characters

#### Sample

```
{
    ...
    "assetProperties": 
    {
        "title": "Sample Lore",
        "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
    },
    ...
}
```

### Custom Subtype

Custom text assets are text assets that do not have a specific use case. It is used by game developers who need a text asset that doesn't fit with the subtypes above. These Custom text assets should only be loaded by the game of the creator which knows full well what the asset is.&#x20;

Other game developers shouldn't load these because it's a security risk.&#x20;

#### Requirement

{% hint style="info" %}
No Requirements
{% endhint %}
