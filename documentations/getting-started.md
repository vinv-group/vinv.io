---

layout: documentation
language: "en"
title: "Getting started with vinv  | Documentation"
type: "website"
image: ""
description: "A schema is provided to ensure that inventory data conforms to the vinv specification."

---

<p class="h4">
  <span class="subtitle point-before hp">Documentation</span>
</p>
# Getting started

The <span class="heighlight">vinv</span> specification defines the **syntax** and **semantics** of forest inventory data. This definition is needed to ensure ...
- that all minimum **required** data are available.
- that data are **realistic** and **valid**.
- that the data is available in the expected form and can therefore be **processed automatically**.

<!--<p class="h5 mt-5">
  <span class="subtitle point-before hp">Precision Forestry</span>
</p>
<h2 class="mt-0">Resolution of Data</h2>

Forest inventory data presented with <span class="heighlight">vinv</span> are formed by the largest possible intersection of common inventory methods. Thereby, the storage of aggregations is deliberately avoided.

Consequently, a `.vinv` file consists of a list of individual tree data defined by various tree attributes.-->

<p class="h5 mt-5">
  <span class="subtitle point-before hp">Core</span>
</p>
<h2 class="mt-0">Feature</h2>

A schema is provided to ensure that inventory data conforms to the vinv specification.

This **open source** schema is provided by the <a href="/group">vinv group</a> and availible under the <a href="https://choosealicense.com/licenses/mit/" rel="noreferrer" target="_blank">MIT license</a>. 
 
<a class="btn btn-outline-dark" href="https://github.com/vinv-group/vinv-schema" target="_blank" rel="noreferrer">
        <i class="bi-github" role="img" aria-label="GitHub"></i>&nbsp;
        vinv-schema & Documentation
</a>

{% include next-btn.html 
    title="Format & Validation"
    href="./format.html"
%}
