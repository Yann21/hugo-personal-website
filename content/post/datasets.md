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
```
import keras
keras.datasets.mnist.load_data()
```


* [ImageNet](http://www.image-net.org/)
* UCI (UC Irvine) ML [Repository](https://archive.ics.uci.edu)
* [OpenML](https://www.openml.org/) datasets
```
sklearn.datasets.fetch_openml("mnist_784")
```
[TFDS](https://blog.tensorflow.org/2019/02/introducing-tensorflow-datasets.html)
```
import tensorflow.datasets as tfds
tfds.load("mnist", split="train", with_info=True)
```

## Scraping
* beautiful soup
* pygithub
* Bing image search API
* 
