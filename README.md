### yajrpc
---
https://github.com/dcousens/yajrpc

```js
let Yajrpc = require('yajrpc')
let rpc = new YajRPC({
  url: 'http://localhost:8332',
  user: process.env.RPCUSER,
  pass: process.env.RPCPASSWORD
})

rpc.call('func1', [1, 2, 3], (err, result) => {
})

rpc.batch([{
  method: 'func1',
  params: [1, 2, 3],
  callback: (err, result) => {
  }
}, ], function (err) { ... })


let quq = require('quq')
let Yajrpc = require('yajrpc')

let client = new Yajrpc({
  url: process.env.RPC,
  user: process.env.RPCUSER,
  pass: process.env.RPCPASSWORD
})

let q = quq((batch, callback) => {
  client.batch(batch, callback)
}, process.env.RPCCONCURRENT, process.env.RPCBATCHSIZE)

function rpc (method, params, callback) {
  q.push({ method, params, callback })
}

rpc('func1', [1, 2, 3], ...)
```

```
```

```
```


