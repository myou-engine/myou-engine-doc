
# About myou-engine-doc

This repository contains the source for the documentation of myou-engine.

To read the documentation online, go [here](http://myou.cat/engine/doc/).

To read the documentation offline, install [myou-tool](https://github.com/myou-engine/myou-tool/) and run `myou-tool help`.

# Contributing

The documentation uses [Codo](https://github.com/coffeedoc/codo) to generate API docs from [myou-engine](https://github.com/myou-engine/myou-engine) source code, as well as rendering the markdown files contained in this repository into the official manual. It uses a [custom codo theme](https://github.com/myou-engine/codo-theme-myou).

All manual files are listed in the file `.codoopts` in the order they should appear. Edit this file to add, remove, rename or move files of the manual around. Use `npm start` to build the documentation with codo.

TODO: Script that watches for changes and calls codo with just the changed files. Or modify codo for this purpose.

We'll probably move from codo to JSDoc after coffee-script 2 is ready and we use it for the engine to compile to native ES6 classes.
