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

  ```[4,41,832,72,89,120,431,505,70]```
  Return value: the first number that's divisible by 10. If there are no numbers divisible by 10, return `undefined`.

  For the sample array above, the function should return `120`.
  
   ### Solution 
  ````
  function divisibleByTen(nums) {
  let multiple = nums.find(function(divide) {
    return divide % 10 === 0
  })
  return multiple
} ````
