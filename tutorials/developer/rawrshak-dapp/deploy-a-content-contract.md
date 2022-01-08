# Deploy a Content Contract

#### 1. Login using the Developer Wallet

Rawrshak Developer Dapp: [https://alpha.rawrshak.io/#/](https://alpha.rawrshak.io/#/)

![Open the Wallet Tab](<../../../.gitbook/assets/image (21) (1) (1).png>)

![Click the Connect Button and Connect Metamask Wallet](<../../../.gitbook/assets/image (13) (1) (1) (1).png>)

#### 2. Select Developer Mode

![Select Developer Mode](<../../../.gitbook/assets/image (12) (1) (1).png>)

#### 3. Go to Store Page

Store Page: [https://alpha.rawrshak.io/#/store](https://alpha.rawrshak.io/#/store)

![Click the Store Page](<../../../.gitbook/assets/image (25) (1) (1) (1).png>)

#### 4. Click "_New Smart Contract"_

![Select "Create your first Smart Contract" or "New Smart Contract" to create a new smart contract.](<../../../.gitbook/assets/image (2) (1) (1) (1).png>)

#### 5. Fill in the Information and click _Create_

{% hint style="info" %}
Once you click _Create_, it takes 60 seconds for the metadata to be propagated by Pinata so that the Subgraph may read it. Please be patient.&#x20;
{% endhint %}

{% hint style="warning" %}
**IMPORTANT:** If the developer doesn't have an image to use for the contract, they can use the Rawrshak's default content contract image.

Content Contract Image Asset: **https://arweave.net/dI\_5bBKqfDwLUHhQXu\_ubnnBi5f3DcpHQ\_oHmIky1QU**

Link: [dI\_5bBKqfDwLUHhQXu\_ubnnBi5f3DcpHQ\_oHmIky1QU](https://osh7s3asvj6dyc2qpbif537onz44dc4x64g4ur2d7idzrcjs2ucq.arweave.net/dI\_5bBKqfDwLUHhQXu\_ubnnBi5f3DcpHQ\_oHmIky1QU)
{% endhint %}

![Fill in Content Contract information and create contract](<../../../.gitbook/assets/image (16) (1) (1).png>)

![Metadata json file is propagating for the Subgraph](<../../../.gitbook/assets/image (23) (1) (1).png>)

{% hint style="info" %}
Please refer to the Content Contract metadata for more information.

// Todo
{% endhint %}

#### 7. Approve and Deploy Transaction

Use Metamask to approve the transaction.&#x20;

![Approve Deployment transaction](<../../../.gitbook/assets/image (24) (1) (1).png>)

#### 8. Verify Smart Contract creation

![Content Contract deployed properly in the Store Page](<../../../.gitbook/assets/image (5) (1).png>)

![Content Contract information](<../../../.gitbook/assets/image (4) (1) (1) (1).png>)

{% hint style="info" %}
The Content subgraph takes a few seconds to a few minutes to update. Please wait for the transaction to propagate.
{% endhint %}

{% hint style="warning" %}
#### \[Alpha Testnet Known Issue]

Once propagated, if the newly creates smart contract did not populate the information, it means the IPFS metadata wasn't propagated properly and TheGraph was not able to parse the metadata. We're looking to switch from Arweave to IPFS, but it is currently not yet supported on TheGraph. The transition will take some time.

In the meantime, please just redeploy a new smart contract.&#x20;
{% endhint %}
