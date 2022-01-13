# Image Meta Asset

Please refer to the [Image Asset ](../../../../developers/in-game-asset-framework/asset-types/image-assets.md)for specific requirements of the Image Meta Asset Framework before uploading an asset.&#x20;

#### 1. Find an image that you want to upload.

![Rocketship - Note: This is just a random image. We don't own this image at all.](../../../../.gitbook/assets/rocketship.jpg)

#### 2. Upload it to Arweave

Please check out [this tutorial ](../upload-data-to-arweave.md)in order to upload to Arweave.

#### 3. Connect to the Rawrshak Dapp and navigate your way to the Content Contract page

![Create New Asset](<../../../../.gitbook/assets/image (23).png>)

#### 4. Fill in the information about the Asset

| Value                         | Description                                                                                                                                                                                                         |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Pinata API Key & Secret       | This is needed for the metadata to be uploaded to IPFS. Please see the [Pinata tutorial](../../setup/pinata.md) to set this up.                                                                                     |
| Name                          | Name of the meta asset                                                                                                                                                                                              |
| Description                   | Description of the meta asset                                                                                                                                                                                       |
| Image                         | Image src that will show up on Dapps and other front-ends                                                                                                                                                           |
| Tags                          | An array of tags categorizing the asset                                                                                                                                                                             |
| Max Supply                    | The maximum instances for this asset that can ever be minted. If left at 0, it will automatically be converted to UINT256\_MAX.                                                                                     |
| Royalty Receiver Address      | The ethereum address that royalty fees will be sent to. If this is set to the Zero Address, the asset royalty will fall back to the default Content Contract royalty.                                               |
| Royalty Rate                  | The percent royalty the developer will receive when this asset is traded in a marketplace that supports royalty fees.                                                                                               |
| Type                          | The Main type of meta asset. In this case, it should be set to Image                                                                                                                                                |
| Subtype                       | The subtype of the meta asset. Please refer to the [Image Assets](../../../../developers/in-game-asset-framework/asset-types/image-assets.md) page to get more info on which subtype to select. Defaults to square. |
| NSFW                          | Notifies game developers and users of explicit content. Please mark this correctly.                                                                                                                                 |
| Image URI (Asset Data)        | The URI to the texture for the specific asset that will be used in-game. This may or may not be the same as the Image.                                                                                              |
| Height in Pixels (Asset Data) | Height of the image in pixels                                                                                                                                                                                       |
| Width in Pixels (Asset Data)  | Width of the image in pixels                                                                                                                                                                                        |
| Content Type (Asset Data)     | File type of the image (we only support jpeg, svg, and png files)                                                                                                                                                   |

{% hint style="info" %}
The Image Meta Asset Framework has some requirements for each type and subtype. If your asset doesn't comply with the framework requirements, it may be unloadable by games.&#x20;

Games expect the asset to follow the framework in order for them to load it.
{% endhint %}

![Fill in the Image information](<../../../../.gitbook/assets/image (29).png>)

#### 5. Click _Create Asset_ and wait for the Metadata to propagate

![](<../../../../.gitbook/assets/image (24).png>)

![](<../../../../.gitbook/assets/image (37).png>)

#### 6. Wait for the transaction to process and Verify

![Verify asset was created.](<../../../../.gitbook/assets/image (36).png>)

