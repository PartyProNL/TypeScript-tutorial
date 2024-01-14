# Example use-cases for OOP
Now that we've learned what OOP is and what it can do, we need to start using it. Doing so effectively can be hard, but here are some ways to do so:

- Create a class for each table in your database. Also think about connected data; every question on your forum also has a user, so make sure to also add a user variable (not just the user ID, a full user) to your question table class.
- Creating a class for a reusable system. Everytime you have code that you use multiple times, you should always have that in a function. Sometimes, you can also put this functionality inside of a class. An example of this could be a `Session` class. In its constructor, it could check if the user is logged in or not, and send the user to a login page if necessary. You could also add a function to load all user data from the database, based on which user is logged in.
- Creating a class to hold complicated data. Creating classes for tables from your database is an example of this, but you might have other data types that might not be in your database.

I would recommend just starting off with the first one for now. After you get more used to using OOP, you might get some ideas to use OOP effectively yourself.