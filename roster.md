Instructions
Read the scenario description and the instructions. Then implement the functions in the solution file, per the descriptions here. Click the 'Submit Solution' button to run the tests to get feedback on whether your functions are working.

Scenario
The football team needs help managing their roster! Use your javascript skills to help us solve these challenges:

Count the number of players
Find the top scoring player
List players names and numbers for their jerseys
Do we have enough players at each position?
Given the roster and a position, count the number of players at that position
Given the roster and a list of positions, return an object with the count for each position
For all of the functions, the roster will look like this:

let roster = [
  {
    "number": 10,
    "isActive": true,
    "age": 30,
    "name": "Allen Hicks",
    "pointsScored": 17,
    "gamesPlayed": 2,
    "yearsPlayed": 4,
    "position": "c"
  },
  {
    "number": 11,
    "isActive": true,
    "age": 40,
    "name": "Concepcion Cash",
    "pointsScored": 21,
    "gamesPlayed": 6,
    "yearsPlayed": 3,
    "position": "c"
  },
  {
    "number": 12,
    "isActive": false,
    "age": 34,
    "name": "Carlson Morin",
    "pointsScored": 24,
    "gamesPlayed": 4,
    "yearsPlayed": 1,
    "position": "lt"
  }
]
Count the number of players
Write a function countPlayers that accepts one argument, the roster of players as an array.

It should return the total number of players on the roster.

Find the top scoring player
Write a function topScoringPlayer that accepts one argument, the roster of players as an array.

It should return the player in the roster with the highest score.

It should return the whole player object (not the name or any other value from the player object)
If the array is empty, it should return null
If two players have the same score, it should return the one that appears first in the list
List players names and numbers for their jerseys
Write a function namesAndNumbers that accepts one argument, the roster of players as an array.

It should return an array of strings with the players' names and numbers as they'll appear on the back of the jersey. So, a player with name: "Allen Hicks" and number 10 should have a jersey string "Allen Hicks\n10".

The return value should be an array
The return value should have one string for each player in the roster
The strings need to match exactly what is described (the tests are not forgiving)
namesAndNumbers(roster)
If the roster only had the three example players as above, the function should return:

[
  "Allen Hicks\n10",
  "Concepcion Cash\n11",
  "Carlson Morin\n12"
]
Do we have enough players at each position?
We need to see the number of players at each position, so that we can make sure that we have all the players we need.

Part 1: Given the roster and a position, count the number of players at that position
Write a function countPlayersAtPosition that accepts two arguments, the roster of players as an array and a position as a string.

It should return the number of players who play in that position.

For instance, in the whole roster, there are 6 players who have position 'c', so the function should return 6, as shown:

countPlayersAtPosition(roster, 'c') //=> 6
Part 2: Given the roster and a list of positions, return an object with the count for each position
Write a function countPositions that accepts two arguments, the roster as an array, and an array of strings representing positions.

It should return an object with the count for each position.

If called like this:

countPositions(roster, ['c', 'lt', 'rg'])
Then the return value should be

{
  c: 6,
  lt: 7,
  rg: 4,
}
The values on the right are the counts of players at that position, just like the countPlayersAtPosition function. You are encouraged to use that function as a helper function if it helps you.
