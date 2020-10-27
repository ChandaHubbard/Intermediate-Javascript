# Practice JS Array Methods 

## Let's practice using `forEach`

## `forEach`
## `console.log` the strings
Write a function `printNames` that uses `forEach` to log each name to the console.

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

### `console.log` object properties
Write a function `logTreeTypethat` uses `forEach` to log the type of each tree object to the console.

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

#### Solution 
````
function logTreeType(trees) {
  trees.forEach(function (tree) {
    console.log(`${tree.type}`)
  })
}
````


sum the numbers
Write a function totalPoints that uses forEach to add up an array of numbers.

Arguments: an array of numbers, like

[6,7,1,3,1,17,4,12,1,5,0,13,15]
Return value: the sum of the numbers in the array

add the strings together
Write a function buildSentence that takes in an array of words and uses forEach to add the strings together. It should also add a space, " ", after each word .

Arguments: an array of strings, like:

["I'm", "looking", "for", "the", "man", "who", "shot", "my", "paw"]
Return value: The full sentence, like

"I'm looking for the man who shot my paw "
Note the spaces.

console.log with template strings
Write a function logPercentages that takes an array of decimal numbers and uses forEach to log each one with some formatting as shown below.

The numbers should be formatted as percentages. That means:

multiply by 100
include the percent symbol% at the end of the string
Arguments: an array of numbers like

[
  0.75,
  0.91,
  0.48,
  0.23,
  0.99,
  0.83,
  1.10,
]
Return value: none

Use forEach and log each value using console.log.

The logged values should look like:

75%
91%
48%
23%
99%
83%
110%
You may find it helpful to use template strings, but you don't have to.







function totalPoints(scores) {
  let sum = 0
  scores.forEach(function (points) {
    sum += points  
  })
  return sum
}

function buildSentence(words) {
  let sentence = ""
  words.forEach(function(word) {
    sentence += word + " "
  })
  return sentence
}

function logPercentages(nums) {
  nums.forEach(function(decimal) {
    console.log(`${decimal*100}%`)
  }) 
}