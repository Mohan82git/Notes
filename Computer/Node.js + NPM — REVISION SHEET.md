
📔Documentation  node js : nodejs.org

## 🧩 NPM BASICS

### Start Project

```bash
npm init        # with questions
npm init -y     # no questions
```

📌 Creates → `package.json` (project identity)

---
### Install Packages

```bash
npm install pkg-name          # local (project only)
npm install pkg1 pkg2 pkg3    # multiple
npm install -g pkg-name       # global (whole system)
```

🧠 **Package = borrowed code**

Get different different packages : 
npmjs.com/packages

---

## 🖥️ RUN NODE SERVER

```bash
node file.js
```

Stop → `Ctrl + C`

### Auto-restart server

```bash
npm install -g nodemon
nodemon file.js
```

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

---

## 📦 MODULES & PACKAGES

- **Package** → collection of modules
	- **Module** → single file (`math.js`)

 in our project modules stored as `node_modules`
 and **NEVER PUSH NODE MODULES TO GITHUB**


---

## 🔀 COMMONJS vs ESM

|Feature|CommonJS|ESM|
|---|---|---|
|Import|`require()`|`import`|
|Export|`module.exports`|`export`|
|Default|✅ Node default|❌|
|package.json|`"type": "commonjs"`|`"type": "module"`|

---

## 📄 package.json TYPE

```json
"type": "commonjs"   // default
```

OR

```json
"type": "module"
```

📌 Decides **import / export syntax**

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

## 🌍 MODULE IN BROWSER

```html
<script type="module" src="app.js"></script>
```

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
path.extname(file)     // .txt
path.dirname(file)    // folder path
path.join(a, b)       // safe join
```

---
