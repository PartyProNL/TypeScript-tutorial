# Functions
Functions are reusable pieces of code. They help you avoid writing the same code multiple times and help clean up your code.

## Creating a function
In TypeScript you create a function like this:
```ts
function sayHello(): void {
    console.log("Hello");
}
```

- `function` is a keyword that tells the computer that we are about to create a function. It is like the `const` and `let` of a variable.
- `sayText` is the name of the function
- `void` is the what the function gives back. This function does not give any data back, so it returns `void`.

We then have a code block of the code that will be executed when the function is called.

## Executing a function
Calling a function is simple:
```ts
sayHello(); // This will log Hello
```

Just like a variable, you only say it's name, but this time you add `()` after the name to run it.

## Return types
Functions can give you back data. An example of this looks like this:
```ts
function getMyName(): string { // We put string here instead of void to say that it gives back a piece of text. You can use the same types here as with variables
    return "Youri";
}

const myName: string = getMyName(); // myName becomes Youri
```

A function that has a return type that is not `void`, must always return a value. If it does not, it will give an error. You return a value by simply typing `return myValue;`. `myValue` can be anything, from literal text, to a variable.

Any code after a return statement is not executed. The function simply stops when a return statement is executed.
```ts
function getMyName(): string {
    return "Youri";
    console.log("Hello"); // This will not run because it comes after the return statement
}
```

When your return type is `void`, you can also use a return statement like this:
```ts
function sayMyName(): void {
    console.log(getMyName()); // Logs Youri
    return; // We don't have to give a value because the function returns void
    console.log("Hello"); // This will not run
}
```

## Parameters
You can use parameters to give values to functions, like this:
```ts
function sayText(text: string): void {
    console.log(text);
}

sayText("Hello"); // Logs Hello
```

Between the `()` we can put our parameters. You can add multiple parameters by separating them with a comma like this:
```ts
function addNumbers(a: number, b: number): number {
    return a + b;
}
const myNumber: number = addNumbers(4, 2); // Value will be 6. Don't ever make a function for a default operation like + though, this is just an example 
```

First we have the name of each parameter (`a` or `b`), and then just like variables the type after it. You can then use these variables inside of the function-scope.