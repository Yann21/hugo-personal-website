+++
title = "Dataset reference"
date = "2020-01-01"
description = "Add description"
tags = []
comments = true
math = true
+++
Compiling a list of datasets.

---

### Datasets
* [ImageNet](http://www.image-net.org/)
* UCI (UC Irvine) ML [Repository](https://archive.ics.uci.edu)
* [OpenML](https://www.openml.org/) datasets
* [Data VDL](https://data.public.lu/en/datasets/)

### Tooling
[TFDS](https://blog.tensorflow.org/2019/02/introducing-tensorflow-datasets.html)

```
import keras
keras.datasets.mnist.load_data()

import tensorflow.datasets as tfds
tfds.load("mnist", split="train", with_info=True)

import sklearn
sklearn.datasets.fetch_openml("mnist_784")
```

### Scraping
* beautiful soup
* pygithub
* Bing image search API
* NYT API (free)
