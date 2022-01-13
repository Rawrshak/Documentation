# Meta Asset Framework

The Meta Asset Framework is a guide for asset creators to follow in order for their assets to be loadable by games. Game developers expect meta assets to be within the framework for the asset type it's loading. Before loading, the game must verify the asset against the asset type requirements. If verification fails, the game cannot load the user's asset.

The meta asset framework gives game developers and content creators a guide to follow so that their content may traverse different worlds. With this "Deploy Once" strategy, asset launch scalability increases and the need to collaborate with other game developers individually is removed.

From the game developer's perspective, by enabling asset interoperability within their game, the value of their game increases. Players are more inclined to spend time in their game and show off their collections.

### Limitations

#### Game Developer

It is up to the game developer on what type of assets they deem can be loadable. Usable assets depend on the type of game. For example, a 2D side scroller may be able to load Text, Image, and Audio assets, but they cannot load 3D assets.&#x20;

The game developer may also opt to only load assets from content contracts that they own or are official. They may also choose to only load assets that are not NSFW.&#x20;

The game engine SDK has capabilities to filter out assets from a user's wallet based on factors such as asset type, asset subtype, contract addresses, and other asset properties. The game developer may also implement their own filter using Rawrshak's subgraphs.

{% hint style="info" %}
Instructions on how to filter for assets using Rawrshak's subgraphs can be found [here](broken-reference).
{% endhint %}

#### Asset Creator

Asset creators must make sure their assets adhere to the asset framework in order for their assets to be loadable. Game developers will make sure assets that are loaded do not break the gameplay, nor provide any in-game advantage.&#x20;

The ecosystem may create a list of banned assets that game developers can check against. If your assets get put on this list, it may lose value in the eyes of gamers.&#x20;
