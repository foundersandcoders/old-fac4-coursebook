# Week 3: use Node.js to create a social media feed

## Time: one week

We will be building a Node.js application to access various social media APIs to collect posts for displaying on each of your blogs.

The initial task will be to create a gallery of tweeted images with the hashtag #FoundersandCoders on your blog, using the Twitter API and an application that responds to AJAX requests by serving JSON.

If you successfully complete this task, there are a number of possible extension tasks that you can attempt:
- Create a real-time feed that automatically updates your page when new data is posted to Twitter;
- Store older tweets locally, so that when they are too old to be retrieved directly from the API, they can be retrieved locally;
- Use the Instagram API and display images from two different sources in the same page;

There are several questions that you will have to answer to successfully complete this week's task:

- What is Node.js and how does it work;
- What Node.js modules might there be to help us with this task;
- How can we access the Twitter API;
- How can we ensure that our API credentials are not shared publicly on GitHub;
- How can we extract image URLs from the Twitter feed;
- How can we repurpose the Twitter data to create our own data feed;
- How can we extract that data to display on the page;
- How can we make a nice-looking gallery page;
- How far back do tweets served by the Twitter API go;
- How can we store and extract data locally;
- How can we extract data from the Instagram API;
- How can we nicely combine data from two different sources;
- Where can we serve our application from?

The complexity of this task is greater than the client-side developer challenge we did in Week 2, but none of the pieces are necesarily harder than anything you have already tackled. The trick will be to understand how all the pieces fit together and to break the task down into manageable chunks.

Project planning is going to be essential and you may want to understand how to solve this problem on paper before you start writing any code.

## Homework

```js
// Write a small program which runs in node.
// This program will allow you to run the following command:

>$ node program.js hello

// and get the following result:

>$ node program.js HELLO
> H
> E
> L
> L
> O

// For this challenge you will need to install node and npm.
// HINT: http://nodejs.org/api/process.html
```

Some references: https://www.codeschool.com/courses/real-time-web-with-node-js

Here you can find a lot of material: https://github.com/FilWisher/node-books