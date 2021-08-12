---
layout: documentation
---

#### . Documentation
# .vinv Format

<span class="heighlight">vinv</span> compliant inventory data is transferred in the `.vinv` data format. The file extension is not mandatory. However, it should be chosen in order to inform the processing programs that the content complies with the given <span class="heighlight">vinv</span> specification.

To be compliant with the <span class="heighlight">vinv</span> specification, a `.vinv` file must meet the defined technical and content requirements.

<p class="h5">
  <span class="subtitle point-before hp">Format</span>
</p>
<h2 class="m-0">JavaScript Object Notation</h2>

`.vinv` files contain a JSON object.

*JSON (JavaScript Object Notation) is a lightweight data-interchange format. It is easy for humans to read and write. It is easy for machines to parse and generate.* [json.org](https://www.json.org/)

To keep the file size as small as possible, recurring objects like "tree data" are represented as tuples in <span class="heighlight">vinv</span>. Get familiar with [tuples](https://json-schema.org/understanding-json-schema/reference/array.html#tuple-validation)

```javascript
// example .vinv file

{
    "v": "0.1-alpha",    // Version of vinv format
    "server": {   // Server
        "url": "https://vinv.io/"
    },   // Server
    "inventory":[   // URL-friendly unique ID
        [ tree1, tree2, ... ],   // Array of tree objects
        [ treeHistorie1, treeHistorie2, ... ]  // Array of changes made to the Tree object above
    ]
}
```

### Version

Currently the first version of vinv is under development. This is your chance to participate in the development of the standard from the very beginning. [Join the vinv group](/group)

| Version Code        | Status  | Documentation |
| ------------- | ------------- |:-----:|
| 0.0.1-alpha.0      | alpha | [view](https://https://github.com/vinv-group/vinv-schema) |

```javascript
// example server object
{
    "v": "0.0.1-alpha"
}
```

### Server ###

Das "server Object" kann genutzt werden, wenn Daten über eine API von einer Datenbank bereitgestellt werden. In the "server Object" the url of the endpoint can be defined.

```javascript
// example server object
{
    "server": {   // Server
        "url": "https://vinv.io/" // Endpoint
    }
}
```

### Inventory ###

The object inventory contains an array of tree objects with attributes and a array of changes to this tree data.

#### Tree Object ####

```javascript
// example tree object

{
    "LURPdZ8NixY7WriS22S01":[   // URL-friendly unique ID
        [
            [
                23.4444441, //  longitude
                23.4464441, // latitude
                0], // altitude
            12 // Accuracy of meassured coordinates
        ],
        "666", // Species ID according to https://github.com/b-lack/tree-species
        25, // DBH in centimeter
        22, // Height in meter
        [   // Trunk definition
            [
                0.3,
                5
            ],
            [0.6,5]],
            [[0.3,5],
            [0.6,5]
        ],
        [   // Crown definition
            [
                0.3,
                5
            ],
            [0.6,5]],
            [[0.3,5],
            [0.6,5]
        ],
        "2018-11-13", // Birthday of tree
        null // List of Images
    ]
}
```

#### Tree History ####

```javascript
// example tree history object

[
    "LURPdZ8NixY7WriS22S01", // The ID of the tree whose data was changed
    "2021-07-12T15:12:09.721Z", // Date and time when the tree data was changed
    tree1 // Tree objects
]
```

{% include next-btn.html 
    title="Validation"
    href="./validation.html"
%}