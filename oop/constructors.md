# Adding and using a constructor
In the last part we ended up with this class:

```ts
export class User {
    public userId: number = 2;
    public username: string = "PartyProNL";

    public saveUsernameToDatabase(): Promise<void> {
        await api.queryDatabase("UPDATE user SET username=? WHERE userId=?", this.username, this.userId);
    }
}
```

The problem is, if we create a new user, they will all have the same `userId` and `username` values. We want this to be different for every user. The solution here is what we call a `constructor`; this is a function that is executed when you create an instance of your class.

## Defining a constructor
This is an example of a constructor for our `User` class:

```ts
export class User {
    // We still define the variables, but don't give them any values yet
    public userId: number;
    public username: string;

    // This is the constructor itself
    public constructor(userId: number, username: string) {
        this.userId = userId;
        this.username = username
    }

    public saveUsernameToDatabase(): Promise<void> {
        await api.queryDatabase("UPDATE user SET username=? WHERE userId=?", this.username, this.userId);
    }
}
```

- We begin with the accessibility modifier. This is a little stupid, because it should ALWAYS be `public`, so just write public. (There might be a VERY rare use-case for making it private, but I have never encountered that situation)
- The constructor function always has the name `constructor` (this tells TypeScript that it is in fact a constructor)
- Then we define the parameters we want our constructor to have (`userId` and `username` in this case)
- We DO NOT add a return type, because a constructor automatically returns the type of the class.
- Then we have the body of the constructor function

Let's take a closer look at the body of the constructor:

```ts
this.userId = userId;
this.username = username
```

What we do here might be a little complicated, but here is what happens:

- The constructor function has the two parameters named `userId` and `username`.
- We change the value of the variables inside of the `class`, by using the `this` keyword. The value we change to is the one from the parameters (notice that there is no `this` after the `=`)

That means that the constructor does the following: Whenever an instance of a user is created, we take the username and user ID we want to give it and update the variables inside of this instance, so that this user becomes unique.