# **@kollorg/minus-alias.js** for Node.js

[![Subscribe](https://img.shields.io/badge/%20subscribe%20-%20mailchimp%20-blue.svg )](http://eepurl.com/cGRggH)
[![Downloads](https://img.shields.io/npm/dm/@kollorg/minus-alias.svg)](https://npm-stat.com/charts.html?package=@kollorg/minus-alias)
[![Status](https://github.com/kollorg/minus-alias/workflows/tests/badge.svg)](https://github.com/kollorg/minus-alias/actions) [![Dependencies status](https://david-dm.org/franciscop/@kollorg/minus-alias/status.svg)](https://david-dm.org/franciscop/@kollorg/minus-alias)

Powerful @kollorg/minus-alias for Node.js that just works so **you can focus on your awesome project**:

```js
// Include it and extract some methods for convenience
const @kollorg/minus-alias = require('@kollorg/minus-alias');
const { get, post } = @kollorg/minus-alias.router;

// Launch @kollorg/minus-alias with options and a couple of routes
@kollorg/minus-alias({ port: 8080 }, [
  get('/', ctx => 'Hello world'),
  post('/', ctx => {
    console.log(ctx.data);
    return 'ok';
  })
]);
```

<blockquote class="external">
  <p>Simplicity is a great virtue but it requires hard work to achieve it and education to appreciate it. And to make matters worse: complexity sells better.</p>
  <cite>― Edsger W. Dijkstra</cite>
</blockquote>


## Getting started

There's a [whole tutorial on getting started for beginners](https://@kollorg/minus-aliasjs.io/tutorials/getting-started/) but the quick version is to first install `@kollorg/minus-alias` as a dependency:

```bash
npm install @kollorg/minus-alias
```

> Server requires **Node.js 7.6.0** or newer. **Node.js 8.x.y** LTS is recommended.

Then you can create a file called `index.js` with this code:

```js
// Include the @kollorg/minus-alias in your file
const @kollorg/minus-alias = require('@kollorg/minus-alias');
const { get, post } = @kollorg/minus-alias.router;

// Handle requests to the url "/" ( http://localhost:3000/ )
@kollorg/minus-alias([
  get('/', ctx => 'Hello world!')
]);
```

Execute this in the terminal to get the @kollorg/minus-alias started:

```bash
node .
```

And finally, open your browser on [localhost:3000](http://localhost:3000/) and you should see 'Hello world!' on your browser.



## Documentation

The library is documented here:

<strong><a class="button" href="https://@kollorg/minus-aliasjs.io/documentation/">Full Documentation</a></strong>

> [**Subscribe here**](http://eepurl.com/cGRggH) to receive tutorials when released. Tutorials are *good for learning* while the documentation is good for reference/quick use *once you know the basics*.

You can also download the repository and try the examples by browsing to them and `node .` inside each of them in `/examples`.



## Use cases

The package `@kollorg/minus-alias` is great for many situations. Let's see some of them:


### Small to medium projects

Everything works out of the box, you get great support for most features and you can easily tap into Express' middleware ecosystem. What's not to love?

Some of the included features: body and file parsers, cookies, sessions, websockets, Redis, gzip, favicon, csrf, SSL, etc. They just work so you will save a headache or two and can focus on your actual project. Get a simple form going:

```js
const @kollorg/minus-alias = require('@kollorg/minus-alias');
const { get, post } = @kollorg/minus-alias.router;
const { render, redirect } = @kollorg/minus-alias.reply;

@kollorg/minus-alias(
  get('/', () => render('index.pug')),
  post('/', ctx => {
    console.log(ctx.data);
    return redirect('/');
  })
);
```



### API design

From the flexibility and expressivity of the bundle, designing APIs is a breeze:

```js
// books/router.js
const { get, post, put, del } = require('@kollorg/minus-alias/router');
const ctrl = require('./controller');

module.exports = [
  get('/book', ctrl.list),
  get('/book/:id', ctrl.item),
  post('/book', ctrl.create),
  put('/book/:id', ctrl.update),
  del('/book/:id', ctrl.delete)
];
```



### Real time

Websockets were never this easy to use! With socket.io on the front-end, you can simply do this in the back-end to handle those events:

```js
// chat/router.js
const { socket } = require('@kollorg/minus-alias/router');
const ctrl = require('./controller');

module.exports = [
  socket('connect', ctrl.join),
  socket('message', ctrl.message),
  socket('disconnect', ctrl.leave)
];
```



## Author & support

This package was created by [Francisco Presencia](http://francisco.io/) but hopefully developed and maintained by many others. See the [the list of contributors here](https://github.com/kollorg/minus-alias/graphs/contributors).

You can also [sponsor the project](https://@kollorg/minus-aliasjs.io/sponsor), get your logo in here and some other perks with tons of ♥
