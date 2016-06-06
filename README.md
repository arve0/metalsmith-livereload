# metalsmith-livereload

Starts a [livereload] server and injects client side livereload script before `</body>` to all `.html`-files.

## Install
```sh
npm install metalsmith-livereload
```

## Usage
```js
Metalsmith(__dirname)
  .use(changed())  // metalsmith-changed
  .use(markdown())
  .use(livereload({
    // defaults
    debug: false,  // print debug messages
    script: '<script ...'  // livereload script to inject
  }))
  .build((err, files) => {
    if (err) return console.log(err);
    let filenames = Object.keys(files).join(', ');
    console.log('Built: ' + filenames);
  });
```

[livereload]: https://www.npmjs.com/package/livereload
