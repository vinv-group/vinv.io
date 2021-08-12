---
layout: documentation
---

#### . documentation
# Getting started

## .vinv Exchange Format ##

.vinv is a format for encoding individual tree data.


```javascript
{
    "LURPdZ8NixY7WriS22S01":[
        [
            [23.4444441,23.4464441,0], // Coordinates 
            12 // Accuracy
        ],
        "666", // Species ID
        25, // DBH
        22, // Height
        [
            [0.3,5],
            [0.6,5]],
            [[0.3,5],
            [0.6,5]
        ],
        "2018-11-13", // Birthday of tree
        null // Images
    ]
}
```

{% highlight javascript %}
{
    "LURPdZ8NixY7WriS22S01":[
        [[23.4444441,23.4464441,0],12],
        "666",
        25,
        22,
        [[0.3,5],[0.6,5]],[[0.3,5],[0.6,5]],
        "2018-11-13",
        null
    ]
}
{% endhighlight %}
