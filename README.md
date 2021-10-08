# Javascript Handbook for Beginners
## Key JS Concepts

### Everything in *Javascript* happens inside an **Execution Context**.

**Execution Context** - It is like a big box and has two components in it. The first component is known as memory component. The memory component stores all the variables and functions as the key value pairs. It is also known as variable enviornment. The second component of this execution context is called code component. In this place all the code is executed one line at a time. The other name for it is thread of execution.

### *Javascript* is a synchronous single-threaded language.
It means that Javascript can only execute one command at a time, and that too in a specific order.

![Javascript Execution Context](https://miro.medium.com/max/700/1*CuL8xsqLb1GhpuHgmDKk0A.png)

Whenever a javascript code is executed a **Global Execution Context** is created. It has two parts and we know them by memory and code components. This execution context is created in two phases.

1. **Memory Creation Phase** - In this phase, javascript will allocate memory to all variables and functions. It allocates memory line by line until whole code isn't completed. While allocating memory, if it encounters variables it stores value *undefined* for them and whole function code(copy of function code) for functions.

2. **Code Execution Phase** - Now once again javascript runs through the whole javascript program line by line and execute the code. At this time all the calculations and function executions are done. In this phase, while encountering variables it replaces the undefined with actual value of variable from inside the javascript program. However, if it encounters the function calls (function invoking) altogether a new execution context is created. It treats a function like a mini program. This new execution context inside global execution context is also divided into two parts having memory and code components. Now once again, memory creation phase will happen and after that function code will be executed and whatever function is returning will be moved to from where function was invoked. The execution context for function(local execution context) will be deleted after function execution is completed.

###### This keeps repeating again and again until all functions are not executed. Once all code execution is completed the global execution context will also be deleted.
