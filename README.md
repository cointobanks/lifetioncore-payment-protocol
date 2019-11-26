# lifetioncore-payment-protocol
==============================

[![NPM Package](https://img.shields.io/npm/v/lifetioncore-payment-protocol.svg?style=flat-square)](https://www.npmjs.org/package/lifetioncore-payment-protocol)
[![Build Status](https://img.shields.io/travis/cointobanks/lifetioncore-payment-protocol.svg?branch=master&style=flat-square)](https://travis-ci.org/cointobanks/lifetioncore-payment-protocol)
[![Coverage Status](https://img.shields.io/coveralls/cointobanks/lifetioncore-payment-protocol.svg?style=flat-square)](https://coveralls.io/r/cointobanks/lifetioncore-payment-protocol)

A module for [lifetioncore](https://github.com/cointobanks/lifetioncore) that implements [Payment Protocol](https://github.com/bitcoin/bips/blob/master/bip-0070.mediawiki) and other related BIPs.

## Getting Started

This library is distributed in both the npm and bower packaging systems.

```sh
npm install lifetioncore-lib
npm install lifetioncore-payment-protocol
```

There are many examples of how to use it on the developer guide [section for payment protocol](https://bitcore.io/api/paypro). For example, the following code would verify a payment request:

```javascript
const PaymentProtocol = require('lifetioncore-payment-protocol');

const body = PaymentProtocol.PaymentRequest.decode(rawbody);
const request = new PaymentProtocol().makePaymentRequest(body);

const version = pr.get('payment_details_version');
const pki_type = pr.get('pki_type');
const pki_data = pr.get('pki_data');
const serializedDetails = pr.get('serialized_payment_details');
const signature = pr.get('signature');

// Verify the signature
const verified = request.verify();
```

## Contributing

See [CONTRIBUTING.md](https://github.com/cointobanks/lifetioncore/blob/master/CONTRIBUTING.md) on the main lifetioncore repo for information about how to contribute.

## License

Code released under [the MIT license](https://github.com/cointobanks/lifetioncore/blob/master/LICENSE).

Copyright 2013-2015 BitPay, Inc. Bitcore is a trademark maintained by BitPay, Inc.
