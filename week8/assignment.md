# Week 8: build a blog using hapi

This week we are going to re-build our blog using [hapi](http://hapijs.com/).

Your jumping off point is Nelson's [learn Hapi](https://github.com/nelsonic/learn-hapi) repo and the [hapi tutorials](http://hapijs.com/tutorials).

We recommend that your start with the following elements:

* a JSON API
* Submission of new blog entries
* Listing of all blog entries
* Viewing of existing entries
* User registration 

Your blog will have the following elements:

### Routing
Using the [hapi](https://github.com/hapijs/hapi) package itself (you may also want to follow [Rails](http://guides.rubyonrails.org/routing.html) routing conventions).

### Testing
Using [lab](https://github.com/hapijs/lab) (we actually covered a lot of this ground last week with *shot*).

### Validation and data storage
Using [joi](https://github.com/hapijs/joi). For storing and retrieving your data you can start by storing your data in a *json* file or you can jump straight into using MongoDB (with e.g. [mongojs](https://github.com/mafintosh/mongojs) or [mongoose](http://mongoosejs.com/)) or [LevelDB](https://github.com/rvagg/node-levelup), or some other database.

### User authentication 
Using [bell](https://github.com/hapijs/bell) or [hapi-auth-cookie](https://github.com/hapijs/hapi-auth-cookie).

## Roles

Split up into four different roles to explore routing, testing, validation and authentication. 

## Stretch goals

If you have time, you can add:

* HTML pages using [views](http://hapijs.com/tutorials/views) and any templating engine you like.
* Editing and deleting of existing entries

And you can explore the following packages:

* [boom](https://github.com/hapijs/boom) for error handling
* [good](https://github.com/hapijs/good) for logging
* [catbox](https://github.com/hapijs/catbox) for caching
* [reply.file](http://hapijs.com/tutorials/serving-files) or [inert](https://github.com/hapijs/inert) for static file handling


