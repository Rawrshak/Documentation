# Static 3D Objects

The Static 3D Object asset metadata framework creates a guide for static 3d object NFTs such as Trophies and Decorations. his contains the information for non-animated 3d asset NFTs. The proposed metadata format enables game developers to easily parse information for static 3d asset NFTs for in-game use. This static 3d object asset metadata framework should go in the <mark style="color:blue;">`assetProperties`</mark> <mark style="color:blue;"></mark><mark style="color:blue;"></mark> object in the Asset Metadata schema.

Static 3D Object Assets are assets that do not contain animation and must contain a model and materials packaged together.&#x20;

These NFTs can be used in many different manners such as rewarding players with trophies alongside achievements, static character models, furniture, buildings, static animals, automobiles, or whatever type of in-game asset.

## Metadata

### Schema

```
{
    "title": "Asset Properties",
    "type": "object",
    "properties": {
        "textures": {
            "type": "array",
            "description": "An array of Prefab objects"
        }
    }
}

{
    "title": "Prefab",
    "type": "object",
    "properties": {
        "name": {
            "type": "string",
            "description": "name of the prefab that's stored in the package"
        },
        "engine": {
            "type": "string",
            "description": "engine which this package supports. Values include unity, unreal, and godot."
        },
        "platform": {
            "type": "string",
            "description": "platform refers to the operating system that the game is on. Values include android, ios, windows, and webgl."
        },
        "renderPipeline": {
            "type": "string",
            "description": "renderPipeline refers to the specific rendering pipeline that is set for a game engine. values on this include brp (built-in render pipeline), urp (universal render pipeline), or hdrp (high-definition render pipeline)."
        },
        "fidelity": {
            "type": "string",
            "description": "fidelity refers to the asset's quality, ease of download, and ease of loading. Values include low, medium, and high."
        },
        "shape": {
            "type": "string",
            "description": "shape refers to which type of default asset this object is expecting to replace.Values include small, medium, large, horizontalx, horizontaly, and horizontalz."
        },
        "uri": {
            "type": "string",
            "description": "uri to the asset package stored in a decentralized database."
        }
    }
}
```

### Default Properties

| Property        |                          |
| --------------- | ------------------------ |
| Game Engine     | Unity                    |
| Platform        | Windows Standalone 64    |
| Render Pipeline | Built-in Render Pipeline |
| Fidelity        | Low                      |

### Properties

<table><thead><tr><th>Game Engine</th><th data-type="checkbox">Supported</th></tr></thead><tbody><tr><td>Unity</td><td>true</td></tr><tr><td>Unreal</td><td>false</td></tr><tr><td>Godot</td><td>false</td></tr></tbody></table>

<table><thead><tr><th>Render Pipelines</th><th data-type="checkbox">Supported</th></tr></thead><tbody><tr><td>Built-in Render Pipeline (Unity)</td><td>true</td></tr><tr><td>Universal Render Pipeline (Unity)</td><td>false</td></tr><tr><td>High Definition Render Pipeline (Unity)</td><td>false</td></tr></tbody></table>

<table><thead><tr><th>Platforms</th><th data-type="checkbox">Supported</th></tr></thead><tbody><tr><td>Standalone Windows 64 (Unity)</td><td>true</td></tr><tr><td>Android (Unity)</td><td>true</td></tr><tr><td>iOS (Unity)</td><td>true</td></tr><tr><td>WebGL (Unity)</td><td>true</td></tr></tbody></table>

<table><thead><tr><th>Asset Shape</th><th data-type="number">Width</th><th data-type="number">Height</th><th data-type="number">Depth</th></tr></thead><tbody><tr><td>Small Object</td><td>1</td><td>1</td><td>1</td></tr><tr><td>Medium Object</td><td>2</td><td>2</td><td>2</td></tr><tr><td>Large Object</td><td>4</td><td>4</td><td>4</td></tr><tr><td>Horizontal X Object</td><td>2</td><td>1</td><td>1</td></tr><tr><td>Horizontal Y Object</td><td>1</td><td>2</td><td>1</td></tr><tr><td>Horizontal Z Object</td><td>1</td><td>1</td><td>2</td></tr></tbody></table>

{% hint style="warning" %}
There isn't a clear asset specification when it comes to levels of fidelity. Currently, only "low" is supported.
{% endhint %}

<table><thead><tr><th>Levels of Fidelity</th><th data-type="checkbox">Supported</th></tr></thead><tbody><tr><td>Low</td><td>true</td></tr><tr><td>Medium</td><td>false</td></tr><tr><td>High</td><td>false</td></tr></tbody></table>

## Asset Requirement

Static 3D objects have a few specific requirements. The asset must be oriented in the correct location and located at the correct position. Once the asset is loaded in-game, it will instantiated in the orientation, scaling, and location of a default asset.&#x20;

#### Asset Orientation

The asset's prefab must be oriented towards the +Z direction. The default camera is placed at (0,1,3) and oriented towards (0,0,0). The prefab's "front" must be facing the camera.

#### Asset Location

The asset's prefab must be defaulted to the origin. The asset must be above the origin (0,0,0). The testing bounding boxes and default assets are expecting the asset to be at the origin before the prefab is packaged.&#x20;

#### Verification

The Rawrshak Unity tools has testing bounding boxes that helps the asset creator determine if their 3d asset fits within the bounds of the expected asset shape. It will help make sure the asset is within the asset shape framework before it is set for packaging.

## Subtypes

We define two static 3d object NFT frameworks, each with a different use case. Gamers should expect them to be used in a game for its designated use. The subtypes are divided based on use-case.

### Trophy Subtype

Trophies are static 3d objects that are rewarded to users for achievements in-game.&#x20;

#### Requirement

* `shape` must be "small"

#### Sample

```
{
    ...
    "assetProperties": 
    [
        {
            "name": "rawr-trophy",
            "engine": "unity",
            "renderPipeline": "brp",
            "platform": "windows",
            "fidelity": "low",
            "shape": "small",
            "uri": "arweave.net/<transaction-id>"
        },
        {
            "name": "rawr-trophy",
            "engine": "unity",
            "renderPipeline": "brp",
            "platform": "ios",
            "fidelity": "low",
            "shape": "small",
            "uri": "arweave.net/<transaction-id>"
        },
        {
            "name": "rawr-trophy",
            "engine": "unity",
            "renderPipeline": "brp",
            "platform": "android",
            "fidelity": "low",
            "shape": "small",
            "uri": "arweave.net/<transaction-id>"
        },
        {
            "name": "rawr-trophy",
            "engine": "unity",
            "renderPipeline": "brp",
            "platform": "webgl",
            "fidelity": "low",
            "shape": "small",
            "uri": "arweave.net/<transaction-id>"
        },
        {
            "name": "rawr-trophy",
            "engine": "unity",
            "renderPipeline": "brp",
            "platform": "windows",
            "fidelity": "medium",
            "shape": "small",
            "uri": "arweave.net/<transaction-id>"
        },
        {
            "name": "rawr-trophy",
            "engine": "unity",
            "renderPipeline": "brp",
            "platform": "high",
            "fidelity": "medium",
            "shape": "small",
            "uri": "arweave.net/<transaction-id>"
        }
    ],
    ...
}
```

### Decoration Subtype

Decorations are static 3d objects that are acquired by users. There is no specific shape requirement for these assets. They can be loaded anywhere and placed anywhere. There's no specific usage designated for this type of static 3d object.

#### Requirement

{% hint style="info" %}
No Requirements
{% endhint %}

#### Sample

```
{
    ...
    "assetProperties": 
    [
        {
            "name": "rawr-figure",
            "engine": "unity",
            "renderPipeline": "brp",
            "platform": "windows",
            "fidelity": "low",
            "shape": "small",
            "uri": "arweave.net/<transaction-id>"
        }
    ],
    ...
}
```
