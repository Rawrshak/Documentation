# 🚧 Audio Meta Asset

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

| Value       | Description                                                                                                                                                                                                         |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name        | Name of the meta asset                                                                                                                                                                                              |
| Description | Description of the meta asset                                                                                                                                                                                       |
| Image       | Image src that will show up on Dapps and other front-ends                                                                                                                                                           |
| Tags        | An array of tags categorizing the asset                                                                                                                                                                             |
| Type        | The Main type of meta asset. In this case, it should be set to Image                                                                                                                                                |
| Subtype     | The subtype of the meta asset. Please refer to the [Image Assets](../../../../developers/in-game-asset-framework/asset-types/image-assets.md) page to get more info on which subtype to select. Defaults to square. |
| NSFW        | Notifies game developers and users of explicit content. Please mark this correctly.                                                                                                                                 |

**Audio Asset Data**

| Value               | Description                                                                                                            |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Name                | The URI to the texture for the specific asset that will be used in-game. This may or may not be the same as the Image. |
| Engine              | Height of the image in pixels                                                                                          |
| Compression         | Width of the image in pixels                                                                                           |
| Audio File URI      | File type of the image (we only support jpeg, svg, and png files                                                       |
| Content Type        |                                                                                                                        |
| Duration (s)        |                                                                                                                        |
| Audio Channel Count |                                                                                                                        |
| Sampling Rate       |                                                                                                                        |

{% hint style="info" %}
The Audio Meta Asset Framework has some requirements for each type and subtype. If your asset doesn't comply with the framework requirements, it may be unloadable by games.&#x20;

Games expect the asset to follow the framework in order for them to load it.
{% endhint %}



// add Audio Asset image

#### 5. Click _Create Asset_ and wait for the Metadata to propagate

![](<../../../../.gitbook/assets/image (24).png>)

![](<../../../../.gitbook/assets/image (37).png>)

#### 6. Wait for the transaction to process and Verify

![Verify asset was created.](<../../../../.gitbook/assets/image (36).png>)

