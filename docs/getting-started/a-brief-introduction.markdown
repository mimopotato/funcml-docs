---
layout: page
title: A brief introduction
permalink: /getting-started/introduction
parent: Getting started
nav_order: 2
---
# A brief introduction

Once Funcml has been installed on your system, you can start generating complex files. 
Take, for example, the following file (extension .yf (YAML function)):

```yaml
sum_values:
  _sum: [1, 2, 3]
```

This file only contains valid YAML syntax. It can also be written as:

```yaml
sum_values:
  _sum:
    - 1
    - 2
    - 3
```

And since YAML syntax also support one-liners, this syntax is also tolerated.

```yaml
sum_values: { _sum: [1, 2, 3] }
```

Here, we want the key `sum_values` to be equal to 6. 

Let me introduce to you the first function of Funcml, `_sum`. As describe in its dedicated documentation section, this function takes an array of integers as argument and _mutates_ the calling block from a dictionary to the direct result. It _mutates__ the calling block, keep this sentence in your head as this is the core principle of Funcml. Funcml _mutates_ structured blocks from YAML or JSON.

## Variables

YAML already implements a principle of anchor ; the syntax isn't that easy to memorize and the feature is pretty limited in fact. 
Funcml prefers to provide an alternative that'll be handled by a mutation. A Funcml variable is a string, always starting with a dollar-sign, like in PHP or Javascript for example.

```yaml

variable: "string"
my_value: "$variable"
```

The `my_value` key will be equal to "string" as the $variable will be expanded. What is nice here is that the dot-convention also works:

```yaml
variable:
  sub_variable:
    again: "string"

my_value: "$variable.sub_variable.again"
```

The variable can also be expanded to another data type. For example, from a string to a dictionary:

```yaml
variable:
  sub_variable:
    again:
      sub_key: sub_value

my_value: "$variable.sub_variable.again"
```
will be rendered as 

```yaml
my_value:
  sub_key: sub_value
```

And last but not the least, the _mutations_ are recursive, meaning you can use any function in the called key.

```yaml
variable:
  sub_variable:
    again:
      sub_key:
        _sum:
          - 1
          - 2
          - 3

my_value: "$variable.sub_variable.again"
```

will be rendered as:

```yaml
my_value:
  sub_key: 6
```

What you need to take attention to is that a block always returns its mutated value. So Funcml acts as it:

* first, it process the _sum function with parameters 1, 2 and 3. 
* $.variable.sub_variable.again.sub_key is returned as 6. 
* Finally the variable call on my_value is executed.


## Special variables

Sometimes, you just want your computer to return a value you don't know yet. For example, the current time as a string or a UUID. To make it short, some special variables exist in Funcml:


```
$now returns the current date
$uuidv4 returns a new UUIDv4
```

Want to learn more about the usable functions ? Read the dedicated page on this website.