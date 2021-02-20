+++
title = "Dimensionality Reduction"
date = "2021-02-17"
description = "Add description"
tags = []
comments = true
math = true
+++

{{< math.inline >}}
{{ if or .Page.Params.math .Site.Params.math }}
<!-- KaTeX -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.10.1/dist/katex.min.css" integrity="sha384-dbVIfZGuN1Yq7/1Ocstc1lUEm+AT+/rCkibIcC/OmWo5f0EA48Vf8CytHzGrSwbQ" crossorigin="anonymous">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.10.1/dist/katex.min.js" integrity="sha384-2BKqo+exmr9su6dir+qCw08N2ZKRucY4PrGQPPWU1A7FtlCGjmEGFqXCv5nyM5Ij" crossorigin="anonymous"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.10.1/dist/contrib/auto-render.min.js" integrity="sha384-kWPLUVMOks5AQFrykwIup5lo0m3iMkkHrD0uJ4H5cjeGihAutqP0yW0J6dpFiVkI" crossorigin="anonymous" onload="renderMathInElement(document.body);"></script>
{{ end }}
{{</ math.inline >}}

A quick tour of different dimensionality reduction techniques. Why are they useful? Which one to use and when?

---

Dataset: MNIST 28x28 dimensions
![mnist_dataset](/posts/dimred/MNIST_dataset.jpg)
In the plots below, different colors correspond to different labels. Clusters of the same color
suggest that the dimensionality reduction algorithm has properly understood
the structure of the data. As a result, identical numbers end up near one another.

## PCA(3)
{{<rawhtml>}}
<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://plotly.com/~Yann21/1.embed" height="525" width="100%"></iframe>
{{</rawhtml>}}

## PCA(50) followed by t-SNE
{{<rawhtml>}}
<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://plotly.com/~Yann21/8.embed" height="525" width="100%"></iframe>
{{</rawhtml>}}
