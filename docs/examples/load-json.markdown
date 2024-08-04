---
layout: page
title: Load JSON file as struct
permalink: /example/json-import
parent: Examples
nav_order: 2
---

```yaml
# example.yaml
key:
  _fromJson:
    _readfile: ./file.json
```

```json
// file.json
{
  "value": "$now"
}
```

Rendered as:

```yaml
key:
  value: "2024-08-03 17:09"
```