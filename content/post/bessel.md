+++
title = "Bessel's correction"
date = "2021-01-25"
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

Short proof of why the MLE of the variance is a biased estimator.

---


$$ \mathop{\mathbb{E}}[\sigma_{ML}^2] = \mathop{\mathbb{E}}[\frac{1}{n} \sum_{i=1}^n(x_i - \mu_{ML})^2] $$
$$ = \color{red}\mathop{\mathbb{E}}[x_i^2] \color{black} - \color{blue}2 \mathop{\mathbb{E}}[x_i \mu_{ML}]\color{black} + \color{green}\mathop{\mathbb{E}}[\mu_{ML}^2] \color{black}$$
$$ = \color{red} \sigma^2 + \mu^2 \color{black} - \color{blue}2 \mathop{\mathbb{E}}[x_i \frac{1}{n} \sum_{j=1}^n x_j] \color{black} + \color{green}\mathop{\mathbb{E}} [\frac{1}{n^2}(\sum_{i=1}^n x_i)^2]\color{black}$$
$$ = \color{red} \sigma^2 + \mu^2 \color{black} - \color{blue}\frac{2}{n} \mathop{\mathbb{E}}[x_i^2 + x_i \sum_{j \neq i} x_j] \color{black} + \color{green}\frac{1}{n^2}\mathop{\mathbb{E}}[\sum_{i=1}^n x_i + \sum_{i \neq j} x_i x_j]\color{black}$$
$$ = \color{red} \sigma^2 + \mu^2 \color{black} - \color{blue} 2(\frac{1}{n}(\sigma^2 + \mu^2) + \frac{n-1}{n} \mu^2)\color{black} + \color{green}\frac{n}{n^2} (\mu^2 + \sigma^2) + \frac{n^2 - n}{n^2} \mu^2 \color{black} $$
$$ = \frac{n-1}{n} \sigma^2$$

Given that: (correct display)
$$
\begin{cases}
      \mathop{\mathbb{E}}[x_i x_j] = \mu^2 + \sigma^2 \text{if $i=j$}
      \mathop{\mathbb{E}}[x_i x_j] = \mu^2 \ if \ i \neq j
\end{cases}
$$

---
When we measure the
variation of our r.v. with respect to the **sample mean**, we are acting as if there was an
additional sample in the average, thus removing a degree of freedom and skewing the result towards less variance.

Conversely, the MLE of the variance with respect to the true **population mean**
is unbiased. This can be seen in the factor n-1/n which tends to 1 as the sample
mean reaches the true population mean.



In other words:
$$ \sigma_{MVU} = \frac{n}{n-1} \sigma_{ML} $$
$$ = \frac{1}{n-1} \sum_{i=1}^n (x_i - \mu_{ML})^2$$
