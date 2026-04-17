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


