# What are objects and classes?
At the core of Object Oriented Programming (`OOP`) are objects and classes. We have previously worked with variables. Whenever we created a variable, we had two core components: the `type` and the `value`. These are essentially objects and classes:

- The `type` is the `class`; it determines what the value can do/hold.
- The `value` is the `object`; it is an `instance` (this is a very important word) of the type.

Imagine this example:

```ts
const name: string = "Youri";
```

The type (class) of the variable is `string`: this means that it is a piece of text. It also means that this variable gets certain functions from a string, like `contains()` or `substring()`.

The value (object) is set to a piece of text containing "Youri". Because we set the type to string, the value can only be a piece of text; it cannot be a number or a boolean for example. We determined what the value could be.

## What is an object?
So that means, that an object is the instance of a class. It is THE piece of text. Or it could be THE number of apples. Or it could be THE boolean that determines whether the user is logged in or not.

## What is a class?
A class defines what an object can do and what data it holds. A class can have functions, variables and a constructor (a function that is executed when you create an instance of a class).
