# Resources

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON# 
- Objects: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object
- Arrays: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/prototype
- Strings: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
- Recursion Article: https://codeburst.io/learn-and-understand-recursion-in-javascript-b588218e87ea
- typeof: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof
- instanceof: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof
- Turn a JSON string to an object
  
    `JSON.parse(data: string): object`
 - Turn an object to a JSON string
  
    `JSON.stringify(data: object): string`
 - Get the keys of an object into an array
  
    `Object.keys(data: object): Array(string)`
 - Iterate through each key of an object.
  
 ```
 for (const property in object) {
  console.log(`${property}: ${object[property]}`);`
  }
```

# Part I

- Given that you have an already valid JSON string where the keys are all kebab-case, write a function called `transformKebabCaseToCamelCase` that takes in this JSON string and returns a JSON string where all the keys are transformed to be camelCase.
   
```
const exampleJson = {
      "first-name": "Chanda",
      "last-name": "Hubbard",
      "city-and-state": "Oakland, CA",
      "zip": "12345-1234"
     };
 ```

```
function transformKebabCaseToCamelCase(data) {
  // Example is that if I was passed '{"first-name": "Fred"}', the result
  // should be '{"firstName": "Fred"}'
  return data;
}
const result = transformKebabCaseToCamelCase(exampleJson);
console.log(result);
document.getElementById("app").innerHTML = result;
```
## My Solution 



```
function transformKebabCaseToCamelCase(data) {
  // Example is that if I was passed '{"first-name": "Fred"}', the result
  // should be '{"firstName": "Fred"}'
  Object.entries(data).forEach(entry => {
    const [key, value ] = entry
    let toCamel= (x) => (`${JSON
                              .parse(JSON
                                  .stringify(x)
                                  .split("-")
                                  .map(x => x.charAt(0)
                                      .toUpperCase() + x.slice(1))
                                      .join(""))}`)
    console.log(`"${toCamel(key)}": "${value}"`)
  })
}

transformKebabCaseToCamelCase(exampleJson)

```

### Output

```
'"firstName": "Chanda"'
'"lastName": "Hubbard"'
'"cityAndState": "Oakland, CA"'
'"zip": "12345-1234"'
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
