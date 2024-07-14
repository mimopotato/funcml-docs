---
layout: default
parent: User guide
title: Encoding
has_toc: true
---
# Navigation Structure
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}


Funcml-core is able to encode and decode base64.

### _base64encode

Input should be a string and output is the string encoded in base64.

*Usage*
```yaml
key:
  _base64encode: |
    test
```

will be rendered as:

```yaml
key: dGVzdA=
```

Obviously, and like every other function of funcml-core, it can take any "string-returner" as a valid input.

```yaml
key:
  _base64encode: 
    _readfile: "./test.txt
```

### _base64decode

Decode a base64 string and returns a string.

*Usage*
```yaml
key:
  _base64decode: "dGVzdA="
```

will be rendered as:

```yaml
key: test
```
