# Using a class by creating an instance
Now that our class has variables, functions and a constructor, we can start using it. Imagine this scenario: we have a page where we can change your username. We keep track of which user is logged in by saving the user's `userId` in the `session`. Here is some (simplified) code for that page:

```ts
// This code is inside of a TypeScript file connected to an HTML page, not inside of a class. This code is ran when the page is loaded.

// First, we load the data of the user
const userId: number = session.get("userId");
const userData: any = await api.queryDatabase("SELECT * FROM user WHERE userId=?", userId);

// We get the username from the userData. Because userData is a list of rows from the database, we have to get the first row using [0] (see Arrays for more info)
const username: string = userData[0].username;

// Now we can create an instance of our user class
const user: User = new User(userId, username);

// We connect a function to a save button that will save the username
document.getElementById("save-username")!.addEventListener("click", () => {
    // Get the entered new username
    const newUsername: string = (document.getElementById("change-username") as HTMLInputElement).value;

    // Change the username inside of our user object
    user.username = newUsername;

    // Save the changed username to the database
    user.saveUsernameToDatabase();
});
```

A lot happens here, so let's break it down.

## Creating an instance of our User class
```ts
const user: User = new User(userId, username);
```

What we do here, is create a variable named `user`. We then set the type of this variable to the name of our user class, so `User`. (You would have to import this)

Then we assign the value of our variable: `new User(userId, username);`. What happens here, is that we call our constructor. Calling a constructor is done by first typing `new`. Then we add a space followed by the name of our class (`User`). Because the constructor is a function, we also add `()` with parameters in between. In this case, our loaded user ID and username.

## Changing the value of a variable inside the object
```ts
user.username = newUsername;
```

We can access a variable inside of an object, by accessing our object `user`. Then we go into that object by using `.`. Last, we type the name of the variable we want to access (`username`). We then give this variable a new value like we would with any variable.

This means that you can also read variables from an object, like this:
```ts
const oldUsername: string = user.username;
user.username = newUsername;
```

## Accessing a function from our object
```ts
user.saveUsernameToDatabase();
```

This is basically the same as accessing a variable. We first access our object `user`, then we enter it by using `.`. Then we call our function, like we would with any other.