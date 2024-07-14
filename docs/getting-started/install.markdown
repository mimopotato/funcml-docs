---
layout: page
title: Install funcml-cli
permalink: /getting-started/install
parent: Getting started
nav_order: 1
---
# Install funcml-cli

Funcml-cli is packaged as a Ruby gem. It can be installed using bundler or the gem cli.

Funcml-cli requires Ruby (superior to 2.7) to work as pattern-matching support is required.

## Using rbenv

Rbenv is the recommended way to install Ruby and funcml-cli.

### Install rbenv

Follow the [guide available on GitHub](https://github.com/rbenv/rbenv) related to the rbenv installation.

Don't forget to install Ruby 3.0 (stable, we are sure it will work with funcml-cli) and export the path for binaries location.

### Install funcml-cli

```bash
gem install funcml-cli
```