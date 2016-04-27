What is Node Js

Node is running Js on the server. It is popular

NPM (Node Package Management)

 

###Installing a node package


- npm install express //express is a package
Including and using the package
```
var express = require("express");
var app = express();

```
- Creating a node js file under the name app.js

```
npm install express //express is a package
```


- Including and using the package


```
var express = require("express");
var app = express();


//telling the node server to start
app.listen(process.env.PORT, process.env.IP, function(){ console.log("server has started!")});

```

- JSON files

JSON files are files that hold information that is useful to API’s and other servers

 -- creating a json file
```
//
npm init

// to save some information from a package to the json file we use --save

npm install express --save
Route parameters

//similar to a 404 
app.get("*", function(req,res){
     res.send("Hola, Commo.");
})

//Root route , homepage
app.get("/", function(req,res){
     res.send("Hi, there");
})

//another root
app.get("/bye", function(req,res){
     res.send("Goodbye");
})

```

-- Parameters

Similar to creating dynamic routes and not statistics
```
app.get("/r/:projects/:id/:title", function(req,res){
     res.send("My Project!");
})

```
### EJS ( Embedded Javascript )

EJS is a package that allow html on pages, this html files are saved with an extension of “.ejs”.

```
$ npm install ejs

//the ejs files are stored in a folder called views
$ mkdir views

//creating a home file in the views folder
$ touch views/home.ejs

//setting home.ejs as the root 
app.get("/", function(req,res){
     res.send("home.ejs");
})
```

