# Custom Subgraph Query

### Requirements

* Familiarity with GraphQL queries and The Graph queries (see [https://thegraph.com/docs/en/developer/graphql-api/](https://thegraph.com/docs/en/developer/graphql-api/))
* A Unity project with the Rawrshak SDK installed

{% hint style="info" %}
Our examples are only for Rawrshak's Contents and Exchange subgraphs. A developer can create custom queries for our subgraphs.

A developer can also retrofit this tutorial for any GraphQL source or any subgraph.
{% endhint %}

### Tutorial

#### 1. Create a folder for custom graphql queries

#### 2. Inside that folder, create a "Resources" folder and a "Scripts" folder

#### 3. In the Resources folder, create a text file that contains the GraphQL query

Filename: `GetAssetName.txt`

```
query GetAssetName {{
    asset ( id: "{0}-{1}" ) {{
        name
    }}
}}
```

Notes:

* GraphQL query syntax "{" and "}" must be replaced with "{{" and "}}"
* Query parameters are indexed. `{0}` and `{1}` indicate the first parameter and second parameter for the query.

#### 4. Create Query Script

```
using System;
using System.Collections;
using System.Collections.Generic;
using System.Threading.Tasks;
using System.Numerics;
using UnityEngine;
using UnityEngine.Networking;
using GraphQlClient.Core;
using Rawrshak;

public class GetAssetName: QueryBase
{
    public static async Task<ReturnData> Fetch(string contractAddress, string tokenId) {
        // Load query if this is the first Fetch
        string query = LoadQuery("GetAssetName"); // Where GetAssetName is the filename.
        
        // Load the query parameters
        string queryWithArgs = String.Format(query, contractAddress.ToLower(), tokenId);

        // Post query
        string returnData = await PostAsync(Subgraph.Instance.contentsSubgraphUri, queryWithArgs);

        // Parse data
        return JsonUtility.FromJson<ReturnData>(returnData);
    }

    [Serializable]
    public class ReturnData
    {
        public DataObject data;
    }

    [Serializable]
    public class DataObject 
    {
        public AssetData asset;
    }

    [Serializable]
    public class AssetData 
    {
        public string name;
    }
}
```

Notes:

* This script should inherit from `QueryBase`
* `queryWithArgs` format string should match the number of input in the `GetAssetName.txt`
* `Subgraph` object is in the Rawrshak SDK. If pointing to a different subgraph, replace this with the correct subgraph source uri
* The ReturnData object should match the serializable json object returned by the query.
* Please check out the [Content ](../../developers/rawrshak-subgraphs/entities/content-subgraph.md)and [Exchange ](../../developers/rawrshak-subgraphs/entities/exchange-subgraph.md)Pages for more info.

#### 5. Use the Custom Query

To use the query:

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class GetAssetInfoScript : MonoBehaviour
{
    // Input
    public string contentContractAddress;
    public int tokenId;

    // Return Value
    public GetAssetName.ReturnData data;

    // Start is called before the first frame update
    async void Start()
    {
        // Test Query
        data = await GetAssetName.Fetch(contentContractAddress, tokenId.ToString());
    }
}
```
