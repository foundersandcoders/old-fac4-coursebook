Q) What is a Server?  

A) A server accepts incoming responses from the client and in turn sends a request to a data source. The data source sends a response back to the server which then responds with the data requested from the client.

Q) How do you read JSON content?

A) We use a readFile function with the parameters being :

first one is the path to the file you are reading.

second is the character set you are reading.

third is a function with two parameters, the first is for an error message and the second is the actual content you are reading from the specified file.
```
var obj;

fs.readFile('./filename.json', 'utf8', function (err, data) {

    if (err) throw err;

    obj = JSON.parse(data);
});
```
Q) How do we send the data received from the client to the browser?

A)` Response.write(JSON.stringify(obj.user.username)); `

We use stringify to convert the objects in our file to strings to send to the browser. In this example we have referenced our file as obj and then specified what data we want in that object.
