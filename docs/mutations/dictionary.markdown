---
layout: default
parent: User guide
title: Dictionary
has_toc: true
---
# Navigation Structure
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Dictionary functions

### _merge
```
Input: x[Hash][_merge]=ref:y[Hash]
Output: x[Hash]+y[Hash] - y[Hash][_merge]
```

Merges a dictionary into another one, while keeping already existing keys.

**Usage**
```yaml
dict:
  key: value

another_dict:
  _merge: $dict
  another_key: value
```

will be rendered as:

```yaml
another_dict:
  another_key: value
  key: value
```

### _concat
```
Input: x[Hash][_concat][items[Array]|sep[String]]
Output: x[String]
```

Concatenates an array of elements with a selected separator. Separator is "" by default.

**Usage**

```yaml
world: World

key:
  _concat:
    items:
      - Hello
      - $world 
    sep: " "
```

Will be rendered as:

```yaml
key: Hello World
```

### _sum

```
Input: x[Hash][_sum] = Array[Integer]
Output: x[Integer]
```

Calculates the sum of the numbers defined and mutates the calling key.

**Usage**
```yaml
key:
  _sum: [1, 2, 3]
```

Will be rendered as

```yaml
key: 6
```