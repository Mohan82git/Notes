 PPT making gamma, popai

Skip the questions, later edit things in package.json
``` bash
npm init -y
  ```
  
Single package install :  
```bash
npm install package-name
```

Multiple packages installs :  
```bash
npm install pkg1 pkg2 pkg3
```

 **Packages are nothing but the code borrowed by someone else** 

learn node.js 	: https://nodejs.org/en/learn/getting-started/introduction-to-nodejs
learn npm 	: https://docs.npmjs.com/getting-started

When we do npm init, our new project gets started, but when we do npm install package, package gets installed in only that specific project so if we want to install packages for whole computer
``` bash
npm install --global 
```

New node server (Sample code)

``` js
const { createServer } = require('node:http');

const hostname = '127.0.0.1';
const port = 3000;

const server = createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

Start server: 
``` bash
node "File-path"
```

Stop server : `Ctrl + C`

We need to manually restart the server if code changes...
so to avoid this, 
``` bash
npm install --global nodemon
```

Here text/plain is used to tell the server that which type of data we are providing to it
``` js
res.setHeader("Content-Type", "text/plain");
```

Group of many modules = 1 Package ( e.g. helllo.py is a module)

Comman JS : Using require(...), you can import any of the module in the package
``` js
const { createServer } = require("node:http");
```

EcmaScript"  : Using import, you can import any of the module in the package
``` js
import http from "http"
```

We define the type of project whether it is ecmascript or command js, go to package.json
ecmascript = es6
commonjs = common js

add: in package.json 
	`"type" : "commonjs" `   //Default value
OR `"type" : "module"`

## Some import and export

File structure
sigma/main.js
sigma/second.js

# EcmaScript  
( "Type" : "module" )
### Method 1 :  To import and export values

**main.js**
``` js
import {a, b, d, e} from "./second.js"
console.log(a, b, d, e)
```

``` Output
99 88 66 77
```

**Second.js**
``` js
export const a = 99; // named export
export const b = 88; // named export
export const c = 77; // named export
export const d = 66; // named export
export const e = 77; // named export
```

### Method 2 :  To import and export values

**main.js**
``` js
import obj from "./second.js"
import mohan from "./second.js"
// here we can import same object by any name, because it is default export

console.log(obj)
```

``` Output
{ x: 5, y: 7 }
```

**Second.js**
``` js
let obj = {
	x: 5,
	y: 7
};

export default obj;
```

# CommonScript
(Default, remove "Type" : "commonscript" )
### Method 1 :  To import and export values

**main.js**
``` js
const a = require("./second.js")
console.log(a)
```

``` Output
{ x: 1, y: 2 }
```

**Second.js**
``` js
module.exports = {
	x: 1,
	y: 2 
}
```

Whatever you put after exports = ....
that get imported in main.js
```
module.exports = c;
module.exports = 23;
module.exports = "Hello dear  !!"
```

if we do require and import this stuff, that file becomes a module, so we need to specify it in html

```html
<script type="Module" src ="Location..."></script>
```

# 86 - 15:45