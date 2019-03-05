## Run a bcoin node in a web browser

![screenshot](https://raw.githubusercontent.com/pinheadmz/mobilebcoin/master/demo.gif "demo")

This repository is a work-in-progress update to the the bcoin browser full node
example described at [https://bcoin.io/guides/browser](https://bcoin.io/guides/browser)
and implemented at [https://bcoin.io/browser](https://bcoin.io/browser).

You can learn more about bundling JS for the browser with the [new guide about
building webapps with bcoin.](https://bcoin.io/guides/webapp.html)

### Files in this package:

#### Copied from bcoin
[wsproxy.js](https://github.com/bcoin-org/bcoin/blob/master/browser/wsproxy.js)

[server.js](https://github.com/bcoin-org/bcoin/blob/master/browser/server.js)
(modified and updated)

#### Bundled with [bpkg](https://github.com/chjj/bpkg)
[logger.js](https://github.com/bcoin-org/blgr/blob/master/lib/logger.js)

[format.js](https://github.com/bcoin-org/blgr/blob/master/lib/format.js)

[proxysocket.js](https://github.com/bcoin-org/bcoin/blob/master/browser/src/proxysocket.js)

[bcoin.js](https://github.com/bcoin-org/bcoin/blob/master/lib/bcoin.js) (This is
the main entry point for the entire bcoin library, including all objects and primitives)

#### Shiny and new
index.html

- Imports [bootstrap](https://getbootstrap.com/) from the
[bootstrap CDN](https://www.bootstrapcdn.com/) for a really nice UI

- Since the bcoin package is now bundled in advance, the actual node object is
configured and instantiated in the in-line JavaScript of this file. This means
that the node can be reconfigured for SPV mode, or different networks like `testnet`.

- The websocket proxy server can also be reconfigured. By default this app uses
the proxy server maintained by the bcoin development team at `browser.c4yt.io`.
However this repository also includes the proxy server module. To use the local
proxy server, (un)comment out the code in `index.html` where indicated and run
the local server with the command `node server.js`. Then navigate to `127.0.0.1:8080`
to load the webapp and connect to the Bitcoin network.

### Installation

```
git clone
npm install
```

### IMPORTANT WARNINGS

**Never enter a password or private key into an online computer**

**Web browsers are insecure environments for cryptography**

**This tool is for entertainment purposes only! Use at your own risk!**

### TODO

- [ ] Finish wallet: send TX / reveal mnemonic for backup / listen for TX events
- [ ] Better logging (scrollable history)
- [ ] Implement API access or interactive console
- [ ] Make options like SPV / WSProxy server accessible from front end
