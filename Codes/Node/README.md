# Javascript (Node.js) Coding Conventions

## Basic rule for source files

* Name source files only with lower case alphabets, hyphens (`-`), underscores (`_`).
* File extensions should be `.js`
* Encode source files in `UTF-8` format.
* Do not indent with tabs.

## Formattings

### Curly brackets (`{}`)

* Even if the control statements (`i.e if, else, for, do, while, ...`) contain one line of code, they should always have curly brackets.
* Follow **Kernighan and Ritchie Style** for formatting curly brackets.

  * Do not change line before opening bracket.
  * Change line after opening bracket.
  * Change line before closing bracket.
  * Change line after closing bracket. But if `else, catch, while, period (.), semi colons, or closing parenthesis` follows, do not change line.
  * ```javascript
    class InnerClass {
      constructor() {}

      /** @param {number} foo */
      method(foo) {
        if (condition(foo)) {
          try {
            something();
          } catch (err) {
            recover();
          }
        }
      }
    }
    ```
* For a empty block, close curly bracket right after opening.

  ```
  // BAD
  function doNothing() {
  } 

  // GOOD
  function doNothing() {}

  ```
* If a empty block occurs in a `if-else if-else` statements or `try-catch-finally` statements, change line.

  ```javascript
  // BAD
  if (condition) {
    ...
  } else if (otherCondition) {} else {
    ...
  }

  try { 
    ...
  } catch (e) {}

  // GOOD
  if (condition) {
    ...
  } else if (otherCondition) {
  } else {
    ...
  }

  try { 
    ...
  } catch (e) {
  }
  ```

### Indentations

* Indent with **two spaces** (spacebars) when new code block occurs.
* Indentation rules in objects is same with normal code blocks.
* For `switch` statements, indentation rules are same as normal code blocks. However, **do not** add empty line between `break` and the next `case`.

  ```javascript
  switch (animal) {
    case Animal.Dog:
      handleDog();
      break;
    case Animal.Cat:
      handleCat();
      break;
    default:
      throw new Error('Unknown animal');
  }
  ```
* When using dots `.` to write long method chains, give indents to every methods. Dot operators should always be in **front** of method names.

  ```javascript
  // BAD
  $('#items').find('.selected').highlight().end().find('.open').updateCount();

  // BAD
  $('#items').
    find('.selected').
      highlight().
      end().
    find('.open').
      updateCount();

  // GOD
  $('#items')
    .find('.selected')
      .highlight()
      .end()
    .find('.open')
      .updateCount();
  ```

### Statements

* Write one statement per line.
* Add semi-colons after every statements.
  ```javascript
  // BAD
  let name = 'Cada'

  doSomething() saySomething()

  // GOOD
  let name = 'Cada';

  doSomething();
  saySomething();
  ```

### Whitespaces

* Do not let each line pass 80 letters.
* Blanks can be divided into two types: `Vertical Whitespaces` and `Horizontal Whitespaces`.
* #### Vertical Whitespaces

  * Vertical whitespace can be written in these circumstances:

    * Between each statements
    * Between methods that were written in succession inside a class, or a object literal.
    * Optional in classes, before first method or after last method inside the class.
  * Do not use two or more vertical whitespaces at the same time.
  * Below is the example of the use of vertical whitespaces.

    ```java
    // BAD
    if (foo) {
      return bar;
    }
    return baz;

    // GOOD
    if (foo) {
      return bar;
    }

    return baz;

    // BAD
    const obj = {
      foo() {
      },
      bar() {
      },
    };
    return obj;

    // GOOD
    const obj = {
      foo() {
      },

      bar() {
      },
    };

    return obj;

    // BAD
    const arr = [
      function foo() {
      },
      function bar() {
      },
    ];
    return arr;

    // GOOD
    const arr = [
      function foo() {
      },

      function bar() {
      },
    ];

    return arr;
    ```
* #### Horizontal Whitespaces

  * There are three types of horizontal whitespaces: `leading (front of a line), trailing (end of a line), internal (inside of a line)`.
  * Leading whitespaces can be used anytime based on indentation rules.
  * Do not use trailing whitespaces.
  * Horizontal Whitespaces can be used in these circumstances:

    * Between keywords like `if, for, catch` and parenthesis `()`.

      ```javascript
      // BAD
      if(condition) {
          ...
      }

      // GOOD
      if (condition) {
          ...
      }
      ```
    * Between keywords like `else, catch` and closing curly brackets (`}`).

      ```javascript
      // BAD
      if (condition) {
          ...
      }else { }

      // GOOD
      if (condition) {
          ...
      } else { }
      ```
    * Before opening curly brackets.
    * Each sides of binary operator and ternary operator.

      ```javascript
      // BAD
      const number = condition?20:30;

      // GOOD
      const number = condition ? 20 : 30;
      ```
    * After commas (`,`), semi colons (`;`).

      ```javascript
      // BAD
      const arr = [1,2,3,4];

      // GOOD
      const arr = [1, 2, 3, 4]; 
      ```
    * After colons (`:`) in object literals.

      ```javascript
      // BAD
      const person = {
          "name":"John Doe",
          "age":"20",
      }

      // GOOD
      const person = {
          "name": "John Doe",
          "age": "20",
      }
      ```
    * On each sides of `//`, after `/*`, before `*/`.
  * Do not use horizontal whitespaces between parenthesis `()` and square brackets `[]`.

    ```javascript
    // BAD
    function bar( foo ) {
      return foo;
    }

    // GOOD
    function bar(foo) {
      return foo;
    }

    // BAD
    if ( foo ) {
      console.log(foo);
    }

    // GOOD
    if (foo) {
      console.log(foo);
    }

    // BAD
    const foo = [ 1, 2, 3 ];
    console.log(foo[ 0 ]);

    // GOOD
    const foo = [1, 2, 3];
    console.log(foo[0]);
    ```
  * Use horizontal whitespaces between curly brackets `{}`.

### Variables

* Declare one variable per line.

  ```javascript
  // BAD
  let a = 1, b = 3;

  // GOOD
  let a = 1;
  let b = 2;
  ```
* Local variables should be declared at nearest point where the variable is actually used. Keep in mind to minimize variable's scope of use.

  ```javascript
  // GOOD
  function() {
    test();
    console.log('Testing..');

    const name = getName();

    if (name === 'test') {
      return false;
    }

    return name;
  }

  // BAD - Wrong place to call getName() function.
  function(hasName) {
    const name = getName();

    if (!hasName) {
      return false;
    }

    this.setFirstName(name);

    return true;
  }

  // GOOD
  function(hasName) {
    if (!hasName) {
      return false;
    }

    const name = getName();
    this.setFirstName(name);

    return true;
  }
  ```
* Do not use `var` keyword. Use `let` when the values change, use `const` when declaring non-changing variables.
* Groupize variable declaration statements. Declare constant variables first, then declare using `let`.

  ```javascript
  // BAD
  let i;
  const items = getItems();
  let dragonball;
  const goSportsTeam = true;
  let len;

  // GOOD
  const goSportsTeam = true;
  const items = getItems();
  let dragonball;
  let i;
  let length;
  ```
* Do not use `this` as a value of a variable. If necessary, use arrow functions or bindings.

  ```javascript
  // BAD
  function foo() {
    const self = this;
    return function () {
      console.log(self);
    };
  }

  // GOOD
  function bar() {
    return () => {
      console.log(this);
    };
  }
  ```

### Arrays

* When declaring arrays, do not use Array constructor `new Array()`. Instead, use literal syntax.

  ```javascript
  // BAD
  const arr = new Array();

  // GOOD
  const arr = [];
  ```
* When appending items to an array, use `Array.push()` function.

  ```javascript
  const arr = [];
  // BAD
  arr[arr.length] = "hello";

  // GOOD
  arr.push("hello");
  ```
* When copying an array, use spread operator `(...)`.

  ```javascript
  // BAD
  const len = arr.length;
  const newArr = [];
  let i;

  for (i = 0; i < len; i++) {
      newArr[i] = arr[i];
  }

  // GOOD
  const newArr = [...arr]
  ```
* When declaring variable and some of its elements, add commas (`,`) including last element.

  ```javascript
  const arr = [
      'first',
      'second',
      'last',
  ]
  ```
* Do not use index that is not a number. If it is nessasary to use something other than number for index, use `map` or an `object`.

  ```javascript
  // BAD
  const arr = [];
  arr["str"] = 32;

  // GOOD
  const obj = {};
  arr.str = 32;

  const map = new Map();
  map.set("str", 32);
  ```

### Objects

* When declaring an object, use literal syntax rather than `new Object()` constructor.

  ```javascript
  // BAD
  const obj = new Object();

  // GOOD
  const item = {};
  ```
* Do not use reserved keywords for keys inside an object. Instead, use a synonym or a slightly different word.

  ```javascript
  // BAD
  const superman = {
    default: { clark: 'kent' },
    private: true,
  };

  // GOOD
  const superman = {
    defaults: { clark: 'kent' },
    hidden: true,
  };
  ```
* When declaring an object, use double quotation mark (`""`) for a key.

  ```javascript
  // BAD
  var my_object = {
    key: "value",
  }

  // GOOD
  var my_object = {
    "key": "value",
  }
  ```
* Use method shortening syntax.

  ```javascript
  // BAD
  const atom = {
    value: 1,

    addValue: function (value) {
      return atom.value + value;
    },
  };

  // GOOD
  const atom = {
    value: 1,

    addValue(value) {
      return atom.value + value;
    },
  };
  ```

### Functions

* Use function declaration rather than function expression syntax. It will effect hoisting of the function.

  ```javascript
  // BAD
  const foo = function () {
  };

  // GOOD
  function foo() {
  }
  ```
* Do not declare function from other blocks, such as `if, while`.
* Do not use arguments for function's parameter. Instead, use `rest` syntax (`...`).

  ```javascript
  // BAD
  function concatenateAll() {
    const args = Array.prototype.slice.call(arguments);
    return args.join('');
  }

  // GOOD
  function concatenateAll(...args) {
    return args.join('');
  }
  ```
* Do not modify a function's parameter. Instead, use default parameter.

  ```javascript
  // WORST
  function handleThings(opts) {
    opts = opts || {};
    ...
  }

  // BAD
  function handleThings(opts) {
    if (opts === void 0) {
      opts = {};
    }
    ...
  }

  // GOOD
  function handleThings(opts = {}) {
    ...
  }
  ```
* Place default value parameters at the very last.

  ```javascript
  // BAD
  function handleThings(opts = {}, name) {
    ...
  }

  // GOOD
  function handleThings(name, opts = {}) {
    ...
  }
  ```
* If a function expression syntax is needed without an alternative, use an arrow function.

  ```javascript
  // BAD
  [1, 2, 3].map(function (x) {
    const y = x + 1;
    return x * y;
  });

  // GOOD
  [1, 2, 3].map((x) => {
    const y = x + 1;
    return x * y;
  });
  ```
* Always include `return` statement even if `return` statement is unnecessary. Omiting `return` statement will decrease productivity while modifying codes.

  ```javascript
  // BAD
  [1, 2, 3].map(number => `A string containing the ${number}.`);

  // GOOD
  [1, 2, 3].map(number => {
    return `A string containing the ${number}.`;
  });
  ```

### Strings

* When declaring a string, use single quotation mark (`'`). When a single quotation mark is needed inside a string, use template literal.

  ```javascript
  // BAD
  const name = "Capt. Janeway";

  // GOOD
  const name = 'Capt. Janeway';

  // GOOD
  const name = `Mark J' Maclachlan`;
  ```
* When a string is too long to write in a single line, use template literals or string concatenation. Do not use backslashes.

  ```javascript
  // BAD
  const errorMessage = 'This is a super long error that was thrown because of Batman. When you stop to think about how Batman had anything to do with this, you would get nowhere fast.';

  // BAD
  const errorMessage = 'This is a super long error that was thrown because \
  of Batman. When you stop to think about how Batman had anything to do \
  with this, you would get nowhere \
  fast.';

  // GOOD
  const errorMessage = 'This is a super long error that was thrown because ' +
    'of Batman. When you stop to think about how Batman had anything to do ' +
    'with this, you would get nowhere fast.';

  const errorMessage = `This is a super long error that was thrown because
    of Batman. When you stop to think about how Batman had anything to do
    with this, you would get nowhere fast.`;
  ```
* When creating a string dynamically, do not use string concatenation. Instead, use template literal.

  ```javascript
  // BAD
  function sayHi(name) {
    return 'How are you, ' + name + '?';
  }

  // BAD
  function sayHi(name) {
    return ['How are you, ', name, '?'].join();
  }

  // GOOD
  function sayHi(name) {
    return `How are you, ${name}?`;
  }
  ```
* Do not use `eval()` function. It has lots of alternatives, and it may cause XSS (Cross Site Scripting) attack.

### Numbers

* Numbers can be expressed in decimal, hexadecimal (`0x`), octal (`0o`), binary (`0b`).
* Do not add unnecessary `0`s right after x, o, and b.

### Control statements

* Use `for-of` statements rather than normal `for` loops. But, if possible, use high-level functions like `map(), reduce(), forEach()`.

  ```javascript
  const numbers = [1, 2, 3, 4, 5];

  // BAD
  let sum = 0;
  for (let num of numbers) {
    sum += num;
  }

  sum === 15;

  // GOOD
  let sum = 0;
  numbers.forEach((num) => sum += num);
  sum === 15;

  // GOOD
  const sum = numbers.reduce((total, num) => total + num, 0);
  sum === 15;
  ```
* In `switch-case` statements, `default` statement should always be at last of the block.
* In conditional statements, use `===`, `!==` rather than `==` and `!=`.
* Keep in mind of the following values and boolean relationships in `ToBoolean` method.

  * Objects are considered as `true` value.
  * `undefined` values are considered as `false` value.
  * `null` is considered as `false` value.
  * Numbers except +0, -0, or `NaN` are considered as  `true` value.
  * +0, -0 and `NaN` are considered as `false` value.
  * Strings are considered as `true` value.
  * Empty strings (`''`) are considered as false value.

## Naming Rules

### Basic rules of naming

* Do not name something as a single letter. Let others know the purpose of it with its name.

  ```javascript
  // BAD
  function s() {
    ...
  }

  // GOOD
  function sum() {
    ...
  }
  ```
* Do not use underscores (`_`) in front or at the end of the name.

  ```javascript
  // BAD
  this.__firstName__ = 'Panda';
  this.firstName_ = 'Panda';
  this._firstName = 'Panda';

  // GOOD
  this.firstName = 'Panda';
  ```
* For readability, write acronyms in all upper case, or all lower case.

  ```javascript
  // BAD
  import SmsContainer from './containers/SmsContainer';

  const HttpRequest = [
    ...
  ];

  // GOOD
  import SMSContainer from './containers/SMSContainer';

  const HTTPRequest = [   
    ...
  ];

  // ALSO GOOD
  const httpRequests = [
    ...
  ];

  // BEST
  import TextMessageContainer from './containers/TextMessageContainer';

  // BEST
  const request = [
    ...
  ];
  ```
* All constants should be in capital case, and in combination with underscores.
* Do not use plural form in variable name.

  ```javascript
  // BAD
  let delivery_notes = ["one", "two"];

  // GOOD
  let delivery_note_list = ["one", "two"];
  ```
* Do not use abbriviations in variable name. Write in proper form.

  ```javascript
  // BAD
  let del_note = 1;

  // GOOD
  let delivery_note = 1;
  ```

### Files and packages

* Write all file names in lower case, including assets that are not source files. Ignore proper grammar.

  ```
  D// BAD
  London.png
  HELLOWORLD.pdf
  APP.js

  // GOOD
  london.png
  helloworld.pdf
  app.js
  ```
* Package names should be in lower Camel Case.
* Match file name with default export's name.

### Variables

* Write variable names in lower Camel Case, except consant variables that are exported.
* Variable names should start with alphabets.

### Functions

* Function names should be written in lower Camel Case.

  ```javascript
  // BAD
  function MyFunction() {...}

  // GOOD
  function myFunction() {...}
  ```
* Name functions in verb form.

  ```javascript
  // BAD
  function whereIsCamera() { ... }

  // GOOD
  function findCamera() { ... }
  function getFoo() { ... } // getter
  function setBar() { ... } // setter
  function hasCoo() { ... } // booleans
  ```
* Function's parameters should be in lower camel case.

  ```javascript
  // BAD
  function someFunction(SOMEVALUE, SOMEARRAY) { ... }

  // GOOD
  function someFunction(someValue, someArray) { ... }
  ```

### Objects

* Object names should be in lower Camel Case.
* When exporting an object, name them in Pascal Case.

### Classes

* Name classes and their constructors in Pascal Case.
* Class names should be in noun form.
* When exporting an class, name them in Pascal Case.
