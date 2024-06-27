# Breakout 11

### members

Kibet

walter

brian

# Difference BTWN var, let and const

## VAR

creates function-scoped variables

var can be hoisted

can be used outside block scope but not outside function scope

```jsx
console.log(x)

var x = 10
```

## LET

creates block scoped variables

cannot be hoisted

cannot be used outside block scope

## CONT

creates variables that cannot be reassigned another value

cannot be hoisted

cannot be used outside block scope

# What is Good?

`let` and `const` have **block scope**.

`let` and `const` can not be **redeclared**.

`let` and `const` must be **declared** before use.

`let` and `const` does **not bind** to `this`.

`let` and `const` are **not hoisted**.

# What is Not Good?

`var` does not have to be declared.

`var` is hoisted.

`var` binds to this.

# Difference Code

```jsx
start()

const user_name = "John Doe"

function start() {
  for (let i = 0; i < 10; i++) {
    console.log(i)
  }

  for (var j = 0; j < 10; j++) {
    console.log(j)
  }

  console.log(j)
}
```

# Questions

1. What is scope in JavaScript, and why is it important?

  scope is the accessibility and visibility of variables within code.

### Importance

1. Helps in avoiding naming conflicts
2. helps in code organization

2. Can you explain the difference between global scope and local scope?

in global scope variables can be accessed from anywhere in the code.

while in local scope variables can only be accessible within that function (or block).

3. How does JavaScript handle scope in functions compared to block-level scope?

JavaScript handles scope in functions by creating a new local scope. This means that any variable declared inside a function is only accessible within that function and any nested functions. However, it is not accessible outside of that function. This is different from block-level scope (which is used by `let` and `const`), where a new scope is created inside every block (e.g., every set of `{}` braces), including if-else blocks, for and while loops, etc.

4. How do var, let, and const differ in terms of scope?

1. `var` is function-scoped, meaning it is accessible within the function it was declared in. `let` and `const` are block-scoped, meaning they are only accessible within the block they were declared in.
2.  `var` variables are hoisted and initialized with `undefined`, while `let` and `const` are hoisted but not initialized.  `let` or `const` variable will throw an error if accessed before declaration. 
3.  `const` variables cannot be reassigned after they are declared.

5. What are the implications of declaring a variable without any keyword (i.e., no var, let, or const)?

When a variable is declared without any keyword, it is automatically declared in the global scope, regardless of where it is declared. This can lead to unintentional side effects, as it can overwrite a global variable with the same name. It also makes the variable accessible throughout the entire file.

1. What is the scope chain, and how does JavaScript use it to resolve variable access?
    
    The **scope chain** is a list of objects representing the current execution context's scope and its outer scopes. JavaScript resolves variable access by looking up the scope chain from the innermost scope to the outermost (global) scope.
    
2. What are some differences between lexical scope and dynamic scope? Which one does JavaScript use?
    
    Lexical scope, also known as static scope, is determined at compile time. Variables are known to be in the scope where they are defined. On the other hand, dynamic scope is determined during the execution of the program. Variables are in scope if they are defined in the current function or any of its callers, regardless of whether the calling function is physically nested within the defining function's scope.
    
    JavaScript uses lexical scoping. This means that a variable's scope is determined by its physical location within the written source code, and nested functions have access to variables declared in their outer scope.
    
3.  What is a closure, and how does it relate to scope in JavaScript?
    
    A closure is a function that has access to its own scope, the outer function’s scope, and the global scope, as well as access to the function parameters and variables. A closure gives you access to the function’s scope from an inner function.