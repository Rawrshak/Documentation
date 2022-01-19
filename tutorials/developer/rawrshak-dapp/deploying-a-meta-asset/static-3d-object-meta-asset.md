# Static 3D Object Meta Asset

Please refer to the [3D Static Object Asset ](../../../../developers/in-game-asset-framework/asset-types/static-3d-objects.md)for specific requirements of the Audio Meta Asset Framework before uploading an asset.&#x20;

#### 1. Find or Create the model file that you want to upload.

You can use any 3d modelling software and 3d model object file that is supported by Unity. For testing purposes, please you can find free 3d assets at [Sketchfab](https://sketchfab.com/tags/free).&#x20;

{% hint style="info" %}
A more complex model with high definition textures will be a larger file and will cost more to upload to Arweave. This also increases download time. Please check out [https://prices.ardrive.io/](https://prices.ardrive.io) to determine Arweave upload costs per megabyte or gigabyte.
{% endhint %}

#### 2. Create a Unity project and install the Rawrshak Tools SDK

Please refer to [this tutorial](../../unity/loading-the-rawrshak-tools.md) on how to install the Rawrshak Tools SDK.

#### 3. Move the asset into the Unity project

![Move the folder containing the asset information including the model and necessary textures into the project](<../../../../.gitbook/assets/image (45).png>)

#### 4. Select the model and drag into the scene. Click the model in the scene and  make sure the Transform is set correctly.

![](<../../../../.gitbook/assets/image (18).png>)

{% hint style="info" %}
Make sure that the Transform is set to the following at the start:

Position: (0,0,0)

Rotation: (0,0,0)

Scale: (1,1,1)&#x20;
{% endhint %}

#### 5. Correct the orientation

Make sure that the front of the asset is pointing towards the Z direction. The Z-direction is the Blue Arrow in the scene.

In this case, we flipped the Y axis 180 degrees.

![Oriented the asset](<../../../../.gitbook/assets/image (29).png>)

#### 6. Select the desired Bounding Box and place it in the scene.

Go to Assets\Rawrshak\Tools\Static3dObjectVerfier\Prefabs and select the desired bounding box. In this case, we're going to select Horizontal-Z shape bounding box. Drag that into the scene hierarchy to preserve the position.

{% hint style="info" %}
Make sure to drag the prefab into the Hierarchy Tab, not the Scene tab. This preserves the position.&#x20;

Make sure that the Position of the bounding box matches the initial Position of the prefab by selecting the prefab and comparing its position with the bounding box in the scene. In the example's case, it's position is at (0, 0.5, 0).
{% endhint %}

![Drag Desired bounding box into the hierarchy, into the scene.](<../../../../.gitbook/assets/image (25).png>)

#### 7. Add a Collider to the model

The box collider will be used by the bounding box to determine if the model is within the Asset Framework.&#x20;

Select the largest mesh in the model hierarchy. Select 'Add Component' and search for a Collider component. In this case, we're using a simple box collider.

![Add a Box Collider](<../../../../.gitbook/assets/image (20).png>)

#### 7.B. You may need to adjust the Collider if it doesn't fit the mesh correctly.

![Adjust the Box Collider if necessary](<../../../../.gitbook/assets/image (4).png>)

#### 8. Select the Bounding Box object and set the Target Object to the object that has the box collider. Click "Load Target Object"

![Set the Target Object in the Object Bounds script in the Horizontal Z bounding box object](<../../../../.gitbook/assets/image (47).png>)

#### 9. Re-scale and re-position the object until the object fits into the bounding box (Bounding Box is white)

![Model intersects with the bounding box.](<../../../../.gitbook/assets/image (49).png>)

![Model is firmly inside the bounding box, the bounding box will turn green.](<../../../../.gitbook/assets/image (28).png>)

#### 10. Create a new Empty Game Object to be the parent of the prefab

![Create Empty object](<../../../../.gitbook/assets/image (48).png>)

{% hint style="info" %}
Make sure the position of the new empty object is set to (0,0,0)
{% endhint %}

#### 11. Move the model game object into the parent

![Move the batmobile model into the Batmobile-parent object](<../../../../.gitbook/assets/image (42).png>)

#### 12. Drag and drop the parent object into the Project Folder in order to create a prefab

![Create a Prefab](<../../../../.gitbook/assets/image (37).png>)

#### 13. Set the prefab's asset bundle name

![Set Asset Bundle Name](<../../../../.gitbook/assets/image (27).png>)

#### 14. Open the Asset Bundles Menu, select the Platform Targets, and click Generate Asset Bundles

Go to the menu and select: **Rawrshak -> Asset Bundles**

![Select StandaloneWindows and WebGL, and click the Generate Asset Bundle](<../../../../.gitbook/assets/image (13).png>)

#### 15. View the Asset Bundle Information

![Click the asset bundle and view the information](<../../../../.gitbook/assets/image (17).png>)

#### 16. Upload it to Arweave

Please check out [this tutorial ](../upload-data-to-arweave.md)in order to upload to Arweave.

#### 17. Connect to the Rawrshak Dapp and navigate your way to the Content Contract page

![Create New Asset](<../../../../.gitbook/assets/image (23).png>)

#### 18. Fill in the information about the Asset

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

**Static 3D Object Asset Data**

| Value                     | Description                                                                                                                                                                                                                                                                                                    |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name                      | This 'name' is reserved for the name of the prefab that will be loaded by the game based on the Asset Names in the Asset bundle Menu.                                                                                                                                                                          |
| Engine                    | Engine that this file is packaged for. Currently only supports Unity.                                                                                                                                                                                                                                          |
| Platform                  | The platform refers to the operating system that the game will be running on. Values include android, ios, windows, and webgl.                                                                                                                                                                                 |
| Render Pipeline           | Render Pipeline refers to the specific rendering pipeline that is set for a game engine. Values on this include brp (built-in render pipeline), urp (universal render pipeline), or hdrp (high-definition render pipeline). **For now, we only support the built-in render pipeline so please set it to BRP.** |
| Fidelity                  | Fidelity refers to the asset's quality, ease of download, and ease of loading. Values include low, medium, and high. Definition for Low, Medium, and High Fidelity is to be determined. **For now, please set it to Low.**                                                                                     |
| Shape                     | Shape refers to which type of default asset this object is expecting to replace.Values include small, medium, large, horizontalx, horizontaly, and horizontalz.                                                                                                                                                |
| 3d Static object file URI | Uri to the asset package stored in a decentralized database.                                                                                                                                                                                                                                                   |

{% hint style="info" %}
The Static 3D Object Meta Asset Framework has some requirements for each type and subtype. If your asset doesn't comply with the framework requirements, it may be unloadable by games.&#x20;

Games expect the asset to follow the framework in order for them to load it.
{% endhint %}

To get the prefab name for **Name** section of the Static 3D Object Asset Data, you must open the Asset Bundle Menu, select the bundle name to view the information, and find the correct Asset name.

In this example, it's not _"batmobile"_**,** instead it's "_**assets/batmobile-parent.prefab"**_

![Use the Prefab name for the Name section](<../../../../.gitbook/assets/image (22).png>)

#### 19. Fill in the Asset Information from the static 3d object information above.

![Fill in 3D static object information](<../../../../.gitbook/assets/image (3).png>)

#### 20. Click _Create Asset_ and wait for the Metadata to propagate

![Click Create Asset](<../../../../.gitbook/assets/image (24) (1).png>)

![Wait for Json to propagate ](<../../../../.gitbook/assets/image (37) (1).png>)

#### 21. Wait for the transaction to process and Verify

![Verify for the asset to show up in the contract](<../../../../.gitbook/assets/image (46).png>)

If you're running into problems or find any issues, please join our discord and reach out. We'll help answer questions and fix issues as fast as we can.&#x20;

{% content-ref url="../../../../rawrshak-platform/community-channels/" %}
[community-channels](../../../../rawrshak-platform/community-channels/)
{% endcontent-ref %}
