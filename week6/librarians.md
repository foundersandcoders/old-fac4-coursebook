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
    <Hello/>, //the 1st argument 
    document.getElementById('mydiv')
    );
```







var person = {
        name1: "Dec",
        name2: "Dave"
}

var Hello = React.createClass({
render: function(){
    return (
        <h1>hello, {this.props.data.name1}</h1>
        );
   }
}); 
React.render(
    <Hello data={person}/>,
    document.getElementById('content')
    );

var Default = React.createClass({
getDefaultProps: function(){
    return {
            name: "anita"
    }
},
render: function(){
    return (
        <h1>My name is {this.props.data.name1}</h1>
        );
    
}
}); 
React.render(
    <Default data={person}/>,
    document.getElementById('content')
);
