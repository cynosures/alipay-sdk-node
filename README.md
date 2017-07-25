# alipay-sdk-node

[![JavaScript Style Guide][style-image]][style-url]
[![Build Status][travis-image]][travis-url]

[style-image]: https://img.shields.io/badge/code_style-standard-brightgreen.svg
[style-url]: https://standardjs.com
[travis-image]: https://travis-ci.org/cynosures/alipay-sdk-node.svg?branch=master
[travis-url]: https://travis-ci.org/cynosures/alipay-sdk-node

---
## Install

```bash
 $ npm install alipay-sdk-node --save
```
---

## Usage

### Create Alipay Instance

e.g.
```js
  const Alipay = require('alipay-sdk-node')
  const alipay = new Aliapy({
    app_id: 'xxx',
    app_private_key: 'xxx',
    alipay_public_key: 'xxx',
    sign_type: 'RSA2',
    notify_url: 'xxx'
  })
```

### APP Pay
* `#getOrderInfoStr(biz_content)`: get the string of order info
* params: biz_content {JSON} [click](https://docs.open.alipay.com/204/105465/)
* return: String

e.g.
```js
  alipay.getOrderInfoStr({
    subject: 'xxx',
    out_trade_no: 'xxx',
    total_amount: 'xxx',
    product_code: 'xxx'
  })
```

### Check sign
* `#rsaCheck(options)`: check sign
* params: request body {JSON} [click](https://docs.open.alipay.com/204/105301/)
* return: Boolean

e.g.
```js
  alipay.rsaCheck(request.body)
```

### Refund
* `#refund(biz_content[,callback])`: refund api
* params: biz_content {JSON} [click](https://docs.open.alipay.com/api_1/alipay.trade.refund)
* return: Promise Or Callback

e.g.
```js
  alipay.refund({
    out_trade_no: 'xxx',
    trade_no: 'xxx',
    refund_amount: 'xxx',
    out_request_no: 'xxx',
    refund_reason: 'xxx'
  })
```
---
