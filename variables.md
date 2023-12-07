# Variables
Basically all of programming exists out of variables and functions. They are the core of any program.

## What are variables?
Variables are a way to temporarily store data. It's the same as when doing a big calculation. You divide the calculation up into smaller calculations and write down or shortly remember the results. Variables are just like that; instead of making one extremely long line of code, you use variables to divide your code up into smaller bits that are also more readable.

## Creating a variable
You create a variable as follows in TypeScript:
```ts
let name: string = "Youri";
```

- `let` is the type of variable. There are two types in TypeScript: `let` and `const`. A `let` can have its value changed, a `const` (constant) cannot.
- `name` is the name of the variable. It is customary to use `camelCase`, meaning that the first word starts with a small letter and then each other word starts with a capital letter.
- `string` is the type of data the variable holds. All these types will be explained later.
- `"Youri"` is the value of the variable.

## Changing the value of a variable (let-only)
To change the value of a variable, do the following:
```ts
name = "Joerie";
```

Here we reference the name of the variable (`name`) and then give it a new value (`"Joeri"`). We don't mention the type of the variable or the type of the data. If we would do this, the computer would attempt to create a new variable with the same name, which will make it error.

## Referencing a variable
You will oftenly use variables. For example, when logging the name:
```ts
console.log(name); // This logs "Joerie" in the console
```

When referencing a variable, you just write its name (`name` in this case) without anything else. It will pass the value of the variable on.

## Types of variables
Variables can have a bunch of types. From `string` to `number` to `HTMLElement`. A few of these are default/core types (called "Primitives"). Every other type is a combination of these. For example, an `HTMLElement` has an `id`, which is just another `string`.

## Primitives
There are multiple primitives in TypeScript. These are the most important ones:

### String
A string is a piece of text. To use it, define the type of the variable as `string`. When setting the literal value of a variable to a string, you use double-quotes to specify that a piece of text is a piece of text to the computer. Like this:
```ts
const favoriteThemePark: string = "Phantasialand";
```

### Number
I don't need to explain what a number is. Here it is in TypeScript:
```ts
const amountOfRollerCoasters: number = 8;
```

A number does not need double-quotes or anything like that. A number can be a full number, or a number with decimals, like in this example:
```ts
const ticketCost: number = 49.99; // Don't fact check this one
```

### Boolean
A boolean can be either `true` or `false`. You use it like this:
```ts
const isOpen = false;
```

Once again, you do not add double-quotes or something like that. When referencing a boolean, you can also flip its value (so `true` becomes `false` and the other way). You do this by using a `!`, like this:

```ts
const isClosed = !isOpen; // True when isOpen is false
```

### Any
When you are not sure what the type of a variable is, you can use `any`. A variable that has the type `any`, can have any kind of value.
```ts
const amountOfVisitors: any = 3500000;
amountOfVisitors = "Many"; // We change the value to something else that has a different type. This would give an error if the type was number
```

You generally do not want to do this, because it is "unsafe". Because you are not sure what the type is, you don't know if you for instance can divide the `amountOfVisitors` by `365` to get the `amountOfVisitorsPerDay`. You cannot divide a string like that, and that would then give an error.

The case where I recommend using `any` is when getting something back from your database using `api.queryDatabase()`.

## Combining/editing variables
You've previously seen the value of a variable get changed to something else. Instead of completely changing and replacing the value, you can also edit it, like in the following examples:
```ts
// These examples are specific for numbers. You cannot subtract from a string or boolean.
let myNumber: number = 1;
myNumber = myNumber + 1; // myNumber becomes 2
myNumber += 1; // myNumber becomes 3
myNumber -= 1; // myNumber becomes 2 again
let myOtherNumber: number = myNumber * 3; // Has a value of 6 (2*3)
myOtherNumber /= 2; // myOtherNumber becomes 3.
```

For strings, the only operation you can do is add (`+`), like this:
```ts
const myName: string = "Youri";
const greeting: string = "Hello, " + myName; // End result is "Hello, Youri"
const alternativeGreeting: string = `Hello, ${myName}`; // When using backticks ` you can also insert values like this. This is useful when pasting in HTML or something like that. You can also use double-quotes in these pieces of text.
```

## Built-in variables
Previously I used `console.log()` in my example. In this case `console` very literally is a variable that has been provided to you. It's `built-in` to TypeScript and can always be used. There is one other built-in variable that is also very important, which is `document`.

You've also used `api`, which is a variable I imported from another file, but it is not built-in like the previous two.