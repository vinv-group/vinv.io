---
layout: documentation
title: "Format & Validation"
description: "vinv compliant inventory data is transferred in the `.vinv` data format."
---

<p class="h4">
  <span class="subtitle point-before hp">Documentation</span>
</p>
# Format & Validation

<span class="heighlight">vinv</span> compliant inventory data is transferred in the `.vinv` data format. The file extension is not mandatory. However, it's best practice in order to tell the receiver that the content follows the <span class="heighlight">vinv</span> specification.

<a class="btn btn-outline-dark" href="https://github.com/vinv-group/vinv-schema" target="_blank" rel="noreferrer">
    <i class="bi-github" role="img" aria-label="GitHub"></i>&nbsp;
    vinv-schema & Documentation
</a>

<p class="h5 mt-5">
  <span class="subtitle point-before hp">Format</span>
</p>
<h2 class="mt-0" id="syntax">Syntax</h2>

Every `.vinv` file contain a single JSON object. 

Virtually all modern programming languages support the JSON structure out of the box.
*JSON (JavaScript Object Notation) is a lightweight data-interchange format. It is easy for humans to read and write. It is easy for machines to parse and generate.* [json.org](https://www.json.org/)

```javascript
// example .vinv file

{
    "v": "0.1-alpha",    // Version of vinv format
    "server": {   // Server
        "url": "https://vinv.io/"
    },
    "inventory":[   // URL-friendly unique ID
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
                        0.3, // Percentage of Height
                        5 // Diameter at Height
                    ],
                    [0.6,5]],
                    [[0.3,5],
                    [0.6,5]
                ],
                [   // Crown definition
                    [
                        0.3, // Percentage of Height
                        5 // Diameter at Height
                    ],
                    [0.6,5]],
                    [[0.3,5],
                    [0.6,5]
                ],
                "2018-11-13", // Birthday of tree
                [   // List of Images
                    "https://via.placeholder.com/150"
                ] 
            ]
        }, 
        []  // Array of changes made to the Tree object above
    ]
}
```

<small>To keep the file size as small as possible, recurring objects like "inventory data" are represented as tuples.</small>

<small>Get familiar with [tuples and JSON-Schema](https://json-schema.org/understanding-json-schema/reference/array.html#tuple-validation).</small>

<p class="h5 mt-5">
  <span class="subtitle point-before hp">Validation</span>
</p>
<h2 class="mt-0" id="semantic">Semantics</h2>

Whether a file meets the vinv specifications is validated against a [Schema](http://schema.vinv.io/0.0.1-alpha.0/vinv.json). This scheme defines where in the file the tree height must be and what unit the BHD must have.

There are [many ways](https://json-schema.org/implementations.html) to technically validate a vinv file against the schema. Depending on the programming language used, only a few lines of source code are required.

```javascript
// exemplary implementation in Javascript

import Ajv from "ajv"
import addFormats from "ajv-formats"

const ajv = new Ajv({strict:false})
addFormats(ajv)

const validate = ajv.getSchema("http://schema.vinv.io/0.0.1-alpha.0/vinv.min.json")
const vinvObject = {...} // vinv Object

if( validate(vinvObject) ) {
    // is valid vinv
} else{
    // is not valid vinv
}

```

<small>Learn more about <a href="https://json-schema.org/" rel="noreferrer" target="_blank">JSON Schema</a>.</small>