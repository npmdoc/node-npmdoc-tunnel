# api documentation for  [tunnel (v0.0.4)](https://github.com/koichik/node-tunnel/)  [![npm package](https://img.shields.io/npm/v/npmdoc-tunnel.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-tunnel) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-tunnel.svg)](https://travis-ci.org/npmdoc/node-npmdoc-tunnel)
#### Node HTTP/HTTPS Agents for tunneling proxies

[![NPM](https://nodei.co/npm/tunnel.png?downloads=true)](https://www.npmjs.com/package/tunnel)

[![apidoc](https://npmdoc.github.io/node-npmdoc-tunnel/build/screenCapture.buildNpmdoc.browser.%252Fhome%252Ftravis%252Fbuild%252Fnpmdoc%252Fnode-npmdoc-tunnel%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-tunnel/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-tunnel/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-tunnel/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Koichi Kobayashi",
        "email": "koichik@improvement.jp"
    },
    "bugs": {
        "url": "https://github.com/koichik/node-tunnel/issues"
    },
    "dependencies": {},
    "description": "Node HTTP/HTTPS Agents for tunneling proxies",
    "devDependencies": {
        "mocha": "*",
        "should": "*"
    },
    "directories": {
        "lib": "./lib"
    },
    "dist": {
        "shasum": "2d3785a158c174c9a16dc2c046ec5fc5f1742213",
        "tarball": "https://registry.npmjs.org/tunnel/-/tunnel-0.0.4.tgz"
    },
    "engines": {
        "node": ">=0.6.11 <=0.7.0 || >=0.7.3"
    },
    "gitHead": "f2dfda3c8df1f75c62ab410d239f70b73aa3145b",
    "homepage": "https://github.com/koichik/node-tunnel/",
    "keywords": [
        "http",
        "https",
        "agent",
        "proxy",
        "tunnel"
    ],
    "license": "MIT",
    "main": "./index.js",
    "maintainers": [
        {
            "name": "koichik",
            "email": "koichik@improvement.jp"
        }
    ],
    "name": "tunnel",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/koichik/node-tunnel.git"
    },
    "scripts": {
        "test": "./node_modules/mocha/bin/mocha"
    },
    "version": "0.0.4"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module tunnel](#apidoc.module.tunnel)
1.  [function <span class="apidocSignatureSpan">tunnel.</span>debug ()](#apidoc.element.tunnel.debug)
1.  [function <span class="apidocSignatureSpan">tunnel.</span>httpOverHttp (options)](#apidoc.element.tunnel.httpOverHttp)
1.  [function <span class="apidocSignatureSpan">tunnel.</span>httpOverHttps (options)](#apidoc.element.tunnel.httpOverHttps)
1.  [function <span class="apidocSignatureSpan">tunnel.</span>httpsOverHttp (options)](#apidoc.element.tunnel.httpsOverHttp)
1.  [function <span class="apidocSignatureSpan">tunnel.</span>httpsOverHttps (options)](#apidoc.element.tunnel.httpsOverHttps)



# <a name="apidoc.module.tunnel"></a>[module tunnel](#apidoc.module.tunnel)

#### <a name="apidoc.element.tunnel.debug"></a>[function <span class="apidocSignatureSpan">tunnel.</span>debug ()](#apidoc.element.tunnel.debug)
- description and source-code
```javascript
debug = function () {}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.tunnel.httpOverHttp"></a>[function <span class="apidocSignatureSpan">tunnel.</span>httpOverHttp (options)](#apidoc.element.tunnel.httpOverHttp)
- description and source-code
```javascript
function httpOverHttp(options) {
  var agent = new TunnelingAgent(options);
  agent.request = http.request;
  return agent;
}
```
- example usage
```shell
...
  $ npm install tunnel

## Usages

### HTTP over HTTP tunneling

'''javascript
var tunnelingAgent = tunnel.httpOverHttp({
maxSockets: poolSize, // Defaults to 5

proxy: { // Proxy settings
  host: proxyHost, // Defaults to 'localhost'
  port: proxyPort, // Defaults to 80
  localAddress: localAddress, // Local interface if necessary
...
```

#### <a name="apidoc.element.tunnel.httpOverHttps"></a>[function <span class="apidocSignatureSpan">tunnel.</span>httpOverHttps (options)](#apidoc.element.tunnel.httpOverHttps)
- description and source-code
```javascript
function httpOverHttps(options) {
  var agent = new TunnelingAgent(options);
  agent.request = https.request;
  return agent;
}
```
- example usage
```shell
...
agent: tunnelingAgent
});
'''

### HTTP over HTTPS tunneling

'''javascript
var tunnelingAgent = tunnel.httpOverHttps({
maxSockets: poolSize, // Defaults to 5

proxy: { // Proxy settings
  host: proxyHost, // Defaults to 'localhost'
  port: proxyPort, // Defaults to 443
  localAddress: localAddress, // Local interface if necessary
...
```

#### <a name="apidoc.element.tunnel.httpsOverHttp"></a>[function <span class="apidocSignatureSpan">tunnel.</span>httpsOverHttp (options)](#apidoc.element.tunnel.httpsOverHttp)
- description and source-code
```javascript
function httpsOverHttp(options) {
  var agent = new TunnelingAgent(options);
  agent.request = http.request;
  agent.createSocket = createSecureSocket;
  return agent;
}
```
- example usage
```shell
...
# node-tunnel - HTTP/HTTPS Agents for tunneling proxies

## Example

'''javascript
var tunnel = require('tunnel');

var tunnelingAgent = tunnel.httpsOverHttp({
  proxy: {
    host: 'localhost',
    port: 3128
  }
});

var req = https.request({
...
```

#### <a name="apidoc.element.tunnel.httpsOverHttps"></a>[function <span class="apidocSignatureSpan">tunnel.</span>httpsOverHttps (options)](#apidoc.element.tunnel.httpsOverHttps)
- description and source-code
```javascript
function httpsOverHttps(options) {
  var agent = new TunnelingAgent(options);
  agent.request = https.request;
  agent.createSocket = createSecureSocket;
  return agent;
}
```
- example usage
```shell
...
agent: tunnelingAgent
});
'''

### HTTPS over HTTPS tunneling

'''javascript
var tunnelingAgent = tunnel.httpsOverHttps({
maxSockets: poolSize, // Defaults to 5

// CA for origin server if necessary
ca: [ fs.readFileSync('origin-server-ca.pem')],

// Client certification for origin server if necessary
key: fs.readFileSync('origin-server-key.pem'),
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
