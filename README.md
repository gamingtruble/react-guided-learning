# react-guided-learning

## guide link:
* https://react.dev/learn

## Quick start
* You will learn
* [x] [How to create and nest components](* how-to-create-and-nest-components)
* [x] [How to add markup and styles](* how-to-add-markup-and-styles)
* [x] [How to display data](* how-to-display-data)
* [ ] How to render conditions and lists
* [ ] How to respond to events and update the screen
* [ ] How to share data between components

* How to create and nest components
  * react components are
    * React apps building blocks
    * a piece of the UI that has its own logic and appearance
    * JavaScript functions that return markup
    * able to be as small as a button, or as large as an entire page
  * components:
    * [x] make: function MyButton()
    * [x] make: function MyApp() and nest MyButton into it

* How to add markup and styles
  * [x] writing markup
    * the markup syntax for MyButton and MyApp is called JSX
      * JSX is stricter than HTML
        * you have to close tags like `<br />`
        * your component also can’t return multiple JSX tags
        * you have to wrap them into a shared parent, like a `<div>...</div>` or an empty `<>...</>` wrapper
      * if you have a lot of HTML to port to JSX, you can use an online converter

  * [x] adding styles
    * to specify css class in react, you use `className`
      * it works the same way as HTML `class` attribute
        * `<img className="avatar"/>`
    * inside css file
      * `.avatar { border-radius: 50%; }`
    * React does not prescribe how to add CSS files
      * in the simplest case, add a `<link>` tag to the HTML
    * when using a build tool or a framework
      * consult its documentation to learn how to add a CSS file to it

* How to display data
  * JSX let you put markup into JS
  * curly braces let you "escape back" into JS
    * this way you can embed some variable from your code and display it to the user
      * this will display `user.name`:
        * `return(<h1>{user.name}</h1>);`
    * the curly braces also allow you to assign values to attributes
      * in this case the `src` attribute reads the JS `user.imageUrl` variable value
        * `return (<img className="avatar" src={user.imageUrl}/>);`
          * now the `user.imageUrl` value will be passed as the `src` attribute value

* How to render conditions and lists
* How to respond to events and update the screen
* How to share data between components

