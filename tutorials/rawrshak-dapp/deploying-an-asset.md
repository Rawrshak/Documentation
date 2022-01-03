# Deploying an Asset

#### 1. Go to Store Page in Developer Mode

![Click the Store Page](<../../.gitbook/assets/image (25) (1) (1).png>)

#### 2. Select the Content Smart Contract

![Select the Content collection to deploy the asset in](<../../.gitbook/assets/image (20) (1).png>)

#### 3. Click "_New Asset"_

![Click New Asset to create a new asset NFT](<../../.gitbook/assets/image (15) (1).png>)

#### 4. Fill in the Asset Information

![Fill in Asset Information](<../../.gitbook/assets/image (11) (1).png>)

{% hint style="info" %}
Default Rawrshak Image Assets:

Text Asset: [TsBCV3HyMssIZQk0S7MqZht\_zR3e9pBXDWUo0VYAXW4](https://j3aeev3r6izmwcdfbe2exmzkmynx7ti5333javynmuuncvqalvxa.arweave.net/TsBCV3HyMssIZQk0S7MqZht\_zR3e9pBXDWUo0VYAXW4)

Image Asset: [2BmDysofcccaTUbjKJHgr9\_0ImlFadE00yAS\_3E9M00](https://3amyhswkd5y4ogsni3rsrepav7p7iitjivu5cngteajp64j5gngq.arweave.net/2BmDysofcccaTUbjKJHgr9\_0ImlFadE00yAS\_3E9M00)

Audio Asset: [eAnYl\_kEpDtYQA8240b0naau5PP4czOFP1qGg4zazQQ](https://pae5rf7zassdwwcab43ogrxutwtk5zht7bzthbj7lkdihdg2zuca.arweave.net/eAnYl\_kEpDtYQA8240b0naau5PP4czOFP1qGg4zazQQ)

Static 3D Object Asset: [5jpY4ouIl9EXqyep6z0p0S\_6nt87DEfsnsxefAa9cOE](https://4y5fryulrcl5cf5le6u6wpjj2ex7vhw7hmgep3e6zrphybv5odqq.arweave.net/5jpY4ouIl9EXqyep6z0p0S\_6nt87DEfsnsxefAa9cOE)
{% endhint %}

#### 5. Click "Create Asset"

![Click Create Asset](<../../.gitbook/assets/image (9) (1).png>)

![PMetadata json file is propagating for the Subgraph](<../../.gitbook/assets/image (14) (1).png>)

#### 6. Approve and Deploy Transaction

Use Metamask to approve the transaction.&#x20;

![Approve Deployment transaction](<../../.gitbook/assets/image (24) (1).png>)

#### 7. Verify Asset creation

![Verify Asset was created correctly](<../../.gitbook/assets/image (10) (1).png>)

{% hint style="info" %}
The Content subgraph takes a few seconds to a few minutes to update. Please wait for the transaction to succeed and propagate to the subgraph.
{% endhint %}

{% hint style="warning" %}
#### \[Alpha Testnet Known Issue]

Once propagated, if the newly created asset did not populate the information, it means the IPFS metadata wasn't propagated properly and TheGraph was not able to parse the metadata. We're looking to switch from Arweave to IPFS, but it is currently not yet supported on TheGraph. The transition will take some time.

In the meantime, please just redeploy a new asset.&#x20;
{% endhint %}
