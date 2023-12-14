# If and else
Sometimes you only want to do something based on a specific condition, like the if the user is not logged in, send them to the login page. The if/else block allows you to do this.

## Example
This is a small example for kicking the user when they are not logged in:

```ts
const isUserLoggedIn: boolean = true; // Add your own code here to check if the user is logged in

if(isUserLoggedIn) {
    console.log("User is logged in");
} else {
    url.redirect("/login.html");
}
```

What you see here is an if/else block. When the specified condition is met (`if(condition`)), the code in the `if` block will be ran. If the condition is not met, the code in the `else` block is executed.

Imagine that we only want to do something when the user is NOT logged in, instead of logging something in the console when the user is logged in. We can change the code like this:

```ts
const isUserLoggedIn: boolean = true; // Add your own code here to check if the user is logged in

if(!isUserLoggedIn) {
    url.redirect("/login.html");
}
```

Previously we learnt that we can flip the value of a boolean by using `!` (false becomes true and true becomes false). That is what we are using above.

## Comparison operators
Imagine you want to check if the password of the user is longer than 8 characters when they register an account, so that we can ensure it is safe. We can create an `if` block like this:

```ts
const password: string = ...; // This would be a variable with the entered password

if(password.length < 8) { // If the password is shorter than 8 characters
    alert("Your password is too short! It must be at least 8 characters");
    return; // Return to stop the code
}
```

These are all of the most important operators:

| Operator | Description                       | Example       |
| -------- | --------------------------------- | ------------- |
| \===     | Checks if two values are the same | `if(2 === 2)` (true) |
| !==      | Checks if two values are NOT the same | `if(2 !== 2)` (false) |
| >        | Greater than | `if(3 > 2)` (true) |
| <        | Less than | `if(3 < 2)` (false) |
| >=       | Greater than or equals | `if(2 >= 2)` (true) |
| <=       | Less than or equals | `if(2 <= 2)` (true) |

## AND & OR operators
Sometimes you want to combine two checks. You could do that like this:

```ts
if(userIsLoggedIn) {
    if(username === "admin") {
        // Do something
    }
}
```

You can somewhat simplify this by using `&&`, the AND operator:

```ts
if(userIsLoggedIn && username === "admin") {
    // Only ran when BOTH conditions are met
}
```

You also have the OR operator, `||`:

```ts
if(password.length < 8 || password.length > 20) {
    // This code is executed if the password is shorter than 8 characters OR longer than 20 characters
    alert("Your password must be 8-20 characters long");
}
```