# Code blocks (and scoping)
You've probably noticed them a lot in your files: `{` and `}`. Everything between these two is code, like in this example:

```ts
{
    let name: string = "Youri";
}
```

The code inside of a code block is executed from the top to the bottom. This means that the following example will not work:
```ts
{
    let firstName: string = "Youri";
    let fullName: string = `${firstName} ${lastName}`; // This will give an error, because lastName has not yet been created
    let lastName: string = "Scheepers";
}
```

but this will work:
```ts
{
    let firstName: string = "Youri";
    let lastName: string = "Scheepers";
    let fullName: string = `${firstName} ${lastName}`;
}
```

## Scopes
These code blocks provided something called `scoping`. I don't have a good analogy for this right now, so I'll explain them without an analogy.

A code-block has its own scope, which means that it is it's own place, protected from other code-blocks. This means that you cannot access something in another scope, unless it is a scope inside of its own scope. This looks like this:

```ts
{
    let firstName: string = "Youri";
}

{
    let lastName: string = "Scheepers";
    let fullName: string = `${firstName} ${lastName}`; // This piece of code will give you an error! This is because `firstName` is not inside of this scope.
}
```

```ts
{
    let firstName: string = "Youri";

    // This scope is inside of the other scope, so you can reference variables from its parent scopes
    {
        let lastName: string = "Scheepers";
        let fullName: string = `${firstName} ${lastName}`;
    }
}
```

```ts
{
    {
        let firstName: string = "Youri";
    }

    // This will not work, you can only get variables from parent scopes, not deeper scopes.
    let lastName: string = "Scheepers";
    let fullName: string = `${firstName} ${lastName}`;
}
```