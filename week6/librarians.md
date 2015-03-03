# Hello World

```html
<html>
    <head>
        <script src="http://fb.me/react-0.12.2.js"></script>
        <script src="http://fb.me/JSXTransformer-0.12.2.js"></script>
    </head>
    <body>
        <div id="mydiv"></div>
        <script src="app.js" type="text/jsx"></script>
    </body>
</html>
```


```javascript
var Hello = React.createClass({ //here we are creating the virtual DOM component, the standard naming convention is to name the 1st letter of the component in capitals.
render: function(){ //using React's render method, we are creating the contents which will LATER be rendered, here we are just creating it.
    return (
        <h1>hello world</h1>
        );
   }
}); 
React.render( //here we are calling the render method using dot notation, it is here that the contents i.e hello world appear in the browser
    <Hello/>, //the 1st argument is the component we are calling, this is variable Hello which will appear in the virtual (React) DOM as a XML element tag.
    document.getElementById('mydiv') //the second argument places the content of the render method into our div.
    );
```

# Hello Me
using props(properties):

```javascript
var Me = React.createClass({
   getDefaultProps: function(){ //getDefaultProps is another method in the React library
      return {
             name: "Sam"
      }
   },
  render: function(){ 
    return (
        <h1>Hello, my name is {this.props.name}</h1> //this refers to what component you are currently in i.e. Me, and props refers to the method property, getDefaultProps in this case
        );
   }
}); 
React.render(
    <Me/>, 
    document.getElementById('mydiv')
);

```

# Hello You

Now let's use props to get data from an object outside of our function:

```javascript
var dataset = {
        name1: "Dec",
        name2: "Dave",
        name3: "Anita",
        name4: "Jason"
} 

var Hello = React.createClass({
    render: function(){
        return (
            <h1>hello, {this.props.data.name1}</h1> //data here is just a placeholder for our dataset object, we could call it anything. name1 is the property of dataset.
            );
       }
}); 
React.render(
    <Hello data={dataset}/>, //here data becomes the attribute in the virtual DOM, to which dataset is assigned.
    //Download the chrome extension and have a look at the React DOM in your browser to see this!
    document.getElementById('mydiv')
);
```