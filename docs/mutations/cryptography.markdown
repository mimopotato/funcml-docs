---
layout: default
parent: User guide
title: Cryptography
has_toc: true
---
# Navigation Structure
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

funcml-core can leverage cryptographic functions.

### _sha1sum

Returns the sum of a string as sha1sum.

*Usage*
```yaml
key:
  _sha1sum: "string"
```

will be rendered as:
```yaml
key: ecb252044b5ea0f679ee78ec1a12904739e2904d
```


### _sha256sum

Returns the sum of a string as sha1sum.

*Usage*
```yaml
key:
  _sha256sum: "string"
```

will be rendered as:
```yaml
key: 473287f8298dba7163a897908958f7c0eae733e25d2e027992ea2edc9bed2fa8
```

### _sha256sum

Returns the sum of a string as sha1sum.

*Usage*
```yaml
key:
  _sha256sum: "string"
```

will be rendered as:
```yaml
key: 473287f8298dba7163a897908958f7c0eae733e25d2e027992ea2edc9bed2fa8
```

### _encryptAES

Returns an encrypted data using an encryption key (aes-256-cbc).

*Usage*
```yaml
key:
  _encryptAES:
    data: data
    encryptionKey: secretkey
```

will be rendered as:
```yaml
key: C5EA6CDBA6CBBD4CA89DF9BC862F3490
```

### _decryptAES

Returns a decrypted data using an encryption key (aes-256-cbc).

*Usage*
```yaml
key:
  _decryptAES:
    data: C5EA6CDBA6CBBD4CA89DF9BC862F3490
    encryptionKey: secretkey
```

will be rendered as:

```yaml
key: data
```
