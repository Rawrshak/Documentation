# Audio Meta Asset

## Under Construction!

{% hint style="info" %}
This content is coming soon! We're working diligently to create this content for our community!

Are you a technical writer who'd like to make the Rawrshak Community better for everyone? Help write this page! Please reach out to <mark style="color:orange;">contact@rawrshak.io</mark>
{% endhint %}

Please refer to the [Audio Asset ](../../../../developers/in-game-asset-framework/asset-types/audio-assets.md)for specific requirements of the Image Meta Asset Framework before uploading an asset.&#x20;

#### 1. Find an audio file that you want to upload.

{% file src="../../../../.gitbook/assets/ChallengeAccepted.mp3" %}
HIMYM - Challenge Accepted
{% endfile %}

#### 1.A. (Optional) You may also package the asset in a Unity Asset Bundle

Follow the tutorial [here ](../../unity/packaging-an-asset/audio-asset.md)on how to package an audio file.

#### 2. Upload it to Arweave

Please check out [this tutorial ](../upload-data-to-arweave.md)in order to upload to Arweave.

#### 3. Connect to the Rawrshak Dapp and navigate your way to the Content Contract page

![Create New Asset](<../../../../.gitbook/assets/image (23).png>)

#### 4. Fill in the information about the Asset

| Value                    | Description                                                                                                                                                                                                         |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Pinata API Key & Secret  | This is needed for the metadata to be uploaded to IPFS. Please see the [Pinata tutorial](../../setup/pinata.md) to set this up.                                                                                     |
| Name                     | Name of the meta asset                                                                                                                                                                                              |
| Description              | Description of the meta asset                                                                                                                                                                                       |
| Image                    | Image src that will show up on Dapps and other front-ends                                                                                                                                                           |
| Tags                     | An array of tags categorizing the asset                                                                                                                                                                             |
| Max Supply               | The maximum instances for this asset that can ever be minted. If left at 0, it will automatically be converted to UINT256\_MAX.                                                                                     |
| Royalty Receiver Address | The ethereum address that royalty fees will be sent to. If this is set to the Zero Address, the asset royalty will fall back to the default Content Contract royalty.                                               |
| Royalty Rate             | The percent royalty the developer will receive when this asset is traded in a marketplace that supports royalty fees.                                                                                               |
| Type                     | The Main type of meta asset. In this case, it should be set to Image                                                                                                                                                |
| Subtype                  | The subtype of the meta asset. Please refer to the [Image Assets](../../../../developers/in-game-asset-framework/asset-types/image-assets.md) page to get more info on which subtype to select. Defaults to square. |
| NSFW                     | Notifies game developers and users of explicit content. Please mark this correctly.                                                                                                                                 |

**Audio Asset Data**

| Value               | Description                                                                                                                                                                                                                                                                                                              |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Name                | Name of the file. If packaged in an asset bundle, name of the audio clip in the asset bundle as shown using the Rawrshak's AssetBundle Window in Unity                                                                                                                                                                   |
| Engine              | Engine that this file is packaged for. Currently only supports Unity.                                                                                                                                                                                                                                                    |
| Compression         | This specifies the compression algorithm used when the audio file was packaged. This information is used by the game engine. For Unity, these values can be PCM, ADPCM, or Compressed. Compressed is the default common value. If the file is directly uploaded instead of packaged by the game engine, set this to RAW. |
| Audio File URI      | The URI to the audio asset bundle or audio file for the specific asset that will be used in-game.                                                                                                                                                                                                                        |
| Content Type        | File type of the image (we only support wav, mp3, ogg, and aiff files)                                                                                                                                                                                                                                                   |
| Duration (ms)       | Duration of the audio clip in milliseconds.                                                                                                                                                                                                                                                                              |
| Audio Channel Count | Number of audio channels for the audio clip.                                                                                                                                                                                                                                                                             |
| Sampling Rate (Hz)  | The sampling rate of audio clip.                                                                                                                                                                                                                                                                                         |

{% hint style="info" %}
The Audio Meta Asset Framework has some requirements for each type and subtype. If your asset doesn't comply with the framework requirements, it may be unloadable by games.&#x20;

Games expect the asset to follow the framework in order for them to load it.
{% endhint %}

![Create Audio Meta Asset information](<../../../../.gitbook/assets/image (40).png>)

#### 5. Click _Create Asset_ and wait for the Metadata to propagate

![](<../../../../.gitbook/assets/image (24).png>)

![](<../../../../.gitbook/assets/image (37).png>)

#### 6. Wait for the transaction to process and Verify

![Challenge Accepted audio file was added](<../../../../.gitbook/assets/image (31).png>)
