# Arrays (or lists)
You've probably come accross this scenario: you are selecting data from your database and get multiple rows back. This 'list' of database rows is what we call an `array` in code. It's a collection of multiple things, that you can edit in a lot of ways.

## Creating an array
Creating an array is quite simple. Here's what an array of `strings` looks like:

```ts
const fruits: string[] = ["Apple", "Banana"];
```

There are two key parts to this. Firstly, we add square brackets `[]` after the type. This changes the type from just one `string` to an array of strings (`string[]`). Secondly, the value we give it is also different. Instead of just a single string, we pass along multiple strings separated by commas and surrounded by square brackets (like `["1", "2"]`).

Any type can become an array. You can make an array of literally everything, like in these examples:

```ts
const someNumbers: number[] = [1, 2, 3]; // An array of numbers
const arrayWithAnyType: any[] = ["A string", 30, false]; // This array has the any type, which means that values can have any type
```

## Getting an element from an array
So now we have an array with multiple elements, but we want to get elements from it. Doing so is quite simple:

```ts
const fruits: string[] = ["Apple", "Banana"];
const firstFruit: string = fruits[0];
```

What we do here is create a new variable (`firstFruit`) that will represent the first element from the list. Because it is a singular string, we don't add the square brackets to the type. To get the first element, we simply type the name of the variable that holds the array (`fruits`) followed by square brackets (`[]`). Between these brackets we put what we call the `index`. (0 in this case)

Every element in an array has an index. It represents the position of the element in the array. This index starts at 0. So, if you have an array with 3 elements, the elements would have the following indexes: `0, 1, 2`.

## Adding an element to an array
Up until this point, we have created arrays with predefined elements. However, we might want to change the array at a later point. To do so, we use the `push()` function of the array, like this:

```ts
const fruits: string[] = ["Apple", "Banana"];
fruits.push("Pineapple"); // Adds a new element at the end of the fruits array
console.log(fruits[2]); // Logs Pineapple
```

## Removing an element to an array
We can also remove elements from an array, but this is a little bit more complicated. There are two ways to remove an element; the first is based on removing an element at a certain position:

```ts
const fruits: string[] = ["Apple", "Banana", "Pineapple"];
const indexToRemoveAt: number = 1; // Second element
fruits.splice(indexToRemoveAt, 1); // The function that removes the element
console.log(fruits); // Logs Apple and Pineapple
```

Sometimes you don't know the position of the element. You might only have the element itself. To remove an element from an array, do the following:

```ts
const fruits: string[] = ["Apple", "Banana", "Pineapple"];
const indexOfMyElement: number = fruits.indexOf("Banana"); // Find the index of our element
fruits.splice(indexOfMyElement, 1); // Remove element at index of our element
console.log(fruits); // Logs Apple and Pineapple
```

## Other useful array features
Arrays have some other useful features as well. Here are some of the most important ones:

```ts
const fruits: string[] = ["Apple", "Banana", "Pineapple"];

const amountOfFruits: number = fruits.length; // The length variable in an array represents the amount of elements in it. In this case, there are 3 elements

// The includes function checks if an element is in an array
const hasApple: boolean = fruits.includes("Apple"); // true
const hasOrange: boolean = fruits.includes("Orange"); // false

// Using the join function, you can combine all elements in a longer string
const allElementsText: string = fruits.join(", "); // Apple, Banana, Pineapple
const secondAllElementsText: string = fruits.join("&") // Apple&Banana&Pineapple
```

There is also a `sort()` function to sort elements in an array. This function is pretty complicated though, and usually you'll want to sort using SQL's `ORDER BY` function anyway. (Because this is more efficient)

## Trivia
Didn't know where to put this so I'm just going to call this 'trivia'. Fun fact: a `string` is actually just an array of characters (`char[]`) in most programming languages. This is the reason why you can use some array features like `contains()` and `length` on a string.