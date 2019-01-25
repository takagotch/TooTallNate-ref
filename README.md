### ref
---
https://github.com/TooTallNate/ref

```
npm install ref

npm install
npm run docs
```

```js
var ref = require('ref');
var buf = new Buffer(4)
buf.writeInt32LE(12345, 0)
console.log(buf.hexAddress())
buf.type = ref.types.int
console.log(buf.deref())
var one = buf.ref()
console.log(one.deref().deref())

var ref = require('ref')
var bigint = require('bigint')
var BigintType = {
  size: ref.sizeof.int64
, indirection: 1
, get: function(buffer, offset){
  return bigint.fromBuffer(buffer)
}
, set: function(buffer, offset, value){
  var val = value.toString()
  return ref.writeInt64(buffer, offset || 0, val)
  }
}
buf.type = BigintType
var val = buf.deref()
  .add('1234')
  .sqrt()
  .shiftLeft(5)
  
```

```
```


