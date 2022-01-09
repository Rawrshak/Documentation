# Pinata

Currently, the Rawrshak (Alpha release) is using IPFS to store the Meta Asset's metadata files. The reason that we are using IPFS instead of Arweave is because TheGraph, as of December 2021, does not yet support reading JSON files from Arweave. Our subgraphs read and process an asset's metadata in order to build a richer data set.&#x20;

We therefore require a Pinata account when creating a Content Contract and Meta Asset when launched in the Developer Dapp. The plan is to eventually store all metadata on Arweave when The Graph <> Arweave integration is released.&#x20;

In the meantime, please use this tutorial to create and use the Pinata account for IPFS.

#### Requirements:

* Email

#### 1. Register for a [Pinata ](https://www.pinata.cloud)Account

![Go to Pinata: www.pinata.cloud](<../../../.gitbook/assets/image (11) (1).png>)

![Register for Pinata](<../../../.gitbook/assets/image (31) (1).png>)

{% hint style="info" %}
Pinata gives you 1GB free of pinning service which is more than enough for uploading asset metadata at about 200 bytes to 2kb per metadata file.
{% endhint %}

#### 2. Create an API Key

In the profile button on the top right, open the dropdown menu and select _API Keys_

![API Keys](<../../../.gitbook/assets/image (20).png>)

#### 3. Set the API Key Settings and click Create

Set "Admin" to true and set Key Name

![Set API Key Settings](<../../../.gitbook/assets/image (19) (1).png>)

#### 4. Copy newly generated Pinata API Key somewhere safe

![Click "Copy All" and paste the keys somewhere safe.](<../../../.gitbook/assets/image (15).png>)

The **API Key** and **API Secret** will be used in the Rawrshak app. Please keep these items safe. They will not be accessible after you click "Done"

#### 5. \[Optional] Revoking API Key Access

If your API Keys become compromised, you can simply Revoke access to these keys.&#x20;

![Revoking Access](<../../../.gitbook/assets/image (10).png>)

![Revoke Key](<../../../.gitbook/assets/image (21) (1).png>)

#### Go to the next tutorial to learn how to load the Arweave Wallet to your ArDrive account for easy asset management.
