# Accessibility (public and private)
Accessibility is a pretty simple concept. Using accessibility modifiers, we can determine where a class's variables and functions can be accessed. This concept is also called `Encapsulation`.

## The `public` modifier
Whenever a variable or function has the `public` modifier, it can be accessed anywhere; inside of the class, but also outside of the class.

## The `private` modifier
When you instead use the `private` modifier, you limit access. Now a variable or function can only be accessed inside of a class, and not outside of it. That means that inside of a class you can still do this:

```ts
export class Fruit {
    // When making a variable private, we start the name of the variable with an underscore (_)
    private _name: string;

    public constructor(name: string) {
        this._name = name;
    }

    public logName(): void {
        // We can access the variable because we are inside of a class
        console.log(this._name);
    }
}
```

but outside of our class, we cannot access it:

```ts
// Imagine this is in a separate file
const myFruit: Fruit = new Fruit("Apple");

// This will give an error, because the name is private and we are not inside the class
console.log(myFruit._name);

// This will not give an error, because the function is public
myFruit.logName();
```

## Example use case of `private`
By setting variables to private, we can protect them. We can make it so that you cannot change a variable, or make it so that we always run certain code when changing the variable from outside a class.

Previously, we had an example where we updated the username of a user in the database. It might be useful to always update the username in the database, when you want to change the username variable. That would look like this:

```ts
export class User {
    public userId: number;

    // The username is private (and therefore the variable name starts with an underscore)
    private _username: string;

    public constructor(userId: number, username: string) {
        this.userId = userId;

        // Notice how we also use an underscore here
        this._username = username
    }

    // Because our username is private, we cannot read it from outside this class. We might want to do this somewhere, so we create a public function that returns the username (this is what we call a getter)
    public getUsername(): string {
        return this._username;
    }

    // Now we create a public function to set the username, that also saves the username to the database (this is called a setter)
    public setUsername(username: string): Promise<void> {
        // Change the value of the variable
        this._username = username;

        // Update in the database
        await api.queryDatabase("UPDATE user SET username=? WHERE userId=?", this._username, this.userId);
    }
}
```