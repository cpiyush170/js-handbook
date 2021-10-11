# Javascript Handbook for Beginners
## Key JS Concepts

### Everything in *Javascript* happens inside an **Execution Context**.

**Execution Context** - It is like a big box and has two components in it. The first component is known as memory component. The memory component stores all the variables and functions as the key value pairs. It is also known as variable enviornment. The second component of this execution context is called code component. In this place all the code is executed one line at a time. The other name for it is thread of execution.

### *Javascript* is a synchronous single-threaded language.
It means that Javascript can only execute one command at a time, and that too in a specific order.

![Javascript Execution Context](https://miro.medium.com/max/700/1*CuL8xsqLb1GhpuHgmDKk0A.png)

Whenever a javascript code runs a **Global Execution Context** is created. It has two parts and we know them by memory and code components. This execution context is created in two phases.

1. **Memory Creation Phase** - In this phase, javascript(I mean js engine - V8) will allocate memory to all variables and functions. It allocates memory line by line until whole code isn't completed. While allocating memory, if it encounters variables it stores value *undefined* for them and whole function code(copy of function code) for functions.

2. **Code Execution Phase** - Now once again javascript runs through the whole javascript program line by line and execute the code. At this time all the calculations and function executions are done. In this phase, while encountering variables it replaces the undefined with actual value of variable from inside the javascript program. However, if it encounters the function calls (function invoking) altogether a new execution context is created. It treats a function like a mini program. This new execution context inside global execution context is also divided into two parts having memory and code components. Now once again, memory creation phase will happen and after that function code will be executed and whatever function is returning will be moved to from where function was invoked. The execution context for function(local execution context) will be deleted after function execution is completed.

###### This keeps repeating again and again until all functions are not executed. Once all code execution is completed the global execution context will also be deleted.

### Call Stack maintains the order of execution of *execution contexts*.

Javascript manages the execution context through call stack. Whenever any javascript program is run the whole global execution context is pushed inside the stack. As soon as a function is invoked it is pushed inside the stack. After execution of function it gets popped out and control is handed back to from where function was invoked inside global execution context. This cycle repeats until whole global execution code is not completed. In the end, after executing whole code global execution context is also deleted and stack gets empty.

### *Window* and *this* in Javascript
JavaScript Engine creates a global object whenever you run any JS code. In the case of browsers, this global object is known as *window*. The javascript *this* refer to the object it belongs to.

### undefined vs not defined in *Javascript*
*Undefined* is a special keyword stored in variables like a placeholder during memory allocation (creation) phase of execution context. On the other hand, *not defined* in javascript mean that variable is defined in memory (or variable was not declared) - so we can't access it. That's why it gives error (eg. x is not defined).

### Scope Chain & Lexical Environment in *Javascript*

**Lexical Environment** -  Lexical as a term means in hierarchy (or in a squence). Whenever an execution context is created, a lexical environment is also created. It consist of local memory along with the lexical environment of its parent.

**Scope Chain** - When a variable is used in JavaScript, the JavaScript engine will try to find the variable’s value in the current scope. If it could not find the variable, it will look into the outer scope and will continue to do so until it finds the variable or reaches global scope.

If it’s still could not find the variable, it will either implicitly declare the variable in the global scope (if not in strict mode) or return an error. This whole process of finding variables in lexical environment of its parent is known as *scope chain*. The whole chain of lexical environments is called *scope chain*.

### Block Scope & Shadowing in JS
To group multiple statements we use curly brackets { } - known as block. All variables and functions that we can access inside a block is called block scope. *let* and *const* are stored in separate memory space(known as Block) and that's why they are block scoped. *var* shadow (modify) the value inside it it declared again (other than in funtion scope) and it is called shadowing.
