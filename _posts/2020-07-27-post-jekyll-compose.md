---
layout: post
title: Jekyll Compose
date: 2020-07-27
author: blat
tags:
  - jekyll
---

[Jekyll compose](https://github.com/jekyll/jekyll-compose) is a Jekyll command that allows you to create a new empty post (or any other item from a collection) from the command line:

```bash
$ bundle exec jekyll compose post "Jekyll Compose"
```

It can be configured with the default front matter options of your collections:

```yaml
jekyll_compose:
  auto_open: true
  default_front_matter:
    posts:
      layout: post
      title:
      date:
      author:
      tags:
```

`auto-open` option uses the current `$EDITOR` to open the new post in the editor to start editing in the moment.

