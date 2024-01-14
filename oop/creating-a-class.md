# Creating a class
Now that we know what classes and objects are, we can go on to the next step: creating a class. (We can't create an object yet, because we need a class to determine what that object can do)

## Defining a class
Firstly, we have to think of a name. This depends on your use case, but it should try to describe the function of the class in a short way, or describe what it IS. Examples are `User`, `Question`, `Answer`, or `Filter`.

Then, we create a new TypeScript file for this class. The naming convention we use here is `kebab-case`. This means every word only has lowercase letters, and words are separated by a `-`. So if we have a class for a user, we would name the file `user.ts`.

Once we have created the file, we can define the class inside of the file, which looks like this:

```ts
export class User {

}
```

- We begin with `export`, because we want to later use this class in other files
- Then we type `class` to say that what is coming next is a class (similar to `function` or `let`)
- Then we enter the name of the class. This name uses `CamelCase`, which means that every word starts with a capital letter, and that there is no separator between words.
- After that we add a code block (`{}`) for the code that the class should hold. This is also called the `body` of the class.

## Adding a variable or function to the class
As mentioned previously, we can give a class variables and functions. These variables and functions are inside of the class, and are only there when an instance (object) is created. All instances have the same variables, but the values of these variables can be unique for each. All instances also have the same functions, but what they do won't change. Their implementation stays the same.

Let's add a variable to our class. This is very similar to how we would create a variable anywhere else, except for two small differences: we don't use the word `let` or `const`, and we also specify the accessibility. What accessibility is will be explained later, so for now we will just enter `public`:

```ts
export class User {
    public userId: number = 2;
    public username: string = "PartyProNL";
}
```

Adding a function to a class is also very similar to how we have done so previously, but once again we have the same two differences: we don't use the word `function` and instead specify the accessibility:

```ts
export class User {
    public userId: number = 2;
    public username: string = "PartyProNL";

    public saveUsernameToDatabase(): Promise<void> {
        await api.queryDatabase("UPDATE user SET username=? WHERE userId=?", this.username, this.userId);
    }
}
```

## What does `this` mean?
When we are in the body of a function, and we want to use a variable or function that is INSIDE of the class, we have to use the `this` keyword. `this` is a variable that is always available, that references to an instance of your class. When we go inside of that variable using `.`, we get access to its variables and functions.