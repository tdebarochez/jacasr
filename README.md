Jacasr
======

About
-----

#### Pure JS XMPP library for NodeJS ####

Jacasr is a library for [NodeJS](http://nodejs.org) that implements the basics of xmpp protocol

Requirements
------------

- [nodejs](http://nodejs.org)
- [sax-js](https://github.com/isaacs/sax-js)

Grab the code
--------------

Check out source with

    $ git clone git://github.com/tdebarochez/jacasr.git

Installation
------------

`npm install jacasr`

Usage
-----

You can find a full featured application with [LePote](http://tdebarochez.github.com/lepote/) bot.
However this is the basic usage :

```js
    var jacasr = require('jacasr');
    var conf = {login: 'user',
                password: 'pass',
                domain: 'server.com'};
    var client = new jacasr.Client(conf);
    client.on('message', function (from, message) {
      if (/^hi/i.exec(message)) {
        this.push(from, 'Hi there');
      }
      else if (/^how are you/i.exec(message)) {
        this.push(from, 'Fine and you ?');
      }
      else if (/bye/i.exec(message)) {
        this.push(from, 'Good bye !');
      }
    });
```

API
-----

For the full API, take a look at [documentation](http://tdebarochez.github.com/jacasr/).

License
-------

Jacasr is licensed under the terms of the MIT License, see the included LICENSE file.