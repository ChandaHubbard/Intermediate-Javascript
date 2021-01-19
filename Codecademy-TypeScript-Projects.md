# TypeScript Project - Codecademy - "Restaurant Orders"

## index.ts
````
import { restaurants, Restaurant } from "./restaurants";
import { orders, Order, PriceBracket } from "./orders";

/// Add your getMaxPrice() function below:
function getMaxPrice(price: PriceBracket) {
  switch(price) {
    case PriceBracket.Low:
      return 10.0;
    case PriceBracket.Medium:
      return 20.0;
    case PriceBracket.High:
      return 30.0;
  }
}

/// Add your getOrders() function below:
function getOrders(price: PriceBracket, orders: Order[][]) {
  let filteredOrders: Order[][] = [];
  orders[0].filter((order: Order) => order.price <= getMaxPrice(price));

  orders.forEach((restaurant: Order[]) => {
    const result = restaurant.filter((order: Order) => order.price <= getMaxPrice(price));
  filteredOrders.push(result);
  });
  return filteredOrders;
  }

/// Add your printOrders() function below:
function printOrders(restaurants: Restaurant[], orders: Order[][]) {
  restaurants.forEach((restaurant: Restaurant, index: number) => {
    if(orders[index].length > 0){
    console.log(restaurant.name);
    orders[index].forEach((order) => {
      console.log(`- ${order.name}: ${order.price}`);
    })
    }
  })
}

/// Main
const elligibleOrders = getOrders(PriceBracket.Low, orders);
// console.log(elligibleOrders)
printOrders(restaurants, elligibleOrders);

````
## restaurants.ts
````
import { restaurants, Restaurant } from "./restaurants";
import { orders, Order, PriceBracket } from "./orders";

/// Add your getMaxPrice() function below:
function getMaxPrice(price: PriceBracket) {
  switch(price) {
    case PriceBracket.Low:
      return 10.0;
    case PriceBracket.Medium:
      return 20.0;
    case PriceBracket.High:
      return 30.0;
  }
}

/// Add your getOrders() function below:
function getOrders(price: PriceBracket, orders: Order[][]) {
  let filteredOrders: Order[][] = [];
  orders[0].filter((order: Order) => order.price <= getMaxPrice(price));

  orders.forEach((restaurant: Order[]) => {
    const result = restaurant.filter((order: Order) => order.price <= getMaxPrice(price));
  filteredOrders.push(result);
  });
  return filteredOrders;
  }

/// Add your printOrders() function below:
function printOrders(restaurants: Restaurant[], orders: Order[][]) {
  restaurants.forEach((restaurant: Restaurant, index: number) => {
    if(orders[index].length > 0){
    console.log(restaurant.name);
    orders[index].forEach((order) => {
      console.log(`- ${order.name}: ${order.price}`);
    })
    }
  })
}

/// Main
const elligibleOrders = getOrders(PriceBracket.Low, orders);
// console.log(elligibleOrders)
printOrders(restaurants, elligibleOrders);

````
## orders.ts
````
export enum PriceBracket {
 Low, // $0 - $10
 Medium, // $10 - $20
 High, // $20 - $30
}

export const orders = [
 [
   {
     name: "Miso Ramen",
     price: 15.99,
   },
   {
     name: "Gyoza and Rice",
     price: 7.99,
   },
   {
     name: "Sashimi Lunch Set",
     price: 13.99,
   },
 ],
 [
   {
     name: "Chicken and Waffles",
     price: 9.99,
   },
   {
     name: "Buffalo Wings Special",
     price: 8.99,
   },
   {
     name: "Rottiserie Meal Deal",
     price: 11.99,
   },
 ],
 [
   {
     name: "Rigatoni Bolognese",
     price: 24,
   },
   {
     name: "Insalata Di Parma",
     price: 20,
   },
   {
     name: "Lasagna Al Forno",
     price: 22,
   },
 ],
 [
   {
     name: "Turkey Bacon Bagel",
     price: 6.99,
   },
   {
     name: "Lox Cream Cheese Bagel",
     price: 9.99,
   },
   {
     name: "Pastrami Swiss Bagel",
     price: 7.99,
   },
 ],
 [
   {
     name: "Xiao Long Bao",
     price: 14.99,
   },
   {
     name: "Red Bean Buns",
     price: 12.49,
   },
   {
     name: "Kurobuta Pork Shao Mai",
     price: 14.99,
   },
 ],
];

export type Order = typeof orders[0][0];

````
# Output
````
Silver Rice Sushi 🍣
- Gyoza and Rice: 7.99
Nikko's Rotisserie Chicken 🍗
- Chicken and Waffles: 9.99
- Buffalo Wings Special: 8.99
Lula Bagel 🥯
- Turkey Bacon Bagel: 6.99
- Lox Cream Cheese Bagel: 9.99
- Pastrami Swiss Bagel: 7.99
````

# TypeScript Project - Codecademy - "Unionversity"

## index.ts
````
import courses from './courses';
import studyGroups from './studyGroups';

type Course = {
  id: number;
  studyGroupId: number;
  title: string;
  keywords: string[];
  eventType: string;
}

type StudyGroup = {
    id: number;
    courseId: number;
    title: string;
    keywords: string[];
    eventType: string;
  }

type SearchEventOptions = {
  query: string | number;
  eventType: 'courses' | 'groups';
}

let enrolledEvents: (Course | StudyGroup)[] = []

function searchEvents(options: SearchEventOptions){
  const events: (Course | StudyGroup)[] = options.eventType === 'courses' ? courses: studyGroups;
  return events.filter((event: Course | StudyGroup) => {
    if(typeof options.query === 'number') {
      return event.id === options.query;
    }
    if(typeof options.query === 'string') {
      return event.keywords.includes(options.query)
    }
  })
}


function enroll(event: Course | StudyGroup) {
 enrolledEvents = [...enrolledEvents, event];
}

const searchResults = searchEvents({query: 'art', eventType: 'courses'})
console.log(searchResults)

enroll(searchResults[0])

console.log(enrolledEvents)
````
## courses.ts

````
const courses = [
  {
    id: 1,
    studyGroupId: 1,
    title: 'Improvisational Arts Lab',
    keywords: ['improv', 'art', 'performance', 'lab'],
    eventType: 'course',
  },
  {
    id: 2,
    studyGroupId: 2,
    title: 'Research Methods 1',
    keywords: ['lab', 'research', 'science', 'self-study'],
    eventType: 'course',
  },
  {
    id: 3,
    studyGroupId: 3,
    title: '19th Century Art',
    keywords: ['1800s', 'art', 'history'],
    eventType: 'course',
  },
];

export default courses;
````
## studyGroups.ts

````
const studyGroups = [
  {
    id: 1,
    courseId: 1,
    title: 'Improvisational Arts Lab Study Group',
    keywords: ['improv', 'art', 'performance', 'lab'],
    eventType: 'group',
  },
  {
    id: 2,
    courseId: 2,
    title: 'Research Methods 1 Study Group',
    keywords: ['lab', 'research', 'science', 'self-study'],
    eventType: 'group',
  },
  {
    id: 3,
    courseId: 3,
    title: '19th Century Art Study Group',
    keywords: ['1800s', 'art', 'history'],
    eventType: 'group',
  },
];

export default studyGroups;
````
## tsconfig.json

````
{
  "compilerOptions": {
    "target": "es2017",
    "module": "commonjs"
  },
  "include": ["**/*.ts"]
}
````

## output
````
[
  {
    id: 1,
    studyGroupId: 1,
    title: 'Improvisational Arts Lab',
    keywords: [ 'improv', 'art', 'performance', 'lab' ],
    eventType: 'course'
  },
  {
    id: 3,
    studyGroupId: 3,
    title: '19th Century Art',
    keywords: [ '1800s', 'art', 'history' ],
    eventType: 'course'
  }
]
[
  {
    id: 1,
    studyGroupId: 1,
    title: 'Improvisational Arts Lab',
    keywords: [ 'improv', 'art', 'performance', 'lab' ],
    eventType: 'course'
  }
]
$
````
