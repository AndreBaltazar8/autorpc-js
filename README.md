# AutoRPC for JS
Simple RPC library that allows to expose functions to be called remotely and also allows to call remote functions easily.

# Example

```javascript
// for simple chat service
let ws = new WebSocket('ws://localhost/')
ws.onopen = function() {
    let service = autorpc.useConnection(ws, {
        'Message': ['string']
    }, {
        'Message': function(text) {
            console.log('other sent message:', text)
        }
    })

    service.Message('hello')
}
```

# About
The AutoRPC JS project was created to be used by the [Nuntius](https://lab.andrebaltazar.com/?p=nuntius) protocol.

# License
The AutoRPC JS project is released under the MIT license. For the full license see LICENSE file.
