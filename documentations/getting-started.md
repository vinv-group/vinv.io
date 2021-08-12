---
layout: documentation
---

<p class="h5">
  <span class="subtitle point-before hp">Documentation</span>
</p>
# Getting started

The <span class="heighlight">vinv</span>  specification defines the **syntax** and **semantics** of forest inventory data. This definition is needed to ensure 
- that all minimum **required data are available**
- that the data are **realistic**
- that the data is available in a form that a machine can understand and thus can be **processed automatically**

<p class="h5">
  <span class="subtitle point-before hp">Precision Forestry</span>
</p>
<h2 class="m-0">Resolution of Data</h2>

Forest inventory data presented with <span class="heighlight">vinv</span> are formed by the largest possible intersection of common inventory methods. Thereby, the storage of aggregations is deliberately avoided.

Consequently, a `.vinv` file consists of a list of individual tree data defined by various tree attributes.

<p class="h5">
  <span class="subtitle point-before hp">Core</span>
</p>
<h2 class="m-0">Feature</h2>

In order to technically ensure that the inventory data follows the vinv specification schema, .

At the same time the schema should be used to check `.vinv` files for validity.

This **open source** schema is provided by the <a href="/group">vinv group</a> and availible under the <a href="https://choosealicense.com/licenses/mit/" rel="noreferrer" target="_blank">MIT license</a>. 
 
<a class="btn btn-outline-dark" href="https://github.com/vinv-group/vinv-schema" target="_blank" rel="noreferrer">
        <i class="bi-github" role="img" aria-label="GitHub"></i>&nbsp;
        vinv-schema & Documentation
</a>

{% include next-btn.html 
    title=".vinv Format"
    href="./format.html"
%}
