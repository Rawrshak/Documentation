# Asset Metadata

The asset metadata is the common metadata schema for all Rawrshak assets. This metadata contains common information about all assets and will be used by all front-end applications. This metadata schema is what the game engine SDKs expect in order for them to load the asset. Any deviation from this metadata will make the asset unloadable.

{% hint style="warning" %}
The schema is still under development and may change over time before public release. For more information, please refer to [_Public Asset Metadata_](https://github.com/Rawrshak/Asset-Frameworks/blob/main/Drafts/PublicAssetMetadata.md)_._
{% endhint %}

## Metadata

### Schema

```
{
    "title": "Token Public Metadata",
    "type": "object",
    "properties": {
        "name": {
            "type": "string",
            "description": "Name of the asset"
        },
        "description": {
            "type": "string",
            "description": "Description or lore of the asset which this token represents"
        },
        "image": {
            "type": "string",
            "description": "A URI pointing to a resource with mime type image/* of an asset this token represents. Consider making any images at a width between 320 and 1080 pixels and aspect ratio between 1.91:1 and 4:5 inclusive."
        },
        "tags": {
            "type": "array",
            "description": "An array of strings that will be used as Tags for the content contract metadata."
        },
        "type": {
            "type": "string",
            "description": "The type of asset that the token is representing. This informs the hidden data reader on how to parse the token's hidden metadata. Values may be text, image, audio, static_object, or other future types that is added."
        },
        "subtype": {
            "type": "string",
            "description": "The subtype of asset that the token is representing. The value depends on what the primary type of the asset is. This informs the hidden data reader if there are any special or custom data in the metadata that it can use. It will also inform the game on how to ideally use the asset."
        },
        "nsfw": {
            "type": "boolean",
            "description": "NSFW indicates that a particular asset contains sexually explicit or other adult content."
        },
        "assetProperties": {
            "type": "object",
            "description": "Asset properties that are specific to the type and subtype of the asset that is necessary to present the asset in-game."
        },
        "devProperties": {
            "type": "object",
            "description": "Arbitrary properties. Values may be strings, numbers, object or arrays. This is data specific to the creator's game or project."
        }
    }
}
```

### Sample

```
{
    "name": "Rawrshak Big Achievement title",
    "description": "Rawrshak Big Achievement title",
    "image": "https://arweave.net/B8P-_xmgnbZZhkAuR3Nty3zeQpsWtewV4MuzHV2Zd9A",
    "tags": [
        "Rawrshak",
        "Title",
        "Big Achievement"
    ],
    "type": "text",
    "subtype": "title",
    "nsfw": false,
    "assetProperties": 
    {
        "title": "Rawrshak Big Achiever",
        "description": "Success in Big Challenge. Player defeated Big Boss."
    },
    "devProperties":
    {
        "experience-gain": 50,
        "level-requirement": 10,
        "unlock-bonus": "AA4424"
    }
}
```
