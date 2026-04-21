### Documentation link : [Express - Node.js web application framework](https://expressjs.com/)

### Installation :  

```js
npm i express
```

### Sample server

```js
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})

```

## Explaination :

``` js
app.get('/', (req, res) => {
  res.send('Hello World!')
})
```

here `.get` is a one of the request browser sends to the server

/ is a endpoint where the server's respose is shown

### Example usage

``` js
app.get('/subscribe', (req, res) => {
  res.send('Buy me a coffee')
})
```

``` js
app.get('/blog', (req, res) => {
  res.send('welcome to my blog')
})
```

``` js
app.get('/blog/python', (req, res) => {
  res.send('This is python')
})
```

``` js
app.get('/blog/java', (req, res) => {
  res.send('intro to python')
})
```

### Universal endpoint : (variables)
if we hit the pre defined endpoints it will show whatever I want,
but what if there is custom endpointss??

``` js
app.get('/blog/:slug', (req, res) => {
  res.send('Welcome to ${req.params.slug}')
})
```
e.g blog/:slug/:prank/:ragebait....
e.g blog/:prank/:ragebait....
e.g blog/:ragebait....

### Instead of creating endpoints for blog/... in a single file, we can organize the endpoints in separate file
(For organized and maintainable code)

### Analysing the request 

```js
app.get('/blog/:slug', (req, res) => {
  console.log(req)
})
```

# 📁 Serving the files 

### 1. Make a folder by any name e.g. public 
### 2. Add files there
### 3. Use the syntax
```js
app.use(express.static('public'))
```

You can add multiple folders
```js
app.use(express.static('public'));

app.use(express.static('files'));

app.use(express.static('src'));

```


### Types of request sent to Server
```js
// To Read the data
app.get('/blog/:slug', (req, res) => {
  console.log(req)
})
```

```js
// To Create the data
app.post('/blog/:slug', (req, res) => {
  console.log(req)
})
```

```js
// To Update the data
app.put('/blog/:slug', (req, res) => {
  console.log(req)
})
```

```js
app.delete('/blog/:slug', (req, res) => {
  console.log(req)
})
```



### Old method : To test the requests

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
<script>
  async function testAPI() {
    let a = await fetch("/", {method: "POST"})
    let b = await a.text();
    console.log(b);
  }
</script>
</body>
</html>
```
change {method: "POST"}, "PUT", "LISTEN"....

# Chaining of requests


```js
// To Update the data
app.put('/blog/:slug', (req, res) => {
  console.log(req)
  
}).delete('/blog/:slug', (req, res) => {
  console.log(req)
  
})
```


## Sending files as a response

```js
app.get('/blog/:slug', (req, res) => {
 res.sendFile('templates/index.html',  {root : __dirname})
});
```

`{root : __dirname}` this is very important, For security resons, express uses only folder spcified by us

**💡 Try this : Below are some other methods for res **

| Method           | Description                                                                  |
| ---------------- | ---------------------------------------------------------------------------- |
| res.download()   | Prompt a file to be downloaded.                                              |
| res.end()        | End the response process.                                                    |
| res.json()       | Send a JSON response.                                                        |
| res.jsonp()      | Send a JSON response with JSONP support.                                     |
| res.redirect()   | Redirect a request.                                                          |
| res.render()     | Render a view template.                                                      |
| res.send()       | Send a response of various types.                                            |
| res.sendFile()   | Send a file as an octet stream.                                              |
| res.sendStatus() | Set the response status code and send its string representation as the body. |

### Creating our api

```js
app.get("/api", (req, res) => {
    res.json({ a: 1, b: 2, c: 3, d: 4, name: ["harry", "jerry"] })
})
```

# Testing API - 👑Postman

	Create workspace and start the putting requests, you can save the requets collections

# Express router : Organising endpoints

Jaise hum alag alag pdf files drive mein alag alag folders mein save karte hein, same ussi tarah alag alag enpoints hum alag alag .js files mein save karte hein

e.g 

Main website : main.js
www.mb.com/

products : products.js
www.mb.com/sheets
www.mb.com/graphics
www.mb.com/matlab


Main.js < /> : Add this code in main.js (main js file)
```js
const express = require('express')
const products = require('./routes/products')

app.use('/products', products)
```


products.js

```js
const express = require('express')
const router = express.Router()

// define the home page route
router.get('/', (req, res) => {
  res.send('Products home page')
})

// define the about route
router.get('/about', (req, res) => {
  res.send('About products')
})
 

module.exports = router
```


# Middleware in Express Js
#### Sometimes we do the same thing for every request, so just like CSS can target all elements at once, middleware lets us handle all requests easily
### `app.get()` = Rooms in a hotel  
### 👉 Middleware = pre-processing / Entrance gate

```js


// Middleware syntax
app.use((req, res, next) => {
    console.log('m2')
    req.harry = "I am Rohan bhai";
    next()
})
```

Example : 

```js
app.use((req, res, next) => {
    console.log(req.headers)
    req.harry = "I am harry bhai";
    fs.appendFileSync("logs.txt", `${Date.now()} is a ${req.method}\n`)
    console.log(`${Date.now()} is a ${req.method}`)
    // res.send("Hacked by Middlware 1")
    next()
})
```



Steps : 

Gather the extensions in array or whatever
dont gather repeated once
then make folder for each array
then check each files and move to the folder according to the extension


https://youtu.be/SksvlZM-5Sk?list=PLu0W_9lII9agq5TrH9XLIKQvv0iaF2X3w&t=1556





