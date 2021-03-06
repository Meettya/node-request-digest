# Request digest client in Node.js [![Build Status](https://travis-ci.org/bnjjj/node-request-digest.svg?branch=master)](https://travis-ci.org/bnjjj/node-request-digest)
[![NPM](https://nodei.co/npm/request-digest.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/request-digest/)

Perform a client request (http) with a digest authentication

## Disclaimer

Only tested against one server and spec is not followed fully. It works for me
and for what I am doing.
Pay attention, it only works with MD5 algorithm currently.

## Usage
```javascript
var digestRequest = require('request-digest')('username', 'password');
digestRequest.request({
  host: 'http://test.com',
  path: '/api/v1/test.json',
  port: 80,
  method: 'GET',
  headers: {
    'Custom-Header': 'OneValue',
    'Other-Custom-Header': 'OtherValue'
  }
}, function (error, response, body) {
  if (error) {
    throw error;
  }

  console.log(body);
});
```

The digest client will make one request to the server, authentication response
is calculated and then the request is made again. Hopefully you will then
be authorized.

## Contributions

Feel free to contribute and extend this package and if you have bugs or if you want more specs make an issue. Have fun !

-------------

Made by [Coenen Benjamin](https://twitter.com/BnJ25) with love
