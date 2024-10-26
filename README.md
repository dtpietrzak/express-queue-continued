# express-queue-continued
Express middleware to limit a number of simultaneously processing requests using queue - Continued due to OP being absent

If you have different needs regarding the functionality, please add a [feature request](https://github.com/dtpietrzak/express-queue-continued/issues).


The following is taken from [alykoshin's project](https://github.com/alykoshin/express-queue/)

## Installation

```sh
npm install --save express-queue
```

## Usage

```js
var express = require('express');
var queue = require('express-queue');
var app = express();

// Using queue middleware
app.use(queue({ activeLimit: 2, queuedLimit: -1 }));
// activeLimit - max request to process simultaneously
// queuedLimit - max requests in queue until reject (-1 means do not reject)
//
// May be also:
// app.get('/api', queue({ activeLimit: 2, queuedLimit: -1})
```

You can access MiniQueue object used internally. To get current queue length you may do following:

```js
const express = require('express');
const expressQueue = require('../');
const queueMw = expressQueue({ activeLimit: 2, queuedLimit: -1 });

const app = express();
app.use(queueMw);

console.log(`queueLength: ${queueMw.queue.getLength()}`);
```

For more info on Queue object used refer to [npmjs.com/package/mini-queue](https://www.npmjs.com/package/mini-queue) package docs and/or [source code](https://github.com/alykoshin/mini-queue). 

Here ends what was taken from [alykoshin's project](https://github.com/alykoshin/express-queue/)

## Reference (for now)

Please, refer to [alykoshin's project](https://github.com/alykoshin/express-queue/) for more details: 


## Credits
OP !!! Thank you much !!!
[Alexander](https://github.com/alykoshin/)

- just a guy
[David P.](https://davidp.dev)


## License

MIT
