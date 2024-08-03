---
layout: default
parent: User guide
title: Strings manipulation
has_toc: true
---
# Navigation Structure
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

Funcml implements string manipulation.

### _replace

_replace replaces accordingly to its substitutions arrays the value loaded in content.

**Usage**
```yaml
key:
  _replace:
    content: "a-b-c"
    substitutions:
      - ["b", "z"]
      - ["-", "."]
```

will be rendered as:

```yaml
key: "a.z.c"
```
### _upcase

_upcase transforms its value to a upcase string.

**Usage**
```yaml
key:
  _upcase: abc
```

will be rendered as:

```yaml
key: ABC
```

### _downcase

_downcase transforms its value to a downcase string.

**Usage**
```yaml
key:
  _downcase: ABC
```

will be rendered as:

```yaml
key: abc
```

### _capitalize

_capitalize capitalizes its value

**Usage**
```yaml
key:
  _capitalize: abc
```

will be rendered as:

```yaml
key: Abc
```