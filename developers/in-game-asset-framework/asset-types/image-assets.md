# Image Assets

The Image Asset metadata framework creates a guide for image-based NFTs such as Logos, Sprays, Decals, Emblems, Banners, and other image assets. It contains the necessary information and specific requirements. This image asset metadata framework should go in the <mark style="color:blue;">`assetProperties`</mark> <mark style="color:blue;"></mark><mark style="color:blue;"></mark> object in the Asset Metadata schema.

Image NFTs have many different use cases both in-game and outside of a game. Game developers can reward players with unique art related to their intellectual property that gamers can then show off. As gamers take these assets to other games, it then functions as an advertisement. It enables cross pollination of playerbases between games in the Rawrshak ecosystem.

## Metadata

### Schema

```
{
    "title": "Asset Properties",
    "type": "object",
    "properties": {
        "textures": {
            "type": "array",
            "description": "An array of texture objects"
        }
    }
}

{
    "title": "Texture",
    "type": "object",
    "properties": {
        "uri": {
            "type": "string",
            "description": "link to the texture object"
        },
        "height": {
            "type": "int",
            "description": "Height of the texture in Pixels"
        },
        "width": {
            "type": "int",
            "description": "Width of the texture in Pixels"
        },
        "contentType": {
            "type": "string",
            "description": "content type. Can be image/png, image/jpg, image/svg"
        }
    }
}
```

## Subtypes

The subtypes are categorized based on asset requirements instead of use case because images can be re-used in many different use cases as long as they fit the specific asset requirements. The use case is limited by the shape of the image, and thus, we use the shape to categorize Image assets.

### Square Subtype

Square image assets are the simplest of image assets. They are probably the most common and can be used in-game for many different reasons such as decals, sprays, guild emblems, etc. They can be used to show off a gamer's affiliations or group.&#x20;

#### Requirement

* aspect ratio must be 1:1
* `textures` array must contain a 256x256 pixel image as the default asset.
* Texture sizes may range from 48x48 to 1024x1024 pixels

#### Sample

```
{
    ...
    "assetProperties": 
    [
        {
            "uri": "arweave.net/<tx>",
            "height": 256,
            "width": 256,
            "contentType": "image/png"
        },
        {
            "uri": "arweave.net/<tx>",
            "height": 512,
            "width": 512,
            "contentType": "image/png"
        },
        {
            "uri": "arweave.net/<tx>",
            "height": 1024,
            "width": 1024,
            "contentType": "image/png"
        }
    ],
    ...
}
```

### Horizontal Banner Subtype

Horizontal Banner assets have a more limited use case than the square image asset. Horizontal banner assets can be used in situations where the asset spans across the screen horizontally.

#### Requirement

* aspect ratio must be 2:1
* `textures` array must contain a 256x128 pixel image as the default asset.
* Texture sizes may range from 96x48 to 1024x512 pixels

#### Sample

```
{
    ...
    "assetProperties": 
    [
        {
            "uri": "arweave.net/<tx>",
            "height": 128,
            "width": 256,
            "contentType": "image/png"
        },
        {
            "uri": "arweave.net/<tx>",
            "height": 256,
            "width": 512,
            "contentType": "image/png"
        },
        {
            "uri": "arweave.net/<tx>",
            "height": 512,
            "width": 1024,
            "contentType": "image/png"
        }
    ],
    ...
}
```

### Vertical Banner Subtype

Similar to horizontal banner assets, Vertical Banner assets have a more limited use case than the square image asset. Vertical banner assets can be used in situations where the asset spans across the screen vertically.

#### Requirement

* aspect ratio must be 1:2
* `textures` array must contain a 128x256 pixel image as the default asset.
* Texture sizes may range from 48x96 to 512x1024 pixels

#### Sample

```
{
    ...
    "assetProperties": 
    [
        {
            "uri": "arweave.net/<tx>",
            "height": 256,
            "width": 128,
            "contentType": "image/png"
        },
        {
            "uri": "arweave.net/<tx>",
            "height": 512,
            "width": 256,
            "contentType": "image/png"
        },
        {
            "uri": "arweave.net/<tx>",
            "height": 1024,
            "width": 512,
            "contentType": "image/png"
        }
    ],
    ...
}
```

### Custom Subtype

The custom subtype doesn't have a requirement for aspect ratio and doesn't have a default texture requirement dimension. The creator is free to choose what they want to use in their games and NFT. The custom subtype, however, should not be loadable in other games aside from the creator's game. The dimensions must still be a power of 2.

#### Requirement

* The dimensions must still be a power of 2.

#### Sample

```
{
    ...
    "assetProperties": 
    [
        {
            "uri": "arweave.net/<tx>",
            "height": 128,
            "width": 512,
            "contentType": "image/png"
        }
    ],
    ...
}
```
