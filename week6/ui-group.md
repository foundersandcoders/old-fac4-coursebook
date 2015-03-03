##UI GROUP

Our main focus for today was understanding the basic User Interface, composing various components and producing the component hierarchy.

Check out our screencast where we look at Apple Notes and describe where each component lives and what sub-component(s) they contain:

https://www.youtube.com/watch?v=iZxAMXLUjX0&feature=youtu.be


You should also check out these docs in order to get a better understanding of React and what we are talking about in our video (basically Step 1 of the docs):

http://facebook.github.io/react/docs/thinking-in-react.html


We also had a go at making a very basic Note-Taking App. It's not complete, but check out the code below:

```
<!DOCTYPE html>
<html>
<head>
    <title>Hello world</title>
    <script src="http://fb.me/react-0.12.1.js"></script>
    <script src="http://fb.me/JSXTransformer-0.12.1.js"></script>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.2/css/bootstrap.min.css">
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"></script>
	<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.2/js/bootstrap.min.js"></script>

<style type="text/css">
.NoteApp{
	margin: 30px auto;
}


.SearchField{
	width: 100%;
	padding-right: 0px;

}
.textarea{
	width: 100%;
	height: 300px;
}

.NoteList{
	margin-top: 10px;
	padding-left: 0px;
	list-style-type: none;
}
</style>
</head>
<body>

<script type="text/jsx">



var NoteApp = React.createClass({
	render: function(){
		return ( 
			<div className="NoteApp col-md-6 col-lg-6 col-sm-8 col-xs-10">
				<SearchableTable notes={this.props.notes}/>
				<TextEditor notes={this.props.notes}/>

			</div>
		)
	}
});

var TextEditor = React.createClass({
	render: function(){
		return(
			<div className="TextEditor col-md-8 col-lg-8 col-sm-8 col-xs-12">
			<textarea className="textarea"/>
			</div>
			)
	}
});

var SearchableTable = React.createClass({
	render: function(){
		return (
			<div className="SearchableTable col-md-4 col-lg-4 col-sm-4 col-xs-4">
				<SearchField/>
				<NoteList notes={this.props.notes}/>
			</div>
			)
	}
});

var SearchField = React.createClass({
	render: function(){
		return(
			<input type="text" className="SearchField" />
			)
	}
});


var NoteList = React.createClass({
	render: function(){
		var titles = [];
		this.props.notes.forEach(function(note){
			titles.push(<IndivNote note={note} />)
		});

		return (
			<ul className='NoteList' > {titles} </ul>
			)

	}
});

var IndivNote = React.createClass({
	render: function(){
		return ( 
			<li>
				<p> {this.props.note.title} </p>
			</li>
		)
	}
});


var NOTES = [
 	{author: 'Amil', title: 'Amils Text1', text: 'This is Amil here and this is my text'},
 	{author: 'Per', title: 'Pers Text1', text: 'This is Per here and this is my text'},
 	{author: 'Ron', title: 'Rons Text1', text: 'This is Ron here and this is my text'},
 	{author: 'Amil', title: 'Amils Text2', text: 'This is Amil here and this is my text'},
 	{author: 'Per', title: 'Pers Text2', text: 'This is Per here and this is my text'},
 	{author: 'Ron', title: 'Rons Text2', text: 'This is Ron here and this is my text'}
];

React.render(<NoteApp notes={NOTES}/>, document.body);



</script>


</body>

</html>
```

You might want to copy and paste this code into your own text editor, save it and drag and drop the file into your browser, just so you can get a taste of what it looks like!
