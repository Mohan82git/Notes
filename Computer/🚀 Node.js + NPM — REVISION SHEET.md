
Learn nodejs via nodejs.org

## 🧩 NPM BASICS

### Start Project

```bash
npm init        # with questions
npm init -y     # no questions
```

📌 Creates → `package.json` (project identity)
Package json story : 
- whenever we install any packages for our project its name gets stored in `package.json` and files gets stored in `node_modules` 
- it contains the list of packages we use for our project and it also works as a backup so even by mistake we delete the `node_modules`, just hit ``` 
- ```bash
  npm -i
  ```
  we can restore the packages


---
### Install Packages

```bash
npm install pkg-name          # local (project only)
npm install pkg1 pkg2 pkg3    # multiple
npm install -g pkg-name       # global (whole system)
```

🧠 **Package = borrowed code**

Explore packages in npm website
Get different different packages : 
npmjs.com/packages

---
## 🌐 SIMPLE NODE SERVER (Skeleton)

```js
const { createServer } = require("node:http");

createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader("Content-Type", "text/plain");
  res.end("Hello World");
}).listen(3000);
```

📌 `Content-Type` → tells browser **what data is sent**
e.g. text/html => for html content

---
## 🖥️ RUN NODE SERVER

```bash
node file.js
```

Stop → `Ctrl + C`

### Auto-restart server (nodemon)

```bash
npm install -g nodemon
nodemon file.js
```

---
## 📦 MODULES & PACKAGES

- **Package** → collection of modules
	- **Module** → single file (`math.js`)   
Stored in `node_modules`
We **NEVER PUSH NODE MODULES TO GITHUB**

---

## 🔀 COMMONJS vs ESM

|Feature|CommonJS|ESM|
|---|---|---|
|Import|`require()`|`import`|
|Export|`module.exports`|`export`|
|Default|✅ Node default|❌|
|package.json|`"type": "commonjs"`|`"type": "module"`|


---

## 🔁 IMPORT & EXPORT

### 🟢 ESM (type = module)

#### Named export

```js
export const a = 10;
import { a } from "./file.js";
```

#### Default export

```js
export default obj;
import anyName from "./file.js";
```

🧠 **Default → any name allowed**

---

### 🔵 CommonJS

```js
module.exports = { x: 1 };
const data = require("./file.js");
```

📌 Whatever after `module.exports =` gets imported

---

## 🌍To use MODULE IN BROWSER

```html
<script type="module" src="app.js"></script>
```


---

## 📄 To run on server : package.json TYPE

```json
"type": "commonjs"   // default for common js
```

OR

```json
"type": "module"   //for EcmaScript
```

📌 Decides **import / export syntax**

---


## 🔄 NVM

📌 Manages **multiple Node.js versions** on one system

---

## 🧠 COMMONJS MAGIC

```js
(function (exports, require, module, __filename, __dirname) {
  // your code
})
```

📌 That’s why `__filename`, `__dirname` exist

---

## 📁 FS MODULE (File System)

```js
const fs = require("fs");
```

⚠️ JS = **Asynchronous**

### Core Methods

```js
fs.writeFileSync("a.txt", "data");   // blocking
fs.writeFile("a.txt", "data", cb);   // non-blocking
fs.readFile("a.txt", cb);            // buffer → toString()
fs.appendFile("a.txt", "more", cb);
```

---

## 📂 PATH MODULE

```js
import path from "path";
```

### Must-Know Methods

```js
path.extname(file)     // view file extention .txt, .pdf
path.dirname(file)    // folder path
path.join(a, b)       // safe join

```
f
---
## 📂 Working with files (fs and path modules)


### To view all the fs module functions

```js
const fs = require("fs")

console.log(fs);
```

### 1. Write operation

``` js

 fs.writeFile("harry2.txt", "Harry is a good boy2", ()={
	   console.log("Done")
})
```


### 2. Read operation

``` js

 fs.readFile("harry2.txt", (error, data)={
	   console.log(error, data.toString);
})
```

### 3. Append
``` js

 fs.writeFile("harry2.txt", "Harry is a good boy2", ()={
	   console.log("Done")
})
```


## 📂 Path modules)


### To view all the path module functions

```js
const path = require("path")

console.log(path);
```

 