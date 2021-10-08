# Javascript Handbook for Beginners
## Key JS Concepts

### Everything in *Javascript* happens inside an **Execution Context**.

**Execution Context** - It is like a big box and has two components in it. The first component is known as memory component. The memory component stores all the variables and functions as the key value pairs. It is also known as variable enviornment. The second component of this execution context is called code component. In this place all the code is executed one line at a time. The other name for it is thread of execution.

### *Javascript* is a synchronous single-threaded language.
It means that Javascript can only execute one command at a time, and that too in a specific order.

![Javascript Execution Context](https://miro.medium.com/max/700/1*CuL8xsqLb1GhpuHgmDKk0A.png)

Whenever a javascript code is executed a **Global Execution Context** is created. It has two parts and we know them by memory and code components. This execution context is created in two phases.

1. **Memory Creation Phase** - In this phase, javascript will allocate memory to all variables and functions. It allocates memory line by line until whole code isn't completed. While allocating memory, if it encounters variables it stores value *undefined* for them and whole function code(copy of function code) for functions.
