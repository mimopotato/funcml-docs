---
layout: default
parent: User guide
title: Loops
has_toc: true
---
# Navigation Structure
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

### _loop

Loop iterates over a list of items and returns an array of blocks.

```yaml

key:
  _loop:
    items:
      - number: 3
      - number: 5
      - number: 9
    block:
      my_value: $item.number
```

will be rendered as
```yaml
key:
  - my_value: 3
  - my_value: 5
  - my_value: 9
```

#### Few things to note

* in the loop execution, the current item is accessible as a variable with $item.
* an item can be a simple value (items is then a simple Array of items) or a dictionary.
* when items are dictionaries, their subkeys can be reached with $item.subkey

#### Pre & post mutations

All items are mutated before being called by the _loop block.

When a block is generated using an item, it is mutated. It allows you to create complex structures easily.

```yaml
items:
  - strings:
    - hello
    - world
  - strings:
    - foo
    - bar

global:
  merged: true

key:
  _loop:
    items: $items
    block:
      subkey:
        _concat: {items: $item.strings, sep: " "}
      _merge: $global
```

will be rendered as:

```yaml
key:
  - subkey: hello world
    merged: true
  - subkey: foo bar
    merged: true
```

### _until

_until repeats an action a certain amount of times, exposing a $item variable equal to the current iteration index.

**Usage**
```yaml
key:
  _until: 3
  current_index: $item
```

Will be rendered as

```yaml
key:
  - current_index: 0
  - current_index: 1
  - current_index: 2
```

### _map

_map returns an array of mutated values using a no-argument function call.

**Usage**

```yaml
key:
  _map:
    items: [a, b, c]
    call: _upcase
```

Will be rendered as

```yaml
key:
  - A
  - B
  - C