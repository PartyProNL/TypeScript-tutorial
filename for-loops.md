# For loops
We previously created arrays. We learned how to edit them, read them, but there is one more key thing we can do with them: run code for each element. 

Imagine the following: you have a database with multiple forum posts. You want to render the 10 most recent posts on your home page. You get all the forum posts using SQL (like `SELECT * FROM posts LIMIT 10 ORDER BY dateCreated DESC`), which returns an array with up to 10 elements. Next, you want to add some HTML for each post. That would look something like this:

```ts
const myQuestionArray: any[] = ...; // Get your data here using api.queryDatabase();

const elementToAddHTMLTo: HTMLElement = document.getElementById("recent-posts-list")!;

for(let element of myQuestionArray) {
    elementToAddHTMLTo.innerHTML += `<p>${element.title}</p>`;
}
```

Let's break this down. We define a for-loop by typing `for(let element of myQuestionArray)`. After this comes a code block. This code block is ran for each element in the given array.

We say `let element` (element can be any name, like `let post`) to create a variable that can be used inside of the code block. Then we say `of myQuestionArray`, which refers to from what array we want to read the elements. (`myQuesitonArray` in this case)

The code block is than ran for every element in the array. Every time, the value of the `element` variable changes to the next element:

```ts
const myArray: number[] = [1, 3, 5, 6];

for(let element of myArray) {
    console.log(element);
}
```

This piece of code logs 4 separate times (because the array has 4 elements). Each time, the next element is logged. You'll get the following output:

```
1
3
5
6
```