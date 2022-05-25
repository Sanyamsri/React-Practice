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
