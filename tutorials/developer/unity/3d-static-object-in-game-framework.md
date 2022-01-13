# 3D Static Object In-game Framework

#### 1. Load Folder containing the asset into the Package Loader Project

![Load Folder containing assets (textures, mesh, materials, etc)](<../../../.gitbook/assets/image (29) (2).png>)

{% hint style="info" %}
Developer may import .obj files, .fbx file, or 3d software package file that is supported by Unity.
{% endhint %}

#### 1.a Extract the Materials from the prefab (if necessary)

If you select the 3D Object file, (in this case, a .OBJ file), some materials may need to be remapped.&#x20;

In this case, in the inspector, open the 'materials' tab and click the "**Extract Materials...**" to extract the materials. It should automatically remap the materials. Although, manual remapping may be necessary.

![Missing Materials](<../../../.gitbook/assets/image (6) (1).png>)

![After clicking the "Extract Materials"](<../../../.gitbook/assets/image (5) (1).png>)

![Extracted Materials and remapped to the mesh](<../../../.gitbook/assets/image (23) (1) (1).png>)

#### 2. Drag the 3D Asset into the Scene, set orientation and position

Make sure the asset is facing the +Z axis and is initially positioned at (0,0,0).

![Asset In the scene](<../../../.gitbook/assets/image (10) (1).png>)

#### 3. Select Static 3D Object Verifier Prefab and drag onto the scene

Go to: the Assets\Rawrshak\Tools\Static3dObjectVerfier\Prefabs&#x20;

Select the default asset shape you want for this asset.

In this tutorial, we'll use HorizontalZ prefab.

![HorizontalZ Prefab](<../../../.gitbook/assets/image (1).png>)

The prefabs will vary in scale and shape.&#x20;

Please note the Object Bounds script in the inspector.&#x20;

#### 4. Resize and Orient 3d asset to fit inside the prefab

#### 4.1 Add Box Collider to the model with the Mesh Renderer

![](<../../../.gitbook/assets/image (31) (2).png>)

Click the object with the mesh renderer to open the inspector. In this case, it's the '_default'_ object inside SCI\_FRS_\__13\_HD game object.&#x20;

Scroll to the bottom of the inspector on the right and click "Add Component". Type "Box Collider" and select the box collider. It should be added to this object as shown in the image above.

The box collider is the green outline shown above.

{% hint style="info" %}
The "Collider" should, as much as possible, be tight to the asset. Feel free to use other colliders or adjust the collider if it seems too big. The model may also have issues if the collider looks is extremely incorrect.&#x20;
{% endhint %}

#### 4.2 Orient and Resize to fit inside the Prefab

Make sure both HorizontalZObjectBounds and SCI\_FRS\_13\_HD objects are enabled.

Select the HorizontalZObjectBounds to open it's inspector. Set the "**Target Object**" to the object with the box collider. In this case, the '**default'** object inside SCI\_FRS\_13\_HD.&#x20;

Click **Load Target Object** button.

![Set the Target Object](<../../../.gitbook/assets/image (7) (1).png>)

{% hint style="info" %}
Make sure that the '**default**' asset has a _collider_ component.
{% endhint %}

#### 4.3 Verify Asset

Make sure that the HorizontalZObjectBounds is at (0,0.5,0) with a scale of (1,1,2).

If the asset intersects or is completely outside the object bounds, it will turn red.

![Invalid Asset](<../../../.gitbook/assets/image (30) (2).png>)

Make sure that the asset is oriented correctly and is scaled to completely fit inside the bounding box.&#x20;

![Fits inside the Bounding Box](<../../../.gitbook/assets/image (11) (2).png>)

#### 5. Finished!

When it's done and you're satisfied with how the asset looks in-game, it is ready for packaging!
