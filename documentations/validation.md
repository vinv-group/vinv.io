---
layout: documentation
---

<p class="h4">
  <span class="subtitle point-before">Documentation</span>
</p>
<h1>Validation</h1>

Validation ensures that `.vinv` files follow the specification, i.e. are valid. So it should be ensured that `.vinv` processing software checks received file to exclude errors due to non-valid data.

The <a href="vinv-schema"></a> is provided to perform this validation. In doing so, it itself follows the specifications of a JSON schema in version *draft-07*. 
Learn more about <a href="https://json-schema.org/" rel="noreferrer" target="_blank">JSON Schema</a>.

There are many ways to validate a vinv file depending on the programming language used. A list of possible implementations can be found <a href="https://json-schema.org/implementations.html" rel="noreferrer" target="_blank">here</a>.

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