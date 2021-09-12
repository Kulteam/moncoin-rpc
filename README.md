# MONCoin RPC

[![NPM](https://nodei.co/npm/moncoin-rpc.png?downloads=true&stars=true)](https://nodei.co/npm/moncoin-rpc/)


#### Master Build Status
[![Build Status](https://travis-ci.org/turtlecoin/moncoin-rpc-js.png?branch=master)](https://travis-ci.org/turtlecoin/moncoin-rpc-js) [![Build Status](https://ci.appveyor.com/api/projects/status/github/brandonlehmann/moncoin-rpc?branch=master&svg=true)](https://ci.appveyor.com/project/brandonlehmann/moncoin-rpc/branch/master)

This project is designed to make it very easy to interact with various RPC APIs available within the [MONCoin](https://turtlecoin.lol) Project. This entire project uses [Javascript Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises) to make things fast, easy, and safe.

## Package Upgrade Warning

v2.0.0+ contains multiple breaking changes to the package including the removal of support for MONCoin-Service, removal of deprecated MONCoind RPC calls that will be removed, renaming of methods, and method argument changes throughout. Please be sure to read the documentation in full before upgrading to v2.0.0+.

## Table of Contents

1. [Dependencies](#dependencies)
2. [Installation](#installation)
3. [Intialization](#intialization)
4. [Documentation](#documentation)

## Dependencies

* [NodeJS v8.x](https://nodejs.org) >= 8.x
* [MONCoin](https://github.com/Kulteam/MONCoin/releases) >= v0.8.4

## Installation

```bash
npm install --save moncoin-rpc
```

### Legacy Version

If you require support for `mon-service` interaction, please install v1.0.3 instead of the current release. For the documentation for the legacy version, please see the [v1.0.3 docs](https://www.npmjs.com/package/moncoin-rpc/v/1.0.3)

```bash
npm install --save moncoin-rpc@1.0.3
```

## Intialization

### MONCoind
```javascript
const MONCoind = require('moncoin-rpc').MONCoind

const daemon = new MONCoind({
  host: '127.0.0.1', // ip address or hostname of the MONCoind host
  port: 12898, // what port is the RPC server running on
  timeout: 2000, // request timeout
  ssl: false, // whether we need to connect using SSL/TLS
  userAgent: 'moncoin-rpc/2.0.0' // specify a customer user-agent or use the default
})
```

### Wallet-API
```javascript
const WalletAPI = require('moncoin-rpc').WalletAPI

const wallet = new WalletAPI({
  host: '127.0.0.1', // ip address or hostname of wallet-api host
  port: 8070, // port wallet-api is running on, default is 8070
  timeout: 5000, // how long to wait before timing out the connection
  ssl: false, // whether or not to connect through SSL
  password: 'password', // your rpc password
  defaultMixin: 3, // should be configured to the default mixin, or false if no default mixin is set
  defaultFee: 0.1, // the default fee of your network, in decimal not atomic units
  decimalDivisor: 1000000000, // how many decimals will be used
  defaultUnlockTime: 0, // default unlock time
  userAgent: 'moncoin-rpc/2.0.0' // specify a customer user-agent or use the default
})
```

## Documentation

You can find the full documentation for this library [here](https://moncoin.io)

## License

```
Copyright (C) 2020-2021 Brandon Lehmann, The MONCoin and TurtleCoin Developers

Please see the included LICENSE file for more information.
```
