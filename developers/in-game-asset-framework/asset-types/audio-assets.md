# Audio Assets

The Audio Asset metadata framework creates a guide for audio-based NFTs such as sound effects, character lines, shouts, and background music. It contains the necessary information and specific requirements that allows game developers to easily parse the information and load the audio file. This audio asset metadata framework should go in the <mark style="color:blue;">`assetProperties`</mark> <mark style="color:blue;"></mark><mark style="color:blue;"></mark> object in the Asset Metadata schema.

Audio NFTs can be used in many different manners such as rewarding players with short sound effects, character lines, background music, shouts, quotes, etc. In-game audio NFTs can add an extra layer of customization for gamers.&#x20;

## Metadata

### Schema

```
{
    "title": "Asset Properties",
    "type": "object",
    "properties": {
        "audio": {
            "type": "object",
            "description": "An array of texture objects"
        }
    }
}

{
    "title": "Audio",
    "type": "object",
    "properties": {
        "name": {
            "type": "string",
            "description": "name of the AudioClip that's stored in the package"
        },
        "engine": {
            "type": "string",
            "description": "engine which this package supports. Values include none, unity, and unreal. none refers to the raw, uncompressed, unpackaged file for use by dapps."
        },
        "compression": {
            "type": "string",
            "description": "specifies the compression algorithm used when the audio file was packaged. For Unity, these values can be PCM, ADPCM, or Compressed. Compressed is the default common value."
        },
        "uri": {
            "type": "string",
            "description": "uri to the downloadable file or audio package"
        },
        "contentType": {
            "type": "string",
            "description": "content type. Can be audio/mpeg, audio/wav, audio/ogg, audio/x-aiff"
        },
        "duration": {
            "type": "int",
            "description": "duration of the audio clip in milliseconds"
        },
        "channelCount": {
            "type": "int",
            "description": "channel count of the audio clip"
        },
        "sampleRate": {
            "type": "int",
            "description-hz": "sample rate of the audio clip in Hz"
        },
    }
}
```

## Subtypes

We define five Audio-based NFT frameworks, each with a different use case. Gamers should expect them to be used in a game for its designated use. However, these <mark style="color:blue;">`subtypes`</mark> are merely guides for game developers, they are free to use them wherever they want to in their game.

### Sound Effect Subtype

Sound effect assets are short audio clips used for sound effects.&#x20;

#### Requirement

* Maximum `duration` of 1 second.
* When loaded by a game, it should be kept in memory as it can be attached to any in-game asset.&#x20;

#### Sample

```
{
    ...
    "assetProperties": 
    [
        {
            "name": "unlockEffect.wav",
            "engine": "none",
            "compression": "raw",
            "uri": "arweave.net/<transaction-id>",
            "contentType": "audio/wav",
            "duration": "500",
            "channelCount": 1,
            "sampleRate": 44100
        }
    ],
    ...
}
```

### Shout Subtype

Shout assets are short character lines used for quick taunts, player communication, or character reactions.&#x20;

#### Requirement

* Maximum `duration` of 2 seconds.
* When loaded by a game, it should be kept in memory as they can be used by the player at any time.

#### Sample

```
{
    ...
    "assetProperties": 
    [
        {
            "name": "Rage.wav",
            "engine": "none",
            "compression": "raw",
            "uri": "arweave.net/<transaction-id>",
            "contentType": "audio/wav",
            "duration": "1200",
            "channelCount": 1,
            "sampleRate": 44100
        }
    ],
    ...
}
```

### Character Line Subtype

Character line assets are longer character lines used for taunts, reactions, or other special character actions. Character line assets are optional to keep in memory or loaded on demand as necessary. The game developer may allow players to say these lines at any time or may have specific locations/situations where they can be loaded and played.&#x20;

#### Requirement

* Maximum `duration` of 10 seconds.

#### Sample

```
{
    ...
    "assetProperties": 
    [
        {
            "name": "ToInfintyAndBeyond.mp3",
            "engine": "none",
            "compression": "raw",
            "uri": "arweave.net/<transaction-id>",
            "contentType": "audio/mp3",
            "duration": "7800",
            "channelCount": 1,
            "sampleRate": 44100
        }
    ],
    ...
}
```

### Background Music Subtype

Background Music assets are longer audio NFTs that may be sold by game developers or unlocked in-game. This allows gamers to take music that they like from a game and use them in any game they wish to play. Game developers may opt to allow gamers to play their own background music playlist in-game.

This asset is loaded per gamer and is not shared during gameplay. They are loaded on demand and shouldn't be kept in memory.

#### Requirement

* Maximum `duration` of 300 seconds.

#### Sample

```
{
    ...
    "assetProperties": 
    [
        {
            "name": "flute.wav",
            "engine": "none",
            "compression": "raw",
            "uri": "arweave.net/<transaction-id>",
            "contentType": "audio/wav",
            "duration": "280000",
            "channelCount": 1,
            "sampleRate": 44100
        }
    ],
    ...
}
```

### Custom Subtype

The custom subtype doesn't have a requirement for duration or how it's loaded by the game. The creator is free to create this asset however they see fit. The custom subtype, however, should not be loadable in other games aside from the creator's game.&#x20;

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
            "name": "custom.wav",
            "engine": "none",
            "compression": "raw",
            "uri": "arweave.net/<transaction-id>",
            "contentType": "audio/wav",
            "duration": "57800",
            "channelCount": 1,
            "sampleRate": 44100
        }
    ],
    ...
}
```

