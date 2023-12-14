# Important functions and variables to know
TypeScript has a huge amount of built-in variables and functions. I'll describe some of the most useful ones here with examples, but there are many I will forget and ones that I might not deem important that you might need. You can always Google something like this by searching for something like `js how to add class to element` on Google. (I recommend searching for JavaScript (`js`) because every function and variable is the same, and you will get more results)

With all of these examples, take notice on whether something is a function (look for `()`) or a variable.

## Examples for DOM-manipulation
One of the most important things to do with TypeScript is editing your HTML, and getting things from your HTML.

```ts
// Get an element from its ID, and edit the text inside
// The element might not exist, by adding a ! we tell the code that we are sure that it is there (see null-safety for more info)
document.getElementById("title")!.textContent = "Welcome, " + username;

// Add HTML to an element by getting it from its class
document.querySelector(".my-list-class")!.innerHTML += "<p>Hello</p>";

// Add code to execute when clicking on a button
// There are other events you can use, like focus for selecting an input
document.getElementById("my-button")!.addEventListener("click", () => {
    alert("You pressed the button");
});

// Get the username input and read the entered value
const inputElement: HTMLInputElement = document.getElementById("username")! as HTMLInputElement;
const enteredUsername: string = inputElement.value;

// Add a class to an element
document.getElementById("delete-button")!.classList.add("hidden");

// Removing a class from an element
document.getElementById("delete-button")!.classList.remove("hidden");
```

## Examples for the HBO-ICT Cloud API
For our current project, we can use the HBO-ICT Cloud API. These are functions that simplify other more complicated functions. You can find all of the documentation here: https://docs.hbo-ict.cloud/

```ts
// Run SQL on the database, and add a value to the query.
const result: any = await api.queryDatabase("SELECT * FROM user WHERE userId=?", userId);

// Save the userId to the session, so it can be loaded on another page
session.set("userId", userId);

// Read the userId from the session
const userId: numnber | undefined = session.get("userId");

// Remove the userId from the session, meaning it can no longer be read
session.remove("userId");

// Send the user to another page
url.redirect("/login.html");
```

There are also functions for uploading and deleting files (useful for profile pictures), functions for reading info from a URL (like youtube.com/watch?video=ABCDEFG) and loading another HTML file and its content (for automatically adding a sidebar to your page).

## Other examples
Here are some other examples that might be useful.

```ts
// Log something in the console
console.log("Hello world");

// Log something in the console but display it as a warning (yellow with the exclamation mark)
console.warn("This is a warning");

// Log something but as an error (in red)
console.error("This is an error");

// Display a pop-up on the screen with a message. You generally do not want to use this and instead edit your page to show a message
alert("This is a popup message")

// Converting a piece of text to a WHOLE number
const myString: string = "2";
const myNumber: number = parseInt(myString);

// Converting a piece of text to a number with decimals
const mySecondString: string = "1.54";
const myNumberWithDecimals: number = parseFloat(mySecondString);
```