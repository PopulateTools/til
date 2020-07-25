---
layout: post
title:  "Detect CSV file encoding in Ruby with Charlock Holmes"
date:   2020-07-25 12:15:49 +0700
author: blat
tags:
- ruby
- data
---

[Charlock Holmes](https://github.com/brianmario/charlock_holmes/) is the best library I've found in
Ruby to detect the encoding of a string.

In our case, we are detecting the encoding of a CSV before converting it to UTF-8:

```ruby
# data is the variable with the CSV content
encoding_detection = CharlockHolmes::EncodingDetector.detect(data)
# => {:encoding => 'ISO-8859-1', :confidence => 75, :type => :text}
data.force_encoding(encoding_detection[:encoding]).encode('UTF-8')
```

BTW, if you use Python, you **must** use
[chardet](https://chardet.readthedocs.io/en/latest/index.html) which also includes a cli.
