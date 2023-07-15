# react-guided-learning

## guide link:
* https://react.dev/learn

## Quick start
* You will learn
* [x] [How to create and nest components](#how-to-create-and-nest-components)
* [x] [How to add markup and styles](#how-to-add-markup-and-styles)
* [x] [How to display data](#how-to-display-data)
* [ ] [How to render conditions and lists](#how-to-render-conditions-and-lists)
* [x] [How to respond to events and update the screen](#how-to-respond-to-events-and-update-the-screen)
* [ ] [How to share data between components](#how-to-share-data-between-components)

### How to create and nest components
  * react components are
    * React apps building blocks
    * a piece of the UI that has its own logic and appearance
    * JavaScript functions that return markup
    * able to be as small as a button, or as large as an entire page
  * components:
    * [x] make: function MyButton()
    * [x] make: function MyApp() and nest MyButton into it

### How to add markup and styles
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

### How to display data
  * JSX let you put markup into JS
  * curly braces let you "escape back" into JS
    * this way you can embed some variable from your code and display it to the user
      * this will display `user.name`:
        * `return(<h1>{user.name}</h1>);`
    * the curly braces also allow you to assign values to attributes
      * in this case the `src` attribute reads the JS `user.imageUrl` variable value
        * `return (<img className="avatar" src={user.imageUrl}/>);`
          * now the `user.imageUrl` value will be passed as the `src` attribute value

### How to render conditions and lists
* [ ] conditions
  * in React there's no special syntax for writing conditions
    * you can use the same techniques as you would in JS with `if`, `else` etc. to conditionally include JSX
      * `let content;`
      * `if (isLoggedIn) {content = <AdminPanel />;}`
      * `else { content = <LoginForm />;}`
      * `return ( <div> {content} </div>);`
    * you can also use conditional `?` operator if you prefer more compact code
    * unlike if, it works inside JSX
      * `<div>`
      * `{isLoggedIn ? (`
      * `<AdminPanel />`
      * `) : (`
      * `<LoginForm />`
      * `)}`
      * `</div>`
    * when no `else` branch is needed, a shorter  logical `and` (`&&`) syntax can be used
      * `<div> {isLoggedIn && <AdminPanel />} </div>`
    * all of these approaches also work for conditionally specifying attributes
* [x] rendering lists
  * list rendering rely on JS features like `for loop` and the `array map()` function
    * about the `array map()` function:
    * it creates a new array populated with the results of operations done on every element in the array it's used on
      * my own words, original source on this [link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
  * example
    * here's an array of products
      * `const product[{title: 'Cabbage', id: 1}, {title: 'Garlic', id: 2}, {title: 'Apple', id: 3}];`
    * inside a jsx component, use the `map()` function to transform the array of products into an array of `<li>` tag items
      * `const listItems = products.map(`
      * `product => <li key={product.id}>`
      * `{product.title}`
      * `</li>`
      * `);`
      * `return (<ul>{listItems}</ul>);`
    * each item in a list should have a unique identifier
      * each of the li elements has a key attribute as their unique identifier
      * the identifier should usually be coming from the data that's being working on
        * things such as a database ID
      * through React keys can be used to see what happened if any changes is done to it later
        * examples for changes could be insertions, deletions or reordering of items

### How to respond to events and update the screen
* [x] responding to events
  * events can be responded to by declaring an event handler functions inside the jsx components
    * `function MyButton() {`
    * `function handleClick(){alert('You clicked me!');}`
    * `ruturn (<button onClick={handleClick}>Click me</button>);`
    * `}`
  * the `handleClick()` function does not get called at `onClick={handleClick}`
    * notice that the `()` parenthesis are not included at `onClick={handleClick}`
      * this way it's only passed down, and React will call the event handler when the button is clicked
* [x] Updating the screen
  * showing  and updating some information on the screen can be useful
    * an example could be showing how many times a button have been clicked
    * this can be done by adding a state to a component
      * to do this
        * import `useState` from react:
          * `ipmort {useState} from 'react';`
        * then declare a state variable inside a component
          * `function MyButton(){const[count, setCount] = useState(0);`
      * `useState` add two things
        * the current state `count`
        * the function that update it `setCount`
        * `count` start at "0" because "0" was passed to `useState` at `useState(0);`
      * full `MyButton` component example:
        * `function MyButton(){`
        * `const[count, setCount] = useState(0);`
        * `function handleClick(){setCount(count + 1);`
        * `)`
        * `return(`
        * `<button onClick={}>Clicked {count} times</button>`
        * `);`
        * `}`
      * React will call the component function again
        * this time `count` will be "1", then it will be "2" and so on
      * if you render the same component multiple times, each will get its own state

### How to share data between components
