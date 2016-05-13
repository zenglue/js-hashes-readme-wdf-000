# JavaScript "Hashes"

## Objectives
+ Explain what a hash in JavaScript is
+ Create an object in JS
+ Access a value from an object
+ Add a key-value pair to an object
+ Delete a key-value pair from an object
+ Iterate over key-value pairs in an object

## Intro

In JavaScript, all objects are effectively key-value pairs. We're not going to talk about objects in relation to Object Orientation, but objects as hashes. We will eventually get to objects and properties of objects, but right now we're just focused on how to create, manipulate and delete key-value pairs from a "hash".

JavaScript Objects behave sort of like a cross between Classes and Hashes in Ruby. For now, we're just going to focus on how to use them like a hash. From here on out, we'll be referring to a hash as an object. Every time you see the word "object" think "hash".



## Creating Objects

You can create an object in two different ways, with the literal syntax and with the new Object constructor.

Literal Syntax:
```js
var meals = {};
```

Object Constructor:
```js
var meals = new Object();
```

You can also create an object with key-value pairs:

```js
var meals = {breakfast: "oatmeal"};
```

Note that JavaScript does not have `=>` syntax. You mark a key with `:` and set the value directly after.

## Adding To An Object

Now that we have an empty object, it's time to start adding key-value pairs:

```js
var meals = {}
meals["breakfast"] = "oatmeal"
meals["lunch"] = "turkey sandwich"
meals["dinner"] = "steak and potatoes"
```

## Accessing A Value
Just like in Ruby, we access the value of an object from its key:

```js
var meals = {breakfast: "oatmeal", lunch: "turkey sandwich", dinner: "steak and potatoes"}
meals["breakfast"] //returns "oatmeals"
meals["lunch"] // returns "turkey sandwich"
meals["dinner"] // returns "steak and potatoes"
```

## Deleting A Key-Value Pair

Let's say it's only 5pm and we haven't actually eaten dinner yet, so we want to delete the dinner key-value pair:

```js
var meals = {breakfast: "oatmeal", lunch: "turkey sandwich", dinner: "steak and potatoes"};
delete meals["dinner"];
meals;
//returns {breakfast: "oatmeal", lunch: "turkey sandwich"}
```
## Changing A Value


Let's say we actually ate oatmeal and a banana for breakfast, and we want to update the value the `breakfast` key is storing:

```js
var meals = {breakfast: "oatmeal", lunch: "turkey sandwich", dinner: "steak and potatoes"};
meals["breakfast"] = "oatmeal and banana";
meals;
//returns {breakfast: "oatmeal and banana", lunch: "turkey sandwich", dinner: "steak and potatoes"}
```

## Check Empty Object

Unlike Ruby, JavaScript does not have a handy `.empty?` convenience method. But, you can check to see if your object is empty by using `Object.keys(yourObject)` which returns an array of all the keys in your object.

```js
var meals = {breakfast: "oatmeal", lunch: "turkey sandwich", dinner: "steak and potatoes"};
Object.keys(meals);
//returns ["breakfast", "lunch", "dinner"]
```

You can also count the number of key-value pairs by doing something like this:

```js
var meals = {breakfast: "oatmeal", lunch: "turkey sandwich", dinner: "steak and potatoes"};
Object.keys(meals).length;
//returns 3
```

## Iterating Over An Object

In order to iterate over an object, we need to use a new loop, the for in loop. We'll stick with the meals object for this example. The for in loop looks something like this:

```js
for (variable in object) {
  // code to be executed goes here
}
```
In this case, we want to iterate over every key value pair, so our variable is `key` and our object is `meals`. JavaScript will automagically take every key in the hash in turn and print out in the console, `"for breakfast I ate oatmeal"`, `"for lunch I ate turkey sandwich"`, `"for dinner I ate steak and potatoes"`.


```js
var meals = {breakfast: "oatmeal", lunch: "turkey sandwich", dinner: "steak and potatoes"};
for (var key in meals) {
  console.log("for " + key + " I ate " + meals[key]);
}
```


## Instructions
1. Open `objects.js`
2. Assign an object to the variable `playlist` — the keys will be artist names and the values will be song titles. (What limitation does this impose on our `playlist`?)
3. Create a function `updatePlaylist` which accepts three parameters: the playlist (an object), an artist name (a string), and a song title. The body of the function should add the song and artist as a key-value pair to the playlist object. (Or change the key's value if the key already exists.) The function should return the whole playlist.
4. Create a function `removeFromPlaylist` which accepts two arguments (the playlist object and the artist name). The body of the function should delete the key-value pair from the playlist and return the updated playlist.

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/js-hashes-readme' title='JavaScript Hashes'>JavaScript Hashes</a> on Learn.co and start learning to code for free.</p>
