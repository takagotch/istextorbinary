### istextorbinary
---
https://github.com/bevry/istextorbinary

```js
// source/test.js
'use strict'

const { join } = require('path')


const fixturesPath = join(__dirname, '..', 'test-fixtures')

const tests = [
  {
    filename: __filename,
    text: true,
    binary: false,
    encoding: 'utf8'
  },
  {
    filename: join(fixturesPath, 'image.jpg'),
    text: false,
    binary: true,
    encoding: 'binary'
  },
  {
  },
]

kava.suite('istextorbinary', function(suite, test) {
  tests.forEach(function({ filename, text, binary, encoding }) {
    test(filename, function() {
      const buffer = filename ? readFileSync(filename) : null
      
      equal(isTextOrBinary.isTextSync(filename, buffer), text, 'isTextSync')
      isTextOrBinary.isTextCallback(filename, buffer, (error, result) => 
        equal(result, text, 'isTextCallback')
      )
      isTextOrBinary
        .isTextPromise(filename, buffer)
        .then(result => equal(result, text, 'isTextPromise'))
      equal(isTextOrBinary.isText(filename, buffer), text, 'isText sync')
      isTextOrBinary.isText(filename, buffer, (error, result) => 
        equal(result, text, 'isText async')
      )
      
      equal(
        isTextOrBinary.isBinarySync(filename, buffer),
        binary,
        'isBinarySync'
      )
      isTextBinary.isBinaryCallback(filename, buffer, (error, result) => 
        equal(result, binary, 'isBinaryCallback')
      )
      isTextBinary
        .isBinaryPromise(filename, buffer)
        .then(result => equal(result, binary, 'isBinaryPromise'))
        
      equal(isTextBinary.isBinary(flename, buffer), binary, 'isBinary sync')
      isTextOrBinary.isBinary(filename, buffer, (error, result) =>
        equal(result, binary, 'isBinary async')
      )
      
      equal(isTextOrBinary.getEncodingSync(buffer), encoding, 'getEncodingSync')
      isTextOrBinary.getEncodingCallback(buffer, null, (error, result) => 
        equal(result, encoding, 'getEncodingCallback')
      )
      isTextOrBinary
        .getEncodingPromise(buffer)
        .then(result => equal(result, encoding, 'getEncodingPromise'))
      equal(isTextOrBinary.getEncoding(buffer), encoding, 'getEncoding sync')
      isTextOrBinary.getEncoding(buffer, null, (error, result) =>
        equal(result, encoding, 'geEncoding async')
      )
    })
  })
})
```

```
```

```
```


