# The project: build a note-taking app 

Build a note-taking application in React. Any user should be able to take notes and those notes should appear in a list on the page. 

Here are a number of issues you might face:
* Persisting notes locally between browser sessions;
* storing notes on a remote server so that they can be shared between users;
* Editing notes.

There are a number of ways that this project could be extended, including adding access control, assigning notes to specific users and allowing commenting on notes. We probably won't have time to explore these areas in detail this week, but we may want to start thinking about them for future weeks.

###Concepts group

What vocabulary do you need to understand and what questions do you need to ask in order to understand React?    

Some vocabulary: *declarative programming, rendering, mutability, reusability, composition, components, templates, coupling, cohesion, separation of concerns, scope, binding, data binding, virtual DOM, HTML attributes, string concatenation, XSS injection.* 

Some questions:    
*Why might components encourage a better separation of concerns than templates?    
Why might you want to re-render rather than mutate the DOM?     
How does React tackle the issue of XSS injection?     
Why might you describe React as "version control for the DOM"?     
What is meant by two-way data binding and why might it be problematic in the context of a web app?*     

###UI group    
Design and mock up the user interface in HTML and CSS. Break the UI into a component hierarchy and give the components sensible names. Create a JSON object of some fake data that can be used to test the application without having to read an actual API. Present the UI and the components.  

If you have time, mock up interfaces for extending the application, perhaps adding user management (logging in and so forth) to allow users to comment on each others' notes. 

Reference: [Thinking in React (Step 1)](http://facebook.github.io/react/docs/thinking-in-react.html).  

###Library group 

What are the main methods and attributes needed to build React components and how would you use them?  

Some methods and attributes: 

    props 
    state 
    createClass() 
    render() 
    renderComponent() 
    setState()  

Go and read the React library documentation and become familiar with as many methods and idioms as you think will be useful.  

###Testing group 

Take a look at: [http://facebook.github.io/jest/docs/tutorial-react.html](http://facebook.github.io/react/docs/thinking-in-react.html) and then start working on tests for the components being designed by the UI group.  Be prepared to take the lead in taking a TDD approach when you return to your teams on Wednesday.  

Some questions:     
*Why might react components be particularly testable?    
Why might testing against the virtual DOM make your life easier?*    

###Tuesday 

**10:00** Morning challenge     
**10:30** Start work in role groups to deliver a set of recommendations.     
**12:00** Catchups with mentors   
**15:00** Catchups with mentors    
**17:00** Screencast presentation(s) from all role groups and pull request to gitbook.




