# Resources

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON# 
- Objects: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object
- Arrays: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/prototype
- Strings: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
- Recursion Article: https://codeburst.io/learn-and-understand-recursion-in-javascript-b588218e87ea
- typeof: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof
- instanceof: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof

# Part I

- Given that you have an already valid JSON string where the keys are all kebab-case, write a function called `transformKebabCaseToCamelCase` that takes in this JSON string and returns a JSON string where all the keys are transformed to be camelCase.
  - Turn a JSON string to an object
  
    `JSON.parse(data: string): object`
  - Turn an object to a JSON string
  
    `JSON.stringify(data: object): string`
  - Get the keys of an object into an array
  
    `Object.keys(data: object): Array(string)`
  - Iterate through each key of an object.
  
    ```for (const property in object) {
      console.log(`${property}: ${object[property]}`);`
    }
    ```
    
```const exampleJson = {
      "first-name": "Chanda",
      "last-name": "Hubbard",
      "city-and-state": "Oakland, CA",
      "zip": "12345-1234"
     };
```

```function transformKebabCaseToCamelCase(data) {
  // Example is that if I was passed '{"first-name": "Fred"}', the result
  // should be '{"firstName": "Fred"}'
  return data;
}
const result = transformKebabCaseToCamelCase(exampleJson);
console.log(result);
document.getElementById("app").innerHTML = result;
```
## My Solution 

`let var1 = "first-name-last-second";`

```
function toCamel(case1) {
  let split = case1.split("-");
  let fullWord = [];
  fullWord.push(split[0]);
  for (let i = 1; i < split.length; i++) {
    fullWord.push(split[i].slice(0, 1).toUpperCase() + split[i].slice(1));
  }
  return fullWord.join("");
}


console.log(toCamel["name"]);
const result1 = toCamel(var1);
console.log(result1);

const nums = [0, 1, 2];
nums[2] = 3;
console.log(nums);

const numObj = { 0: 0, 1: 1, 2: 2 };
numObj[2] = 3;
numObj["foo"] = "something";
numObj.bar = "something else";
console.log(numObj);

console.log(typeof nums, Array.isArray(nums));
console.log(typeof numObj);
function transformKebabCaseToCamelCase(data) {
  // for (const property in data) {
  //   console.log(`${property}: ${data[property]}`);
  // }
  let dataObject = JSON.parse(data);
  let keys = Object.keys(dataObject);
  return keys.map((x) => toCamel(x));
}

```

### Extra Credit
Learn how to do this problem using Maps: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map

# Part II

Solve Part II of the problem using this as your example JSON:

```
const exampleJsonExpanded = `[{
"first-name": "Chanda",
"last-name": "Hubbard",
"address": {
"city-and-state": "Oakland, CA",
"zip": "12345-1234"
},
"pets": [{
"pet-gender": "male",
"pet-name": "Jamaal"
}, {
"pet-gender": "female",
"pet-name": "Taraji"
}]
}]`;
```
