# api documentation for  [bcryptjs (v2.4.3)](https://github.com/dcodeIO/bcrypt.js#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-bcryptjs.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-bcryptjs) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-bcryptjs.svg)](https://travis-ci.org/npmdoc/node-npmdoc-bcryptjs)
#### Optimized bcrypt in plain JavaScript with zero dependencies. Compatible to 'bcrypt'.

[![NPM](https://nodei.co/npm/bcryptjs.png?downloads=true)](https://www.npmjs.com/package/bcryptjs)

[![apidoc](https://npmdoc.github.io/node-npmdoc-bcryptjs/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-bcryptjs_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-bcryptjs/build..beta..travis-ci.org/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-bcryptjs/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-bcryptjs/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Daniel Wirtz",
        "email": "dcode@dcode.io"
    },
    "browser": "dist/bcrypt.js",
    "bugs": {
        "url": "https://github.com/dcodeIO/bcrypt.js/issues"
    },
    "contributors": [
        {
            "name": "Shane Girish",
            "email": "shaneGirish@gmail.com",
            "url": "https://github.com/shaneGirish"
        },
        {
            "name": "Alex Murray",
            "url": "https://github.com/alexmurray"
        },
        {
            "name": "Nicolas Pelletier",
            "url": "https://github.com/NicolasPelletier"
        },
        {
            "name": "Josh Rogers",
            "url": "https://github.com/geekymole"
        },
        {
            "name": "Noah Isaacson",
            "email": "noah@nisaacson.com",
            "url": "https://github.com/nisaacson"
        }
    ],
    "dependencies": {},
    "description": "Optimized bcrypt in plain JavaScript with zero dependencies. Compatible to 'bcrypt'.",
    "devDependencies": {
        "bcrypt": "latest",
        "closurecompiler": "~1",
        "metascript": "~0.18",
        "testjs": "~1",
        "utfx": "~1"
    },
    "directories": {},
    "dist": {
        "shasum": "9ab5627b93e60621ff7cdac5da9733027df1d0cb",
        "tarball": "https://registry.npmjs.org/bcryptjs/-/bcryptjs-2.4.3.tgz"
    },
    "gitHead": "f7dd725a0b77036696042b5c1cb5e13cf0f7291e",
    "homepage": "https://github.com/dcodeIO/bcrypt.js#readme",
    "keywords": [
        "bcrypt",
        "password",
        "auth",
        "authentication",
        "encryption",
        "crypt",
        "crypto"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "dcode",
            "email": "dcode@dcode.io"
        }
    ],
    "name": "bcryptjs",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "url",
        "url": "git+https://github.com/dcodeIO/bcrypt.js.git"
    },
    "scripts": {
        "build": "node scripts/build.js",
        "compile": "node node_modules/closurecompiler/bin/ccjs dist/bcrypt.js --compilation_level=SIMPLE_OPTIMIZATIONS --create_source_map=dist/bcrypt.min.map > dist/bcrypt.min.js",
        "compress": "gzip -c -9 dist/bcrypt.min.js > dist/bcrypt.min.js.gz",
        "make": "npm run build && npm run compile && npm run compress && npm test",
        "test": "node node_modules/testjs/bin/testjs"
    },
    "version": "2.4.3"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module bcryptjs](#apidoc.module.bcryptjs)
1.  [function <span class="apidocSignatureSpan">bcryptjs.</span>compare (s, hash, callback, progressCallback)](#apidoc.element.bcryptjs.compare)
1.  [function <span class="apidocSignatureSpan">bcryptjs.</span>compareSync (s, hash)](#apidoc.element.bcryptjs.compareSync)
1.  [function <span class="apidocSignatureSpan">bcryptjs.</span>decodeBase64 (s, len)](#apidoc.element.bcryptjs.decodeBase64)
1.  [function <span class="apidocSignatureSpan">bcryptjs.</span>encodeBase64 (b, len)](#apidoc.element.bcryptjs.encodeBase64)
1.  [function <span class="apidocSignatureSpan">bcryptjs.</span>genSalt (rounds, seed_length, callback)](#apidoc.element.bcryptjs.genSalt)
1.  [function <span class="apidocSignatureSpan">bcryptjs.</span>genSaltSync (rounds, seed_length)](#apidoc.element.bcryptjs.genSaltSync)
1.  [function <span class="apidocSignatureSpan">bcryptjs.</span>getRounds (hash)](#apidoc.element.bcryptjs.getRounds)
1.  [function <span class="apidocSignatureSpan">bcryptjs.</span>getSalt (hash)](#apidoc.element.bcryptjs.getSalt)
1.  [function <span class="apidocSignatureSpan">bcryptjs.</span>hash (s, salt, callback, progressCallback)](#apidoc.element.bcryptjs.hash)
1.  [function <span class="apidocSignatureSpan">bcryptjs.</span>hashSync (s, salt)](#apidoc.element.bcryptjs.hashSync)
1.  [function <span class="apidocSignatureSpan">bcryptjs.</span>setRandomFallback (random)](#apidoc.element.bcryptjs.setRandomFallback)



# <a name="apidoc.module.bcryptjs"></a>[module bcryptjs](#apidoc.module.bcryptjs)

#### <a name="apidoc.element.bcryptjs.compare"></a>[function <span class="apidocSignatureSpan">bcryptjs.</span>compare (s, hash, callback, progressCallback)](#apidoc.element.bcryptjs.compare)
- description and source-code
```javascript
compare = function (s, hash, callback, progressCallback) {

    function _async(callback) {
        if (typeof s !== "string" || typeof hash !== "string") {
            nextTick(callback.bind(this, Error("Illegal arguments: "+(typeof s)+', '+(typeof hash))));
            return;
        }
        if (hash.length !== 60) {
            nextTick(callback.bind(this, null, false));
            return;
        }
        bcrypt.hash(s, hash.substr(0, 29), function(err, comp) {
            if (err)
                callback(err);
            else
                callback(null, safeStringCompare(comp, hash));
        }, progressCallback);
    }

    if (callback) {
        if (typeof callback !== 'function')
            throw Error("Illegal callback: "+typeof(callback));
        _async(callback);
    } else
        return new Promise(function(resolve, reject) {
            _async(function(err, res) {
                if (err) {
                    reject(err);
                    return;
                }
                resolve(res);
            });
        });
}
```
- example usage
```shell
...
});
'''

To check a password:

'''javascript
// Load hash from your password DB.
bcrypt.compare("B4c0/\/", hash, function(err, res) {
    // res === true
});
bcrypt.compare("not_bacon", hash, function(err, res) {
    // res === false
});

// As of bcryptjs 2.4.0, compare returns a promise if callback is omitted:
...
```

#### <a name="apidoc.element.bcryptjs.compareSync"></a>[function <span class="apidocSignatureSpan">bcryptjs.</span>compareSync (s, hash)](#apidoc.element.bcryptjs.compareSync)
- description and source-code
```javascript
compareSync = function (s, hash) {
    if (typeof s !== "string" || typeof hash !== "string")
        throw Error("Illegal arguments: "+(typeof s)+', '+(typeof hash));
    if (hash.length !== 60)
        return false;
    return safeStringCompare(bcrypt.hashSync(s, hash.substr(0, hash.length-31)), hash);
}
```
- example usage
```shell
...
// Store hash in your password DB.
'''

To check a password:

'''javascript
// Load hash from your password DB.
bcrypt.compareSync("B4c0/\/", hash); // true
bcrypt.compareSync("not_bacon", hash); // false
'''

Auto-gen a salt and hash:

'''javascript
var hash = bcrypt.hashSync('bacon', 8);
...
```

#### <a name="apidoc.element.bcryptjs.decodeBase64"></a>[function <span class="apidocSignatureSpan">bcryptjs.</span>decodeBase64 (s, len)](#apidoc.element.bcryptjs.decodeBase64)
- description and source-code
```javascript
function base64_decode(s, len) {
    var off = 0,
        slen = s.length,
        olen = 0,
        rs = [],
        c1, c2, c3, c4, o, code;
    if (len <= 0)
        throw Error("Illegal len: "+len);
    while (off < slen - 1 && olen < len) {
        code = s.charCodeAt(off++);
        c1 = code < BASE64_INDEX.length ? BASE64_INDEX[code] : -1;
        code = s.charCodeAt(off++);
        c2 = code < BASE64_INDEX.length ? BASE64_INDEX[code] : -1;
        if (c1 == -1 || c2 == -1)
            break;
        o = (c1 << 2) >>> 0;
        o |= (c2 & 0x30) >> 4;
        rs.push(stringFromCharCode(o));
        if (++olen >= len || off >= slen)
            break;
        code = s.charCodeAt(off++);
        c3 = code < BASE64_INDEX.length ? BASE64_INDEX[code] : -1;
        if (c3 == -1)
            break;
        o = ((c2 & 0x0f) << 4) >>> 0;
        o |= (c3 & 0x3c) >> 2;
        rs.push(stringFromCharCode(o));
        if (++olen >= len || off >= slen)
            break;
        code = s.charCodeAt(off++);
        c4 = code < BASE64_INDEX.length ? BASE64_INDEX[code] : -1;
        o = ((c3 & 0x03) << 6) >>> 0;
        o |= c4;
        rs.push(stringFromCharCode(o));
        ++olen;
    }
    var res = [];
    for (off = 0; off<olen; off++)
        res.push(rs[off].charCodeAt(0));
    return res;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.bcryptjs.encodeBase64"></a>[function <span class="apidocSignatureSpan">bcryptjs.</span>encodeBase64 (b, len)](#apidoc.element.bcryptjs.encodeBase64)
- description and source-code
```javascript
function base64_encode(b, len) {
    var off = 0,
        rs = [],
        c1, c2;
    if (len <= 0 || len > b.length)
        throw Error("Illegal len: "+len);
    while (off < len) {
        c1 = b[off++] & 0xff;
        rs.push(BASE64_CODE[(c1 >> 2) & 0x3f]);
        c1 = (c1 & 0x03) << 4;
        if (off >= len) {
            rs.push(BASE64_CODE[c1 & 0x3f]);
            break;
        }
        c2 = b[off++] & 0xff;
        c1 |= (c2 >> 4) & 0x0f;
        rs.push(BASE64_CODE[c1 & 0x3f]);
        c1 = (c2 & 0x0f) << 2;
        if (off >= len) {
            rs.push(BASE64_CODE[c1 & 0x3f]);
            break;
        }
        c2 = b[off++] & 0xff;
        c1 |= (c2 >> 6) & 0x03;
        rs.push(BASE64_CODE[c1 & 0x3f]);
        rs.push(BASE64_CODE[c2 & 0x3f]);
    }
    return rs.join('');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.bcryptjs.genSalt"></a>[function <span class="apidocSignatureSpan">bcryptjs.</span>genSalt (rounds, seed_length, callback)](#apidoc.element.bcryptjs.genSalt)
- description and source-code
```javascript
genSalt = function (rounds, seed_length, callback) {
    if (typeof seed_length === 'function')
        callback = seed_length,
        seed_length = undefined; // Not supported.
    if (typeof rounds === 'function')
        callback = rounds,
        rounds = undefined;
    if (typeof rounds === 'undefined')
        rounds = GENSALT_DEFAULT_LOG2_ROUNDS;
    else if (typeof rounds !== 'number')
        throw Error("illegal arguments: "+(typeof rounds));

    function _async(callback) {
        nextTick(function() { // Pretty thin, but salting is fast enough
            try {
                callback(null, bcrypt.genSaltSync(rounds));
            } catch (err) {
                callback(err);
            }
        });
    }

    if (callback) {
        if (typeof callback !== 'function')
            throw Error("Illegal callback: "+typeof(callback));
        _async(callback);
    } else
        return new Promise(function(resolve, reject) {
            _async(function(err, res) {
                if (err) {
                    reject(err);
                    return;
                }
                resolve(res);
            });
        });
}
```
- example usage
```shell
...

Usage - Async
-------------
To hash a password:

'''javascript
var bcrypt = require('bcryptjs');
bcrypt.genSalt(10, function(err, salt) {
    bcrypt.hash("B4c0/\/", salt, function(err, hash) {
        // Store hash in your password DB.
    });
});
'''

To check a password:
...
```

#### <a name="apidoc.element.bcryptjs.genSaltSync"></a>[function <span class="apidocSignatureSpan">bcryptjs.</span>genSaltSync (rounds, seed_length)](#apidoc.element.bcryptjs.genSaltSync)
- description and source-code
```javascript
genSaltSync = function (rounds, seed_length) {
    rounds = rounds || GENSALT_DEFAULT_LOG2_ROUNDS;
    if (typeof rounds !== 'number')
        throw Error("Illegal arguments: "+(typeof rounds)+", "+(typeof seed_length));
    if (rounds < 4)
        rounds = 4;
    else if (rounds > 31)
        rounds = 31;
    var salt = [];
    salt.push("$2a$");
    if (rounds < 10)
        salt.push("0");
    salt.push(rounds.toString());
    salt.push('$');
    salt.push(base64_encode(random(BCRYPT_SALT_LEN), BCRYPT_SALT_LEN)); // May throw
    return salt.join('');
}
```
- example usage
```shell
...

Usage - Sync
------------
To hash a password:

'''javascript
var bcrypt = require('bcryptjs');
var salt = bcrypt.genSaltSync(10);
var hash = bcrypt.hashSync("B4c0/\/", salt);
// Store hash in your password DB.
'''

To check a password:

'''javascript
...
```

#### <a name="apidoc.element.bcryptjs.getRounds"></a>[function <span class="apidocSignatureSpan">bcryptjs.</span>getRounds (hash)](#apidoc.element.bcryptjs.getRounds)
- description and source-code
```javascript
getRounds = function (hash) {
    if (typeof hash !== "string")
        throw Error("Illegal arguments: "+(typeof hash));
    return parseInt(hash.split("$")[2], 10);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.bcryptjs.getSalt"></a>[function <span class="apidocSignatureSpan">bcryptjs.</span>getSalt (hash)](#apidoc.element.bcryptjs.getSalt)
- description and source-code
```javascript
getSalt = function (hash) {
    if (typeof hash !== 'string')
        throw Error("Illegal arguments: "+(typeof hash));
    if (hash.length !== 60)
        throw Error("Illegal hash length: "+hash.length+" != 60");
    return hash.substring(0, 29);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.bcryptjs.hash"></a>[function <span class="apidocSignatureSpan">bcryptjs.</span>hash (s, salt, callback, progressCallback)](#apidoc.element.bcryptjs.hash)
- description and source-code
```javascript
hash = function (s, salt, callback, progressCallback) {

    function _async(callback) {
        if (typeof s === 'string' && typeof salt === 'number')
            bcrypt.genSalt(salt, function(err, salt) {
                _hash(s, salt, callback, progressCallback);
            });
        else if (typeof s === 'string' && typeof salt === 'string')
            _hash(s, salt, callback, progressCallback);
        else
            nextTick(callback.bind(this, Error("Illegal arguments: "+(typeof s)+', '+(typeof salt))));
    }

    if (callback) {
        if (typeof callback !== 'function')
            throw Error("Illegal callback: "+typeof(callback));
        _async(callback);
    } else
        return new Promise(function(resolve, reject) {
            _async(function(err, res) {
                if (err) {
                    reject(err);
                    return;
                }
                resolve(res);
            });
        });
}
```
- example usage
```shell
...
Usage - Async
-------------
To hash a password:

'''javascript
var bcrypt = require('bcryptjs');
bcrypt.genSalt(10, function(err, salt) {
    bcrypt.hash("B4c0/\/", salt, function(err, hash) {
        // Store hash in your password DB.
    });
});
'''

To check a password:
...
```

#### <a name="apidoc.element.bcryptjs.hashSync"></a>[function <span class="apidocSignatureSpan">bcryptjs.</span>hashSync (s, salt)](#apidoc.element.bcryptjs.hashSync)
- description and source-code
```javascript
hashSync = function (s, salt) {
    if (typeof salt === 'undefined')
        salt = GENSALT_DEFAULT_LOG2_ROUNDS;
    if (typeof salt === 'number')
        salt = bcrypt.genSaltSync(salt);
    if (typeof s !== 'string' || typeof salt !== 'string')
        throw Error("Illegal arguments: "+(typeof s)+', '+(typeof salt));
    return _hash(s, salt);
}
```
- example usage
```shell
...
Usage - Sync
------------
To hash a password:

'''javascript
var bcrypt = require('bcryptjs');
var salt = bcrypt.genSaltSync(10);
var hash = bcrypt.hashSync("B4c0/\/", salt);
// Store hash in your password DB.
'''

To check a password:

'''javascript
// Load hash from your password DB.
...
```

#### <a name="apidoc.element.bcryptjs.setRandomFallback"></a>[function <span class="apidocSignatureSpan">bcryptjs.</span>setRandomFallback (random)](#apidoc.element.bcryptjs.setRandomFallback)
- description and source-code
```javascript
setRandomFallback = function (random) {
    randomFallback = random;
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
