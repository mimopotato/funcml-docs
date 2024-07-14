---
layout: default
parent: User guide
title: Time
has_toc: true
---
# Navigation Structure
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

Time management is included in funcml-core.

### $now

Special variable returning the current time object. Must be converted to string using _time function.

*Usage*
```yaml
key:
  _time:
    value: "$now"
```

will be rendered as:
```yaml
key: "14/07/2024 15:54:06"
```

A `format` argument is supported to change the time representation in the output.

```yaml
key:
  _time:
    value: "$now"
    format: "%H:%M"
```

will be rendered as:
```yaml
key: "15:54"
```


### _ago

Returns a time object with seconds delta from now.

*Usage*
```yaml
key:
  _time:
    format: "%H:%M"
    value:
      _ago: 600
```

will be rendered as:
```yaml
key: 15:24
```
