# Practice JS Array Methods 

## Let's practice using `forEach`

#### `console.log` the strings
- Write a function `printNames` that uses `forEach` to log each name to the console.

  Argument: an array of strings like
  ```
  [
    "Mark Fisher",
    "Ira Bennett",
    "Denise Hicks",
    "Julius Patterson"
  ]
  ```
  Return value: none

  ### Solution 

  ````
  function printNames(names) {
    names.forEach(function (name) {
      console.log(name)
    })
  }
  ````

#### `console.log` object properties
- Write a function `logTreeTypethat` uses `forEach` to log the type of each tree object to the console.

  Arguments: an array of objects like
  ```
  [
    {
    type: "oak",
    height: "30m"
    },
    {
     type: "elm",
     height: "21m"
    }
  ]
  ```
  Return value: none

  Log the `type` property of each tree object to the console.

  ### Solution 
  ````
  function logTreeType(trees) {
    trees.forEach(function (tree) {
      console.log(`${tree.type}`)
    })
  }
  ````

#### sum the numbers
- Write a function `totalPoints` that uses `forEach `to add up an array of numbers.

  Arguments: an array of numbers, like
  ```
  [6,7,1,3,1,17,4,12,1,5,0,13,15]
  ```
  Return value: the sum of the numbers in the array

  ### Solution 
  ````
  function totalPoints(scores) {
    let sum = 0
    scores.forEach(function (points) {
      sum += points  
    })
    return sum
  }
  ````

#### add the strings together
- Write a function `buildSentence` that takes in an array of words and uses `forEach` to add the strings together. It should also add a space, `" "`, after each word .

  Arguments: an array of strings, like:
  ```
  ["I'm", "looking", "for", "the", "man", "who", "shot", "my", "paw"]
  ```
  Return value: The full sentence, like
  ```
  "I'm looking for the man who shot my paw "
  ```
  Note the spaces.
  ### Solution 
  ````
  function buildSentence(words) {
    let sentence = ""
    words.forEach(function(word) {
      sentence += word + " "
    })
    return sentence
  }
  ````

#### `console.log` with template strings
- Write a function `logPercentages` that takes an array of decimal numbers and uses `forEach` to log each one with some formatting as shown below.

  The numbers should be formatted as percentages. That means:

  multiply by 100
  include the percent symbol`%` at the end of the string
  Arguments: an array of numbers like

  ```
  [
    0.75,
    0.91,
    0.48,
    0.23,
    0.99,
    0.83,
    1.10,
  ]
  ```
  Return value: none

  Use `forEach` and log each value using `console.log`.

  The logged values should look like:
  ```
  75%
  91%
  48%
  23%
  99%
  83%
  110%
  ```
  You may find it helpful to use template strings, but you don't have to.

  ### Solution 
  ````
  function logPercentages(nums) {
    nums.forEach(function(decimal) {
      console.log(`${decimal*100}%`)
    }) 
  }
  ````
  
## Let's practice using `find`

#### Find the first odd number
- Write a function firstOdd that uses find to find the first odd number in an array.

  Arguments: an array of numbers like

  ```[4,41,832,72,89,120,431,505,70]```
  
  Return value: the first odd number, if there is one. If there are no odd numbers, return undefined. For the array above, the function should return `41`

  Remember - you can find out if a number is odd using the `%` operator.

  `number % 2 === 1` // true, for odd numbers
  
  ### Solution 
  ````
  function firstOdd(nums) {
  let odd = nums.find(function (odds) {
    return odds % 2 === 1
  })
  return odd
  }
  ````
#### Find an object based on a property
- Write a function `getAdministrator` that uses `find` to return the first object that has `isAdmin: true` from a list of user objects.

  Arguments: an array of user objects, like

  ```
  [
    {
      "username": "carlie.beauchamp",
      "isAdmin": false
    },
    {
      "username": "wonda.garmon",
      "isAdmin": false
    },
    {
      "username": "myong.huntington",
      "isAdmin": false
    },
    {
      "username": "davis.brennan",
      "isAdmin": true
    },
    {
      "username": "porsha.stump",
      "isAdmin": false
    },
  ]
  ```
  Return the first user object that has a `true` value for the `isAdmin` property.

  In this case, the function should return the object
```
  {
    "username": "davis.brennan",
    "isAdmin": true
  }
  ```
  ### Solution 
  ````
  function getAdministrator(admins) {
  let admin = admins.find(function(name) {
    return name.isAdmin === true
  })
  return admin
}
  ````
  
#### Find the first number divisible by 10
- Write a function `divisibleByTen` that takes in an array of numbers, and uses `find` to return the first number that is a multiple of 10.

  Arguments: an array of numbers like:

  ```
  [4,41,832,72,89,120,431,505,70]
  ```
  
  Return value: the first number that's divisible by 10. If there are no numbers divisible by 10, return `undefined`.

  For the sample array above, the function should return `120`.
  
   ### Solution 
  ````
  function divisibleByTen(nums) {
  let multiple = nums.find(function(divide) {
    return divide % 10 === 0
  })
  return multiple
  } 
  ````
#### Find the first number divisible by a number provided as an argument
- Write a function `divisibleByX` that uses `find` to return the first number in the array that's divisible by another number, passed in as an argument.

  Arguments: an array of numbers, and another number, the divisor.

  `let numbers = [4,41,832,72,89,120,431,70]`
  
  `divisibleByX(numbers, 10)` // 120
  
  `divisibleByX(numbers, 3)` // 72
  
  `divisibleByX(numbers, 2)` // 4

  Return value: the first value in the array that's divisible by the number that's the second argument. If there are no values that are divisible by the second argument, return undefined.
  
  ### Solution 
  
  ````
  function divisibleByX(nums, divisor) {
  let divide = nums.find(function(x) {
    return x % divisor === 0
  })
  return divide
  }
  ````

#### Find the first string that starts with a letter provided as an argument
- Write a function `startsWithLetter` that uses `find` to return the first string that starts with a particular letter.

  Arguments: an array of strings, and a letter.
  Return value: the first string that has that letter as the first character of the string.

  Example:

  `let strings = ["Do you want to hear a joke?", "It's about a three-legged dog", "The dog walks into a bar", "The dog says, ", "\"I'm looking for the man who shot my paw\"", "Get it?"]`
  
  `startsWithTheLetter(strings, "T")` // "The dog walks into a bar"
  
  `startsWithTheLetter(strings, "I")` // "It's about a three-legged dog"
  
  If there's no string in the array that starts with that letter, return `undefined`. The function should leave lowercase and uppercase letters alone, so:
`startsWithTheLetter(strings, "i")` // undefined
  As a bonus: throw an error `"Letter must be a string of length 1"` if the second argument is not a string, or if its `.length` is more than 1.

  `startsWithTheLetter(strings, "dog")` // Error: Letter must be a string of length 1

  ### Solution 
  
  ````
  function startsWithLetter(words, letter) {
  let firststring = words.find(function(word) {
    return word.charAt(0) === letter
  })
  return firststring
  }
  ````
  
## Let's practice using `filter`

#### Even Numbers
- Write a function evenNumbers that uses filter to return only the even numbers from an array of numbers.

  Arguments: an array of numbers like

  ```[4,41,832,72,89,120,431,505,70]
  ```
  Return value: an array of even numbers. If there are no even numbers, return an empty array. For the array above, the function should return `[4,832,72,120,70]`

  Remember - you can find out if a number is even using the `%` operator.
  
  `number % 2 === 0 `// true, for even numbers
  
  ### Solution 
  
  ````
  function evenNumbers(nums) {
  let evens = nums.filter(function(numbers) {
    return numbers % 2 === 0
  })
  return evens
  }
  ````

#### Numbers greater than 100

  - Write a function `greaterThan100` that takes in an array of numbers, and uses `filter` to return an the ones that are greater than 100.

  Arguments: an array of numbers like:

  ```
  [4,41,832,72,89,120,431,505,70]
  ```
  Return value: an array of numbers greater than 100. If there are no numbers greater than 100, return an empty array.

  For the sample array above, the function should return `[832,120,431,505]`.
  
  ### Solution 
  
  ````
  function greaterThan100(nums) {
  let hundos = nums.filter(function(numbers) {
    return numbers > 100
  })
  return hundos
}
  ````

#### Users that are not administrators
  - Write a function `nonAdminUsers` that uses `filter` to return the users who are not admins.

  Arguments: an array of user objects, like
  ```
  [
    {
      "username": "carlie.beauchamp",
      "isAdmin": false
    },
    {
      "username": "wonda.garmon",
      "isAdmin": false
    },
    {
      "username": "myong.huntington",
      "isAdmin": false
    },
    {
      "username": "davis.brennan",
      "isAdmin": true
    },
    {
      "username": "porsha.stump",
      "isAdmin": false
    },
  ]
  ```
  Return an array of user objects that have `false` value for the `isAdmin` property.

  For this sample input, it should return an array of 4 users - all except the one with `isAdmin: true`.
   ### Solution 
  
  ````
  function nonAdminUsers(people) {
  let nonAdmin = people.filter(function(admin) {
    return admin.isAdmin === false
  })
  return nonAdmin
}
  ````

#### Count of the users that are admins
  - Write a function `countAdminUsers` that returns the number of users that have `isAdmin: true`. It should use `filter` and then `.length` on the result from `filter`.

  For this sample input, it should return `1`, because there is only one admin user.
  
  ### Solution 
  
  ````
  function countAdminUsers(people) {
  let areAdmin = people.filter(function(admin) {
    return admin.isAdmin === true
  })
  return areAdmin.length
}
  ````

#### Strings shorter than a specified length
  - Write a function `shorterThanX` that takes an array of strings and a `maxLength` number and uses `filter` to return all the strings shorter than the `maxLength`.

  Arguments: an array of strings, and a number.
  Return value: an array of strings that have `.length` less than the number.

  Example:

  `
  let strings = ["Four score and seven years ago", "our forefathers brought forth on this continent a new nation", "concieved in liberty", "and dedicated to the proposition that all men are created equal", "Now we are engaged in a great civil war", "testing whether that nation", "or any so conceived and so dedicated", "can long endure."]
  `
  
  `shorterThanX(strings, 20)` // ["can long endure."]
  
  `shorterThanX(strings, 30)` // [ 'concieved in liberty',  'testing whether that nation',  'can long endure.' ]
  
  If there's no strings in the array that are shorter than the number, return an empty array.
  
  ### Solution 
  
  ````
  function shorterThanX(strings, max) {
  let shortStrings = strings.filter(function(word) {
    return word.length < max
  })
  return shortStrings
}
````

#### Only the strings from an array of different types
  - Write a function `onlyStrings` that takes an array that has different kinds of elements and uses `filter` to return an array of only the strings.

  Arguments: an array of different types of elements.
  Return value: an array with only the strings from the input array.

  `let manyTypes = [4, "4", "four score", 80, {age: 80}, ["nations"], {type: "free"}, "states"]`
  
  `onlyStrings(manyTypes)` //=> `["4","four score", "states"]`
  
  ### Solution 
````
function onlyStrings(strings) {
  let stringsOnly = strings.filter(function(arr) {
    return typeof(arr) === 'string'
    })
   return stringsOnly
  }
  ````
  
## Let's practice using `map`

#### Add 3 to all the numbers
- Write a function addThreeToAll that uses `map` to add 3 to each number in an array of numbers.

  Arguments: an array of numbers like

  `[4,41,832,72,89,120,431,505,70]`

  Return value: an array of numbers, each 3 more than the input array. For the array above, the function should return `[7,44,835,75,92,123,434,508,73]`

 ### Solution 
````
function addThreeToAll(preThree) {
  let plusThree = preThree.map(number => number +3 )
  return plusThree
}
````

#### Square all the numbers
- Write a function `squareAll` that takes in an array of numbers, and uses `map` to return an array of each of the numbers, squared.

  Arguments: an array of numbers like:

  `[4,41,832,72,89,120,431,505,70]`
Return value: an array of numbers, each the square of the input array.

For the sample array above, the function should return `[16, 1681, 692224, 5184, 7921, 14400, 185761, 255025, 4900]`.

Remember, you can square a number by multiplying it by itself, or by using the exponent operator:

`let number = 4`

`number * number` // 16

`number ** 2` // 16

Note that the caret operator `^` does not mean exponent in JavaScript.

 ### Solution 
````
function squareAll(preSquare) {
  let squares = preSquare.map(number => number * number )
  return squares
}
````

#### Add the greeting to each of the names
- Write a function `allGreetings` that takes an array of names (strings) and returns an array of greetings (strings).

  The greetings should each be `"Hello, [name], nice to meet ya!"`

  Arguments: an array of strings, each a name of someone to greet 
  
  Return value: an array of strings, with the greeting added to the name.

`let names = ['Terri Melia', 'Manpreet Wong', 'Madelyn Francis', 'Theia Kane', 'Arwel Barrera', 'Humza Medina', 'Jean-Luc Robles', 'Gianni Head', 'Rowan Skinner', 'Jago Blevins']`

`allGreetings(names)` // => ['Hello, Terri Melia, nice to meet ya!', 'Hello, Manpreet Wong, nice to meet ya!', 'Hello, Madelyn Francis, nice to meet ya!', 'Hello, Theia Kane, nice to meet ya!', 'Hello, Arwel Barrera, nice to meet ya!', 'Hello, Humza Medina, nice to meet ya!', 'Hello, Jean-Luc Robles, nice to meet ya!', 'Hello, Gianni Head, nice to meet ya!', 'Hello, Rowan Skinner, nice to meet ya!', 'Hello, Jago Blevins, nice to meet ya!']

You might find it helpful to use template strings.
 ### Solution 
````
function allGreetings(names) {
  let greetings = names.map(greet => `Hello, ${greet}, nice to meet ya!`)
  return greetings
}
````

#### Get the username from each of the users
- Write a function `getUsernames` that takes in an array of user objects and uses `map` to return an array of just the usernames.

  Arguments: an array of user objects like

  ```
  let users = [
  {
    "username": "carlie.beauchamp",
    "isAdmin": false
  },
  {
    "username": "wonda.garmon",
    "isAdmin": false
  },
  {
    "username": "myong.huntington",
    "isAdmin": false
  },
  {
    "username": "davis.brennan",
    "isAdmin": true
  },
  {
    "username": "porsha.stump",
    "isAdmin": false
  },
  ]
  ```

Return value: an array of strings with just the usernames, like

`getUsernames(users)` // => ['carlie.beauchamp', 'wonda.garmon', 'myong.huntington', 'davis.brennan', 'porsha.stump']

 ### Solution 
  ````
  function getUsernames(users) {
    let usernames = users.map(name => name.username)
    return usernames
  }
  ````

#### Write a `'pluck'` function
- Write a function `pluck` that takes in an array of objects and a string representing a key, and uses `map` to return an array of the values at that key for each of the objects.

Arguments: an array of objects, and a string key


Return value: an array of the values at that key

For example, if we used the users array from the last exercise, we could do:

`pluck(users, 'username')` // => ['carlie.beauchamp', 'wonda.garmon', 'myong.huntington', 'davis.brennan', 'porsha.stump']

`pluck(users, 'isAdmin')` // => [false, false, false, true, false]
If any of the objects does not have a value at that key, the array should have undefined in that slot.

`let birds = [{species: "warbler", weight: "0.45oz"}, {species: "jay"}, {species: "raven", weight: "1.6lbs"}]`
`pluck(birds, 'weight')` // ["0.45oz", undefined, "1.6lbs"]

Hint: Using the square bracket notation, you can access a property of an object using a variable.

`let bird = {species: "warbler", weight: "0.45oz"}`
`let key = 'species'`
`bird[key]` //=> "warbler"
