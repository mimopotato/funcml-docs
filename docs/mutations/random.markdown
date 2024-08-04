---
layout: default
parent: User guide
title: Random
has_toc: true
---
# Navigation Structure
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

funcml-core is able to generate random string, numbers and floats.

### _randomString

Returns a random string.

**Usage**
```yaml
key:
  _randomString:
    length: 6
    allowed: abcdef # defaults to abcdefhijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWYXZ
```

will be rendered as:
```yaml
key: aebcdf
```

### _randomNumber

Returns a random number with optional boundaries.

**Usage**
```yaml
key:
  _randomNumber: null # min: 0, max: 1000 by default
key2:
  _randomNumber:
    min: 1
    max: 10
key3:
  _randomNumber:
    min: 1.0
    max: 10.0
```

will be rendered as:
```yaml
key: 783
key2: 8
key3: 6.0
```
