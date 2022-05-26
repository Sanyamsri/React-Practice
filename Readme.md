# React Notes

### React Introduction

- JSX id not supported by browser. React Craete Element API creates an element for us.JSX is an html like syntax to create

- To use JSX in brwoser we need a compiler like Babel Stand alone which will compile our JSX code in the brows

- The babel finds a code in the script compiles it and inserts a new script that has the compiled code. So the browser can evaluate

- {} is used for javascript expressions. Whatever in it that resolves to a va\

- React Fragmant impotance :
  If we need to put two elemets side by side
  In react.createelement, We cannot pass two variables side by side in the first argument, that's why JSX always needs to return a single component.
  so instead what we can do is we can craete react fragment. The React fragment allows us to put elements side by side without having to have some sort of container element like a div. (<></>)

```jsx
<>
  <span>hellow</span>
  <span>world</span>
</>
```

- We can make reusable components in JSX.We can declarea component and then reuse it in another component by just inserting it like in html. The first letter should be capital and teh component would be a function or class with return value as JSX

```jsx
const Message = (props) => <div>{props.msg}</div>;
const element = (
  <>
    <Message msg="Hello world" />
    <Message msg="Nya world" />
  </>
);
```

- PropTypes is used to check if the custom component has been used correctly or not and validate the types of props that are passed into the component.

```jsx
const Message = ({ firstName, lastName }) => (
  <div>
    {firstName} {lastName}
  </div>
);
Message.propTypes = {
  firstname: PropTypes.string,
  lastName: PropTypes.string.isrequired,
};
const element = (
  <>
    <Message firstName="Sanyam" />
  </>
);
```

- PropTypes adds a fair amount of code that needs to be run whenever React is rendering your components which may impact performance.

- while using {} the expression inside it is compiled to, in the react.createElement as a string as the third argument, we get this string.

- We have react.createElement div, null for the props, and then the string and so on. If we wanted to, instead of passing this string, do some sort of if statement, that wouldn't work at all. It doesn't make any sense to pass a statement as an argument to a function

- Working with ternary expressions in reactJs

```jsx
const Message = ({ text }) => {
  // console.log(text.length);
  //js
  return (
    //jsx
    <div>
      {/*js*/}
      {`This text ${text} contains `}
      <strong> {text.length > 0 ? text.length : "NO"} </strong>
      characters
    </div>
  );
};
```

- Whenever any element in DOM is changed in simple Javascript the whole DOM updates even its child elements who were not affected by the change , whenever state changes, you don't have to re-render your entire element whereas

- When you create React elements, you trigger a re-render of a component, React is going to compare the elements that you returned this time with the elements that you returned last time nd then it will update the DOM surgically to only update the things that were different between the last time and this time you returned JSX.

- for inline styles we need to use style attribute and pass an object like this

```jsx
const Box = ({ size, color }) => {
  return (
    <div className={`box box--${size}`} style={{ backgroundColor: `${color}` }}>
      {size} {color} box
    </div>
  );
};
```
