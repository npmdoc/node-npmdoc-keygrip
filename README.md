# api documentation for  [keygrip (v1.0.1)](https://github.com/expressjs/keygrip)  [![npm package](https://img.shields.io/npm/v/npmdoc-keygrip.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-keygrip) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-keygrip.svg)](https://travis-ci.org/npmdoc/node-npmdoc-keygrip)
#### Key signing and verification for rotated credentials

[![NPM](https://nodei.co/npm/keygrip.png?downloads=true)](https://www.npmjs.com/package/keygrip)

[![apidoc](https://npmdoc.github.io/node-npmdoc-keygrip/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-keygrip_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-keygrip/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-keygrip/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-keygrip/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "bugs": {
        "url": "https://github.com/expressjs/keygrip/issues"
    },
    "dependencies": {},
    "description": "Key signing and verification for rotated credentials",
    "devDependencies": {},
    "directories": {},
    "dist": {
        "shasum": "b02fa4816eef21a8c4b35ca9e52921ffc89a30e9",
        "tarball": "https://registry.npmjs.org/keygrip/-/keygrip-1.0.1.tgz"
    },
    "engines": {
        "node": "*"
    },
    "homepage": "https://github.com/expressjs/keygrip",
    "maintainers": [
        {
            "name": "jed",
            "email": "tr@nslator.jp"
        }
    ],
    "name": "keygrip",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/expressjs/keygrip.git"
    },
    "scripts": {
        "test": "node test.js"
    },
    "version": "1.0.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module keygrip](#apidoc.module.keygrip)
1.  [function <span class="apidocSignatureSpan">keygrip.</span>index ()](#apidoc.element.keygrip.index)
1.  [function <span class="apidocSignatureSpan">keygrip.</span>sign ()](#apidoc.element.keygrip.sign)
1.  [function <span class="apidocSignatureSpan">keygrip.</span>verify ()](#apidoc.element.keygrip.verify)



# <a name="apidoc.module.keygrip"></a>[module keygrip](#apidoc.module.keygrip)

#### <a name="apidoc.element.keygrip.index"></a>[function <span class="apidocSignatureSpan">keygrip.</span>index ()](#apidoc.element.keygrip.index)
- description and source-code
```javascript
index = function () {
  throw new Error("Usage: require('keygrip')(<array-of-keys>)")
}
```
- example usage
```shell
...

Keygrip keeps a reference to this array to automatically reflect any changes. This reference is stored using a closure to prevent
 external access.

### keys.sign(data)

This creates a SHA1 HMAC based on the _first_ key in the keylist, and outputs it as a 27-byte url-safe base64 digest (base64 without
 padding, replacing '+' with '-' and '/' with '_').

### keys.index(data, digest)

This loops through all of the keys currently in the keylist until the digest of the current key matches the given digest, at which
 point the current index is returned. If no key is matched, '-1' is returned.

The idea is that if the index returned is greater than '0', the data should be re-signed to prevent premature credential invalidation
, and enable better performance for subsequent challenges.

### keys.verify(data, digest)
...
```

#### <a name="apidoc.element.keygrip.sign"></a>[function <span class="apidocSignatureSpan">keygrip.</span>sign ()](#apidoc.element.keygrip.sign)
- description and source-code
```javascript
sign = function () {
  throw new Error("Usage: require('keygrip')(<array-of-keys>)")
}
```
- example usage
```shell
...

The keylist is an array of all valid keys for signing, in descending order of freshness; new keys should be 'unshift'ed into the
 array and old keys should be 'pop'ped.

The tradeoff here is that adding more keys to the keylist allows for more granular freshness for key validation, at the cost of
a more expensive worst-case scenario for old or invalid hashes.

Keygrip keeps a reference to this array to automatically reflect any changes. This reference is stored using a closure to prevent
 external access.

### keys.sign(data)

This creates a SHA1 HMAC based on the _first_ key in the keylist, and outputs it as a 27-byte url-safe base64 digest (base64 without
 padding, replacing '+' with '-' and '/' with '_').

### keys.index(data, digest)

This loops through all of the keys currently in the keylist until the digest of the current key matches the given digest, at which
 point the current index is returned. If no key is matched, '-1' is returned.
...
```

#### <a name="apidoc.element.keygrip.verify"></a>[function <span class="apidocSignatureSpan">keygrip.</span>verify ()](#apidoc.element.keygrip.verify)
- description and source-code
```javascript
verify = function () {
  throw new Error("Usage: require('keygrip')(<array-of-keys>)")
}
```
- example usage
```shell
...

### keys.index(data, digest)

This loops through all of the keys currently in the keylist until the digest of the current key matches the given digest, at which
 point the current index is returned. If no key is matched, '-1' is returned.

The idea is that if the index returned is greater than '0', the data should be re-signed to prevent premature credential invalidation
, and enable better performance for subsequent challenges.

### keys.verify(data, digest)

This uses 'index' to return 'true' if the digest matches any existing keys, and 'false' otherwise.

## Example

'''javascript
// ./test.js
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
