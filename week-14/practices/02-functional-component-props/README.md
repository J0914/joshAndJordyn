# Practice: Functional Components and Passing Props

In this practice you will create a functional component and pass props from a
parent component to a child component.

## Set up

Download the [starter][props-starter] file for this practice.

Open the starter in VSCode and run `npm install` in the terminal.

Run `npm start` to make sure your project is set up correctly.

## Create a Functional Component

Create a functional component called `BaseStats` in your `src` folder. It should
have a `div` with a class of `base-stats` and an `h1` with the text "BaseStats".
Import the `BaseStates.css` file into your component.

Next, add the `BaseStats` component to your `App.js` component. It should be
placed below the `Showcase` component. Test it in the Browser.

Next, you are going to create an object inside your `App.js` called `baseStats`.
It should look like this:

```js
const baseStats = {
  hp: 45,
  attack: 49,
  defense: 49,
  spAttack: 65,
  spDef: 65,
  speed: 45,
};
```

Pass this object to the `BaseStats` component using `stats` as the prop name.
In your `BaseStats` component, bring in `props` as the argument to the
functional component.

Go to your browser, go to the Browser DevTools and open your React DevTools.
Click on the BaseStats component. Under `props` you should see your stats props
object.

## Use props object in the child component

Now you are ready to use your props object. 

Create a table beneath your `h1` tag. It should have four table rows, each with 
two table data tags. The first table data tag of each table row should contain
the header for each stat (Hit Points, Attack, Defense, and Speed). 

The second table data tag of each table row should contain the cooresponding 
variable you destructured from props. Your code should look something like:

```js
<table>
  <tbody>
    <tr>
      <td>Hit Points</td>
      <td>{props.stats.hp}</td>
    </tr>
    <tr>
      <td>Attack</td>
      <td>{props.stats.attack}</td>
    </tr>
    <tr>
      <td>Defense</td>
      <td>{props.stats.defense}</td>
    </tr>
    <tr>
      <td>Speed</td>
      <td>{props.stats.speed}</td>
    </tr>
  </tbody>
</table>
```

To make your code more concise and practice the DRY principal, destructure your
props variables in the argument for the `BaseState` functional component. 
Refactor your JSX to reflect these variables. You should only call the variables
hp, attack, defense, and speed in your JSX. 

** Remember, you can destructure a nested object.

### Pass a Function as a Prop

There are times where you may want to pass a function as a prop. By doing this,
you will be passing a reference to the function in the parent component which
may then have some functionality.

In your `App.js`, beneath your `baseStats` object, create a function called
`handleClick`

Place this code inside the function:

```js
alert(
  `Special Stats:\nSpecialAttack: ${baseStats.spAttack}\nSpecialDefense:${baseStats.spDef}`
);
```

Now, pass the `handleClick` function as a prop called `clicker` to the
`BaseStats` component.

In your `BaseStats` component, destructure the `clicker` prop in your function
component argument.

Next, above your table, create a button with the text `Check Special Stats`.
Give it a class of `sp-stats`. Pass an `onClick` event listener to the `button`
element and assign it the clicker function prop.

Remember, an event listener in React is camel cased (_`onClick` instead of `onclick`_) and it takes a function as it's assignment.

Notice that when the button is clicked, it triggers the `handleClick` function
in the parent component.

**Congratulations!**
In this practice you have learned:

1. Passing values as props from parent to child.
2. Checking props using React DevTools.
3. Adding prop values to the child component.
4. Destructuring props to remain DRY
5. Passing a function as a prop
6. One way of using the onClick EventHandler

[props-starter]: ./starter
