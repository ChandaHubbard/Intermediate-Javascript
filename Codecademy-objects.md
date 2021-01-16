# Meal Maker Objects Project
- implement the `set()` methods

````
let menu = {
  _courses: {
     get courses() {
       return {
         appetizers: this.appetizers,
         mains: this.mains,
         desserts: this.desserts
    }
  },
  appetizers: [],
  mains: [],
  desserts: [] 
  },
  get appetizers() {
    return this._appetizers
  }, 
  get mains() {
    return this._mains
    }, 
  get desserts() {
    return this._desserts
    }, 
  set appetizers(appetizerIn) {},
  set mains(mainIn) {  },
  set desserts(dessertIn) {},
  addDishToCourse(courseName, dishName, dishPrice) {
   const dish =  {
     name: dishName,
     price: dishPrice
   };
   return this._courses[courseName].push(dish);
  },
  getRandomDishFromCourse(courseName) {
    const dishes = this._courses[courseName]
    const randomIndex = Math.floor(Math.random() * dishes.length);
    return dishes[randomIndex]
  },
  generateRandomMeal() {
    const appetizer = this.getRandomDishFromCourse('appetizers');
    const mains = this.getRandomDishFromCourse('mains');
    const desserts = this.getRandomDishFromCourse('desserts');
    const totalPrice = appetizer.price + mains.price + desserts.price;
    return `Your meal is ${appetizer.name}, ${mains.name} & a ${desserts.name}. The price is $${totalPrice.toFixed(2)}.`;
  }
  }

menu.addDishToCourse('mains', 'Bacon Cheese Burger with Mushroom and Swiss', 16.99)
menu.addDishToCourse('appetizers', 'Caesar Salad', 4);
menu.addDishToCourse('desserts', 'Lava Cake', 4.25);
menu.addDishToCourse('mains', 'spaghetti', 17.75)
menu.addDishToCourse('appetizers', 'Buffalo Wings', 8.99);
menu.addDishToCourse('desserts', 'Apple Blossom', 5.99);

let randomMeal = menu.generateRandomMeal()
console.log(randomMeal)
````

## Team Stats

 ````
 let team = {
  _players: [
    {
  firstName: 'Steph',
  lastName: 'Curry',
  age: 32
},
{
  firstName: 'Draymond',
  lastName: 'Green',
  age: 32
},
{
  firstName: 'Klay',
  lastName: 'Thompson',
  age: 30
}
],
  _games: [
    {
  opponent: 'Nets',
  teamPoints: 120,
  opponentPoints: 80
},
{
  opponent: 'Bucks',
  teamPoints: 115,
  opponentPoints: 114
},
{
  opponent: 'Celtics',
  teamPoints: 95,
  opponentPoints: 87
}
  ],
  get players() {
    return this._players
  },
  get games(){
    return this._games
  },
  addPlayer(firstName, lastName, age) {
    let player = {
      firstName,
      lastName,
      age
    }
    this.players.push(player)
  },
  addGame(opponent, teamPoints, opponentPoints){
    let game = {
      opponent, 
      teamPoints, 
      opponentPoints
    }
    this.games.push(game)
  }
};

team.addPlayer('Steph', 'Curry', 28)
team.addPlayer('Lisa', 'Leslie', 44)
team.addPlayer('Bugs', 'Bunny', 76)
team.addGame('Rockets', 100, 28)
team.addGame('Trailblazers', 108, 110)
team.addPlayer('Lakers', 120, 135)

console.log(team.players)
console.log(team.games)
````
