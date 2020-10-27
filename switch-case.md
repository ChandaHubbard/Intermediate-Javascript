# Switch /Case

https://www.qualified.io/assess/5e8e2b1aa78b15001b426e15

````
## Switch/Case: Rock Facts
Let's practice working with `switch` and `case`. Remember: this syntax is another way to handle control flow.

Write a function called `rockFacts` that takes in a kind of rock, as a string. It should use `switch` and `case` to return the correct fact, depending on which kind of rock is passed in.

If the argument is `'metamorphic'` it returns the string: `"Created by extreme heat and pressure"`
If the argument is `'igneous'`, it returns the string: `"Formed through the cooling and solidification of magma or lava"`
If given the argument `'sedimentary' it returns the string: "Formed by the accumulation or deposition of small particles"`
Otherwise, it should return `"Please provide an appropriate rock type."`

### Solution: 
````
function rockFacts(rock) {
  switch(rock) {
    case "metamorphic":
      return 'Created by extreme heat and pressure';
      break;
    case 'igneous' :
      return "Formed through the cooling and solidification of magma or lava"
      break
    case 'sedimentary' :
      return "Formed by the accumulation or deposition of small particles" 
      break
    default :
      return "Please provide an appropriate rock type."
  }
}
````

## Switch/Case: Parsing Number Input
We have a data set with lots of important numbers. Unfortunately, the data is very inconsistent. The items in the collection can look like any of the following:

- `34`
- `"34"`
- `{input: 34}`

We want to get the number out, whichever kind of input we have.

Write a function called `parseNumber` that gets one of these as an argument, and uses a switch statement to handle the different cases.

- If given a number, return the number
- If given a string, convert it to a number and return the result
- If given an object, return the value of the input property
- Otherwise, throw an error: `"Unexpected data type"`

### Hints
You can use `typeof` to get the type of a value
You can use `parseInt` to convert from a string to a number

### Solution: 
````
function parseNumber(nums) {
  switch(typeof nums) {
    case 'number':
      return nums
      break
    case 'string':
      return +nums
      break
    case 'object':
      return +Object.values(nums)
      break
    default :
      throw new Error("Unexpected data type")
    
  }
}
````

