# Useful Code Snippets

Try finding your ancestors and offspring with code.

Create a function that takes a number` x` and a character `y` ("m" for male, "f" for female), and returns the name of an ancestor (m/f) or descendant (m/f).

If the number is negative, return the related ancestor.
If positive, return the related descendant.
You are generation 0. In the case of 0 (male or female), return "me!".
##### Examples

`generation(2, "f") ➞ "granddaughter"`

`generation(-3, "m") ➞ "great grandfather"`

`generation(1, "f") ➞ "daughter"`


Generation	|Male|	Female
--- | --- | ---
-3	|great grandfather |	great grandmother
-2	|grandfather|	grandmother
-1	|father	|mother
0	|me!	|me!
1	|son|	daughter
2	|grandson|	granddaughter
3	|great grandson	|great granddaughter

### Input 
```
function generation(x, y) {
	const generation = {
		'-3': {m : "great grandfather", f: "great grandmother"},
		'-2': {m : "grandfather", f: "grandmother"},
		'-1': {m : "father", f: "mother"},
		0: {m : "me!", f: "me!"},
		1: {m : "son", f: "daughter"},
		2: {m : "grandson", f: "granddaughter"},
		3: {m : "great grandson", f: "great granddaughter"}
	}
return generation[x][y]
}
```


## 

`const removeDups = arr => [...new Set(arr)]`

## `for...in`

```
for (let crewMember in spaceship.crew) {
  console.log(`${crewMember}: ${spaceship.crew[crewMember].name}`);
}
```


```
for(const age in names) {
	names[age] += Math.abs(n)
	}
return names
```
## 
Swap Object keys & values
```
function invert(o) {
	let switcheroo = Object.entries(o).reduce((r, [k, v]) => (r[v]=k, r), {})
	return switcheroo
}
```
## The Box Model - CSS
![](https://content.codecademy.com/courses/freelance-1/unit-4/diagram-boxmodel.svg)

## `.padStart()`

````
const str1 = '5';

console.log(str1.padStart(2, '0'));
// expected output: "05"

const fullNumber = '2034399002125581';
const last4Digits = fullNumber.slice(-4);
const maskedNumber = last4Digits.padStart(fullNumber.length, '*');

console.log(maskedNumber);
// expected output: "************5581"

````
