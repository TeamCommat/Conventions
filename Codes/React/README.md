# React.js Coding Conventions

## Basic Rules

1. Always use .jsx file, instead of .js when programming React.js components.
2. Do not use `React.createElement` unless you're initializing the app from a file that is not JSX.
3. Only include on React component per file. However, multiple stateless components are allowed per file.

## Naming conventions

1. Component names should be in Pascal Case. For example:

   ```
   Header.jsx Footer.jsx MainNavigation.jsx PostList.jsx
   ```
2. Non-component names should be in Camel Case. For example:

   ```
   myUtilityFile.js cookieParser.js onFetch.js
   ```
3. Unit testing codes' names should be the same with the target file name. For example:

   ```
   Header.test.js MainNavigation.test.js PostList.test.js
   ```
4. Constants should have their names in capital letters and underscores(_). For example:

   ```javascript
   const EXAMPLE_VARIABLE = 0;
   ```
5. Event Handlers should have name on Camel Case. Also, they should have names in on__ form. For example:

   ```javascript
   const onPressButton = () => {
     ...
   }
   ```
6. Custom hooks should have names on Camel Case. Also, they should have names in use___ form. For example:

   ```
   const useCustomHook = () => {
     ...
   }
   ```
7. Functions that return values after calculating from given parameters should have names in get___From form. For example:

   ```javascript
   const getProductFrom = (a: number, b: number) => {
     return a * b
   }
   ```
8. For interfaces, use Pascal case for naming. For example:

   ```javascript
   interface MyPerson {
     name: string;
     age: number;
   }
   ```

## Syntaxes

1. Although it is not mandatory to use semicolons(;) in EC6, always write semicolons at the end of each lines of code.
2. When exporting components, use const declarations and arrow functions with `export default`. Inheritance and use of render() function is a old React.js syntax.

   ```javascript
   // BAD
   class Component extends React.Component {
     render() {
       return ();
     }
   }

   // GOOD
   const Component = () => {
     return ()
   }

   export default Component
   ```
3. When using curly brackets to reference a component, give a space at each end of the component name. For example:

   ```javascript
   import { NavigationBar } from './NavigationBar
   ```
4. When using curly brackets to reference a variable, do not give a space at each end of the variable name. For example:

   ```javascript
   const Name = () => {
     const name = "John Doe";

     return <h1>{name}</h1>;
   }

   export const Name;
   ```
5. When calling React hooks, do not refer to `React` again. For example:

   ```javascript
   // BAD
   React.useEffect(() => {
       // ...
     }, []);

   // GOOD
   import React, { useEffect } from 'react';

   useEffect(() => {
     // ...
   }, []);
   ```
6. When using `if, else if, else, for` etc. , do not omit brackets. It is needed for easy editing for the future.

   ```javascript
   if ( ) {
     ...
   } else if ( ) {
     ...
   } else {
     ...
   }
   ```
7. Align components and props as follows.

   ```javascript
   // BAD
   <App parameter1="foo"
        parameter2="bar" />

   // GOOD
   <App 
     parameter1="foo"
     parameter2="bar" 
   />

   // IF PROPS FIT IN ONE LINE, KEEP IT
   <App param="foo" />

   // Indent in child components
   <App>
     <Child />
   </>
   ```
8. Include single space in single closing tag.

   ```html
   // BAD
   <App/>

   // BAD
   <App
    />

   // GOOD
   <App />
   ```
9. Use self-closing tags when there are no children.

   ```html
   // BAD
   <Foo className="stuff"></Foo>

   // GOOD
   <Foo className="stuff" />
   ```
10. If a component has multiple lines of props,close the tag on a new line.

    ```
    // BAD
    <Foo
      bar="bar"
      baz="baz" />

    // GOOD
    <Foo
      bar="bar"
      baz="baz"
    />
    ```

## Architecture & Bug Avoidence

1. Do not use inline styling CSS.
2. Do not assign `undefined` values to a variable. To tell that the variable does not exist, use falsy values for each data types. Falsy values for each data types are given below. If `0` or `false` is an value that has logical meaning in the code, it is fine to use `null` in a integer or a string data type as a next-priority option. Also, empty array itself is a truthy value.

| Data Types | Falsy Values |
| :--------- | ------------ |
| Integer    | 0            |
| Boolean    | false        |
| String     | ''           |
| Object     | null         |
| Array      | [].length    |

3. Make utility files to prevent repeating same codes.
4. Strictly divide component that manages states and component that shows the UI.
5. To import multiple components from same directory, create `index.js` file at every directory. It prevents repetition of `import` statements. For example:

   ```javascript
   // index.js
   import { Nav } from './Nav';
   import { Banner } from './Banner';

   export { Nav, Banner };
   ```
6. Do not leave codes that were commented out during development process. Delete them out and clean up codes before commiting on git.
7. If a function is too long, or does multiple actions at the same time, divide them into smaller units.
8. If possible, do not create a function inside a component.
9. Do not use functions that are not from the parent component. Avoid dependency reversal in class hierachy.
10. Double check to delete `console.log()` functions that were added during development process for testing before deployment.
11. Do not modify `props` directly.
12. In a function, do not use data located outside the function. Instead, receive the variable as a prop.
13. Do not use `var` to declare a variable. Use `let` and `const` instead.
14. If possible, try to use arrow functions.
15. Use spread operator.
16. If a function requires more than 2 lines, separate the function from the JSX element.
17. Aviod using indexes as key props in `map` function.
18. When using `styled` variable, declare them in the same file with the component.
19. Use double quotes for JSX elements, but single quotes for all other JS.

    ```html
    // BAD
    <App bar='bar' />

    // GOOD
    <App bar="bar" />

    // BAD
    <App style={{ left: "20px" }}

    // GOOD
    <App style={{ left:'20px' }}

    ```
20. Use Camel Case for prop names.

    ```html
    // BAD
    <App
      UserName="hello"
      phone_number={12345678}
    />

    // GOOD
    <App
      userName="hello"
      phoneNumber={12345678}
    />
    ```
21. Do not use `isMounted`, since it is an anti-patter for ES6.

## Testing

1. Always Write Tests.
2. Test one feature in one testing code.
3. Do not make any logics inside a test.
4. Do not connect with actual network or database while testing. Use mock API or mock databast instead.
