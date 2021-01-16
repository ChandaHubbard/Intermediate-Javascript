# Meal Maker Objects Project
- implement the `get()` and `set()` methods

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
  get appetizers() {}, 
  get mains() {}, 
  get desserts() {}, 
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
