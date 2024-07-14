---
layout: page
title: Render
permalink: /getting-started/render
parent: Getting started
nav_order: 3
---
## Render

Saving the following file as "./example.yaml":

```yaml
variable:
  sub_variable:
    again:
      sub_key: sub_value

my_value: "$variable.sub_variable.again"
```

You can now render the file by using the funcml-cli commands:

### As YAML in the stdout
```bash
funcml-cli render-all --directory . -x yaml --mutations ./example.yaml
```

### As JSON in the stdout

```bash
funcml-cli render-all -x yaml -m ./example.yaml --output-format json
```

### As JSON saved in a directory

```bash
funcml-cli render-all -x yaml -m ./example.yaml --no-output-stdout --output-directory ./output
```