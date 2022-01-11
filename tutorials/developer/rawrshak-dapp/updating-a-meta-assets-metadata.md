# Updating a Meta Asset's Metadata

#### 1. Go to Store Page in Developer Mode

![Click the Store Page](<../../../.gitbook/assets/image (25) (1) (1) (1).png>)

#### 2. Select the Content Smart Contract

![Select the Content collection to deploy the asset in](<../../../.gitbook/assets/image (20) (1) (1) (1).png>)

#### 3. Select an Asset to edit

![Selecting Smol Ina asset](<../../../.gitbook/assets/image (20).png>)

#### 4. Click "Edit Metadata" button

![Edit Metadata](<../../../.gitbook/assets/image (35).png>)

#### 5. Edit the Metadata that needs to get updated, and Click "Update Asset" button

{% hint style="info" %}
Make sure you put in a valid Pinata API Key and API Secret.
{% endhint %}

In this case, we're updating the "Name" of the prefab inside the uploaded AssetBundle.

![Edit "Name"](<../../../.gitbook/assets/image (38).png>)

![When ready, click the "Update Asset" button.](<../../../.gitbook/assets/image (12).png>)

#### 6. Wait for IPFS to propagate the metadata to the subgraph

![Wait for it to succeed](<../../../.gitbook/assets/image (8).png>)

7\. Verify the metadata

![Info in the metadata is read by TheGraph properly](<../../../.gitbook/assets/image (43).png>)

If the underlined information is blank, it means the subgraph was not able to process the asset. Please edit the metadata again (send the same 'edit metadata' transaction).
