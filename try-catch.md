## Try / Catch

https://www.qualified.io/assess/5e8cb4770b3d890013d6f00b/challenges/5e909d498abcc00014f565a3?invite=dBuaNoFx7FEpGg

The following challenges wil help you get more comfortable with throwing exceptions and handling them using `try` and `catch`.
#
### Use try and catch to handle errors
Write a function called `getCarColor` that takes in a car object like in the example below. It should return car's color. Use `try` and `catch` so that if accessing the color raises an error, the function returns `"Color unknown"`.

- The function must use the try/catch syntax
- For a valid car, it should return the car's color
- If accessing the color fails, the function should catch the error and return "Color unknown"

```
let car = { make: "Honda", model: "Civic", color: "Slate Grey"}

`getCarColor(car) // "Slate Grey"

`getCarColor(undefined) // "Color unknown"
```

````
function getCarColor(car) {
  try {
    return car.color;
  } catch (e) {
    throw new Error("Color unknown");
    console.log(e);
  }
}
````


Throwing an error
Write a function checkBankAccount that takes in a number. If the number is less than or equal to 0, use throw to raise an error. You should throw the string "Out of money".

If the number is greater than 0, the function shouldn't do anything.

Example:

checkBankAccount(100) //=> undefined
checkBankAccount(-50) // Thrown: 'Out of money'
Custom Error Messages
You can give your errors more context by passing them a message. It will look like: throw new Error("An error! Oh no!")

Write a function called customErrorMessage that takes a string and throws an error with that string as its message.

Example:

customErrorMessage("An error! Oh no!") // Error: An error! Oh no!
customErrorMessage("Argument must be a car object with a color property") // Error: Argument must be a car object with a color property
Error types
There are different categories of errors. For example, if you encounter an error because of an incorrect data type, you can use a TypeError. Instead of throwing a new Error, it will look like: throw new TypeError("Wrong data type!")

Write a function addOneHundred that takes in one argument. If the argument is a number, return the number plus 100.

If the argument is not a number, use throw to raise a TypeError with the message "Argument must be a number".

Example:

addOneHundred(15) //=> 115
addOneHundred("A Mighty Wind") // TypeError: Argument must be a number
Reminder: you can check if something is a number using typeof.

Catching and throwing again
Write a function called getAuthorName that takes in an author object. It should return the author's name, if accessing the author.name works. If it doesn't, catch the error, and throw a new TypeError("Author name failed").

The function must use the try/catch syntax
The function should attempt to return the author name as follows: return author.name
Example:

getAuthorName({name: "George Eliot"}) //=> "George Eliot"
getAuthorName(null) // TypeError: Author name failed
