---
layout: default
parent: User guide
title: Types cast
has_toc: true
---
# Navigation Structure
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

Funcml knows how to cast data types using functions.

### _string

_string takes an integer, a float, a dictionary (Hash) or an Array and stringifies it.

**Usage**
```yaml
key:
  _string: 1
```

will be rendered as:

```yaml
key: "1"
```

### _int

_int takes a string or a float and returns a unsigned integer.

**Usage**
```yaml
key:
  _int: "1"
```

will be rendered as:

```yaml
key: 1
```

### _float

_float takes a string or an integer and returns a float.

**Usage**
```yaml
key:
  _float: "1"
```

will be rendered as:

```yaml
key: 1.0
```

### _json

_json returns its structure in JSON.

**Usage**
```yaml
key:
  _json:
    subkey: value
```

will be rendered as:

```yaml
key: '{"subkey":"value"}'
```
