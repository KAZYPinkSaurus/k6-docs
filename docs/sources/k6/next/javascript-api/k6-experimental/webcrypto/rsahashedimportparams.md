---
title: 'RsaHashedImportParams'
description: 'RsaHashedImportParams represents the object that should be passed as the algorithm parameter into the importKey operation, when using the RSA algorithm.'
weight: 12
---

# RsaHashedImportParams

{{< docs/shared source="k6" lookup="webcrypto/deprecated.md" version="<K6_VERSION>" >}}

The `RsaHashedImportParams` represents the object that should be passed as the algorithm parameter into [`importKey`](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/webcrypto/subtlecrypto/importkey/) when using the RSA algorithm.

## Properties

| Property | Type     | Description                                                         |
| :------- | :------- | :------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| name     | `string` | This should be set to `RSASSA-PKCS1-v1_5`, `RSA-PSS` or `RSA-OAEP`. |
| hash     | `string` | `object`                                                            | The name or an object with a `name` property of the digest function to use. Possible values are `SHA-1`, `SHA-256`, `SHA-384` and `SHA-512`. |
