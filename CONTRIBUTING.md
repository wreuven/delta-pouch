
Building
----
    npm install
    npm run build

Your plugin is now located at `dist/pouchdb.delta-pouch.js` and `dist/pouchdb.delta-pouch.min.js` and is ready for distribution.

Testing
----

### In Node

This will run the tests in Node:

    npm run node-test

You can also check for 100% code coverage using:

    npm run node-full-test

Run single test

    ./node_modules/mocha/bin/mocha -g '<regex>' test/index.js


### In the browser

    $ npm run browser-server
    Use any browser to visit http://127.0.0.1:8001/index.html
    And you can filter the tests, e.g. http://127.0.0.1:8001/index.html?grep=reg-ex


### Automated browser tests

phantomjs:

    $ npm run browser-test-phantomjs

You can also filter the tests, e.g.

    $ npm run browser-test-phantomjs -- -g reg-ex

Chrome:

Note: you must have Chrome installed

    $ npm run browser-test-phantomjs -- -b selenium:chrome

Firefox:

Note: you must have Firefox installed

    $ npm run browser-test-phantomjs -- -b selenium:firefox

Firefox and Chrome use IndexedDB and PhantomJS uses WebSQL.


Build & Publish
----
Let VERSION be the next version, something like 1.0.7

    tin -v VERSION
    npm run build
    git add -A
    git commit -m 'VERSION'
    git tag vVERSION
    git push origin master --tags
    npm publish
