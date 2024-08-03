---
layout: default
parent: User guide
title: Mathematics
has_toc: true
---
# Navigation Structure
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

Funcml implements basic mathematics.

### _add

Returns a + b

**Usage**
```yaml
key:
  _add:
    - 1
    - 2
```

will be rendered as:

```yaml
key: 3
```

### _sub

Returns a - b

**Usage**
```yaml
key:
  _sub:
    - 2
    - 1
```

will be rendered as:

```yaml
key: 1
```

### _div

Returns a / b

**Usage**
```yaml
key:
  _add:
    - 3
    - 2
```

will be rendered as:

```yaml
key: 1.5
```

### _mod

Returns a % b

**Usage**
```yaml
key:
  _add:
    - 2
    - 3
```

will be rendered as:

```yaml
key: 2
```

### _mul

Returns a * b

**Usage**
```yaml
key:
  _mul:
    - 2
    - 3
```

will be rendered as:

```yaml
key: 6
```

### _min

Returns minimal value in array

**Usage**
```yaml
key:
  _min:
    - 2
    - 1
    - 3
```

will be rendered as:

```yaml
key: 1
```

### _max

Returns maximal value in array

**Usage**
```yaml
key:
  _min:
    - 2
    - 3
    - 1
```

will be rendered as:

```yaml
key: 3
```

### _floor

Returns floor value.

**Usage**
```yaml
key:
  _floor: 1.1
```

will be rendered as:

```yaml
key: 1
```

### _ceil

Returns ceil value.

**Usage**
```yaml
key:
  _ceil: 1.1
```

will be rendered as:

```yaml
key: 2
```

### _round

Returns rounded value.

**Usage**
```yaml
key:
  _round: 1.1
key2:
  _round: 1.9
```

will be rendered as:

```yaml
key: 1
key2: 2
```
