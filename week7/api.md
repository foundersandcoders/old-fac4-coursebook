# The API

## What is REST?

* REST stands for _RE_presentational _S_tate _T_ransfer. This refers to transferring "representations". You are using a "representation" of a resource to transfer resource state which lives on the server into application state on the client. See image below:



![REST](http://yuml.me/ce0fe2f0 "REST")
* It is a software architecture style consisting of guidelines and best practices for creating scalable web services
* The use of REST is often preferred over the more heavyweight SOAP (Simple Object Access Protocol) style because REST does not leverage as much bandwidth, which makes it a better fit for use over the Internet

------

## What is CRUD?

* CRUD stands for _C_reate, _R_ead, _U_pdate and _D_elete
* Sometimes known as SCRUD - the S being Search
* For each letter in the CRUD acronym the HTTP Methods are as follows:
  * Create - POST (201 (Created), 'Location' header with link to /customers/{id} containing new ID.)
  * Read - GET (200 (OK), list of customers. Use pagination, sorting and filtering to navigate big lists.)
  * Update - PUT (404 (Not Found), unless you want to update/replace every resource in the entire collection.)
  * Delete - Delete (404 (Not Found), unless you want to delete the whole collection—not often desirable.)

 ------
## What is Routing?

* "Routing" means, we want to handle requests to different URLs differently
* Making different HTTP requests point at different parts of our code is called "routing"


 ------

## The server.js and handler.js files - a basic skeleton for the RESTful CRUD API

#### server.js

```
var http = require("http");
var handler = require("./handler");
var port = 4000;


//*** List of Routes and Associated Handler Functions ***//
var routes = {}
routes["/"] = handler.home;
routes["/create"] = handler.create;
routes["/update"] = handler.update;



//*** Invokes the right handler or throws error ***//
var router = function(req, res){
	var url = req.url;
	console.log("request received for ", url);


	if (typeof routes[url] === 'function'){
		routes[url](req, res); 
	} else {
		console.log('Error, route for ', url, 'does not exist');
		res.writeHead(404, {"Content-Type": "text/plain"});
	    res.end(" ERROR!!");
	}
}


http.createServer(router).listen(port);

console.log('Server running on port', port);

```

#### handler.js

```

module.exports = {


	home: function handler(req, res) {
		// console.log("Request for " + pathname + " received.");

	    res.writeHead(200, {"Content-Type": "text/plain"});
	    res.write("Welcome");
	    res.end(" to Testing");

	},

	create: function handler(req, res) {
		// console.log("Request for " + pathname + " received.");

	    res.writeHead(200, {"Content-Type": "text/plain"});
	    res.write("Welcome");
	    res.end(" to create article");

	},

	update: function handler(req, res) {
	// console.log("Request for " + pathname + " received.");

    res.writeHead(200, {"Content-Type": "text/plain"});
    res.write("Welcome");
    res.end(" to update article");

	},

	//createArticle

	//updateArticle

	//deleteArticle

	//viewArticle


}

};

```
 ------

##Helpful Links:

* The Node Beginner's Book - http://www.acfo.org/www/uploads/documents/33e2d962a6da1d1124e7c23a9fb23972.pdf

* Vanilla JS Node Routing Demo - http://www.learnallthenodes.com/episodes/3-beginning-routing-in-nodejs

* Restful API Design With Node JS Restify (more helpful next week when we introduce frameworks) - http://code.tutsplus.com/tutorials/restful-api-design-with-nodejs-restify--cms-22637


