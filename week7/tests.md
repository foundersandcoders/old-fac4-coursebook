# TESTING

We are using [shot](https://www.npmjs.com/package/shot) to inject requests to the handler. This means we do not have to start the server or make real HTTP requests through the network stack. Instead, we inject mock requests directly to the handler and receive mock responses that we can then test. This saves us A LOT of time (real HTTP requests are slow).
### Tools
* We are writing acceptance tests using Mocha and Shot.
* We are using node's core Assert module for assertions.
* We are writing HTTP servers using node.

### Commands

* Install dependencies with ``` npm install ```
* Start the server with ``` make s ``` or ```node server.js```
* Run the tests with ``` make t ``` or ``` npm test ```


## USER STORIES
 * As a user I would like to see an excerpt of the 'n' most recent blog posts when I first open the page
 * As a user I would like to see a side pane list of past blog posts titles
 * As a user I would like to be able to view an entire blog post in a separate page when I select 'read more'
 * As a user I would like to be able to select one of the older posts from the list and have an excerpt displayed on the main page
 * As a user I would like to add a new post 
 * As a user I would like to edit a post
 * As a user I would like a separate editing/new post page.
 * As a user I would like to delete a post

## TESTING HTML AND JSON
 * We need to test that a client request(GET, POST, DELETE) is met with a successful response, however it is trickier to extract the data we want to check from html than JSON.  
 * Therefore, it may be easier to test that the content of a server rendered page contains what we expect it to by looking at the data in it's json form.
 
## TESTS USING SHOT
```js 
var shot = require("shot");
var server = require("../handler");
var assert = require("assert");
var request;

describe("Main page (reading view)", function () {
    request = {
            method: "GET",
            url: "
    };
    it("should respond with an OK status code", function (done) {
        shot.inject(server, request, function (res) {
            assert.equal(res.statusCode, 200);
            done();
        });
    });
    it("should show a list of blog entry titles", function (done) {
        shot.inject(server, request, function (res) {
            // Placeholder test - looking for evidence of 'blog post' html
            assert.equal(res.payload.match(/blog/), true);
            done();
        });
    });
    it("should show excerpts of the most recent blog posts", function (done) {
        shot.inject(server, request, function (res) {
            // Placeholder test - looking for evidence of 'blog post' html
            assert.equal(res.payload.match(/blog/), true);
            done();
        });
    });
});

describe('Edit Page', function(){
     it("should respond with an OK status code", function (done) {
        request = {
            method: "GET",
            url: "/edit"
        };
        shot.inject(server, request, function (res) {
            assert.equal(res.statusCode, 200);
            done();
        });
    }); 
    it("should show a text editor for writing your blog post", function (done) {
        request = {
            method: "GET",
            url: "/edit"
        };
        shot.inject(server, request, function (res) {
            // Placeholder test looking for 'input' field
            assert.equal(res.payload.match(/input/), true);
            done();
        });
    }); 
    it("should select a post from list in edit page for editing", function (done) {
        request = {
            method: "GET",
            url: "/edit/<blog_post_id_number>"
        };
        shot.inject(server, request, function (res) {
            assert.equal(res.payload, "");
            done();
        });
    });
    it("should add new blog post", function (done) {
        request = {
            method: "POST",
            url: "/edit"
        };
        shot.inject(server, request, function (res) {
            assert.equal(res.payload, "");
            done();
        });
    });
    it("should delete selected blog post", function (done) {
        request = {
            method: "DELETE",
            url: "/edit/<blog_post_id_number>"
        };
        shot.inject(server, request, function (res) {
            assert.equal(res.payload, "");
            done();
        });
    });
    it("should update selected blog post", function (done) {
        request = {
            method: "PUT",
            url: "/edit/<blog_post_id_number>"
        };
        shot.inject(server, request, function (res) {
            assert.equal(res.payload, "");
            done();
        });
    });
});

describe('Individual Post Page', function(){
    it("should retreive a and display single blog post", function (done) {
        request = {
            method: "GET",
            url: "/blog/<blog_post_id_number>"
        };
        shot.inject(server, request, function (res) {
            assert.equal(res.payload, "");
            done();
        });
    });
});
```
