---
layout: default
parent: User guide
title: Conditions
has_toc: true
---
# Navigation Structure
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

You can decide to render a block or not depending on conditions state. A condition is a function of comparison return a boolean value.

### _if

**Usage**
```yaml
key:
  _if:
    - eq: [1, 1]
  foo: bar
```

will be rendered as:

```yaml
key:
  foo: bar
```

#### Multiple conditions

```yaml
key:
  _if:
    - gt: [2, 1]
    - lt: [3, 5]
    - eq: ["foo", "foo"]
  foo: bar
```

will be rendered as
```yaml
key:
  foo: bar
```

since all conditions are met.

#### _else

The else function is also supported. Else requires a _if set in the block. Only its subkeys will be rendered.

```yaml
key:
  _if:
    - eq: [1, 2]
  foo: should not be rendered

  _else:
    foo: this should be rendered
```

will be rendered as
```yaml
key:
  foo: this should be rendered
```

#### All conditions

Funcml includes a bunch of comparisons, working with string, integers, arrays or dictionaries.

* **eq: [a, b]** returns true if a is equal to b
* **gt: [a, b]** returns true if a is greater than b
* **ge: [a, b]** returns true if a is greater than or equal to b
* **lt: [a, b]** returns true if a is less than b
* **le: [a, b]** returns true if a is less tha or equal to b
* **in: [a, [b, c, d]]** returns true if a is one of b, c or d.
* **present: [a]** returns true if a exists (typically a variable not returning null)
* **null: [a]** returns true if a does not exist (typically a variable set to null or unset)
* **match: [a, b]** returns true if a match a regex set in b
* **unmatch: [a, b]** returns true if a doesn't match a regex set in b.

#### Usage example

```
key:
  _if:
    - {eq: [1, 1]}
    - {gt: [2, 1]}
    - {ge: [2, 2]}
    - {lt: [1, 2]}
    - {le: [1, 1]}
    - {in: [a, [a, b, c]]}
    - {present: [1]}
    - {null: [null]}
    - {match: [test, "^test$]}
    - {unmatch: [test, "^error$"]}
  everything_matches: true
```

#### OR

Or is a condition returning true if at least on of its sub-condition is met:

```yaml
key:
  _if:
    - or:
      - eq: [1, 1]
      - eq: ["hello", "world"]
  foo: bar
```

will be rendered as
```yaml
key:
  foo: bar
```

since the first condition is met. Of course, OR is a simple condition that can be additional to other lower-level ones:

```yaml
key:
  _if:
    - eq: [1, 1]
    - or:
      - eq: [2, 2]
      - in: [1, [2, 3, 4]]
  foo: bar
```

will be rendered as
```yaml
key:
  foo: bar
```

because the conditions are met: the eq: [1, 1] returns true and the OR returns true also since its first condition returns true itself.
