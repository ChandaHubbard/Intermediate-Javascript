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

# TypeScript Project - Codecademy - "Park Service Volunteer Appreciation Program"

## index.ts

````
import {
  RaccoonMeadowsVolunteers,
  RaccoonMeadowsActivity,
  raccoonMeadowsVolunteers,
} from './raccoon-meadows-log';

import {
  WolfPointVolunteers,
  WolfPointActivity,
  wolfPointVolunteers,
} from './wolf-point-log';

type CombinedActivity = RaccoonMeadowsActivity | WolfPointActivity;

type Volunteers = {
  id: number;
  name: string;
  activities: CombinedActivity[];
};

function combineVolunteers(
  volunteers: (RaccoonMeadowsVolunteers | WolfPointVolunteers)[]
) {
  return volunteers.map((volunteer)=>{
    let id = volunteer.id;

    if(typeof id === 'string') {
      id = parseInt(id, 10)
    }
    return {
      id: id,
      name: volunteer.name,
      activities: volunteer.activities
    }
  })

}

function isVerified(verified: string | boolean) {
  if(typeof verified === 'string') {
    return verified === 'Yes';
  }
  return verified;
}

function getHours(activity: CombinedActivity) {
  if('hours' in activity) {
    return activity.hours;
  } else {
    return activity.time;
  }
}

function calculateHours(volunteers: Volunteers[]) {
  return volunteers.map((volunteer) => {
    let hours = 0;

    volunteer.activities.forEach((activity) => {
      if(isVerified(activity.verified)) {
        hours = hours + getHours(activity);
      }
    });

    return {
      id: volunteer.id,
      name: volunteer.name,
      hours: hours,
    };
  });
}

function byHours(a, b) {
  return b.hours - a.hours;
}

const combinedVolunteers = combineVolunteers(
  [].concat(wolfPointVolunteers, raccoonMeadowsVolunteers)
);

const result = calculateHours(combinedVolunteers)

console.log(result.sort(byHours))

````

## raccoon-meadows-log.ts

````
export type RaccoonMeadowsVolunteers = {
  id: number;
  name: string;
  activities: RaccoonMeadowsActivity[];
};

export type RaccoonMeadowsActivity = {
  description: string;
  hours: number;
  verified: string;
};

export const raccoonMeadowsVolunteers = [
  {
    id: 100,
    name: 'Rose Sutton',
    activities: [
      {
        description: 'Removed stump from trail head',
        hours: 3,
        verified: 'Yes',
      },
      {
        description: 'Cleared moss from storm drain',
        hours: 3,
        verified: 'No',
      },
    ],
  },
  {
    id: 101,
    name: 'Leigh Gilmour',
    activities: [
      {
        description: 'Trail maintenance',
        hours: 4,
        verified: 'Yes',
      },
    ],
  },
  {
    id: 102,
    name: 'Raj Wardle',
    activities: [
      {
        description: 'Cleaned campsite 14, 15, and 18',
        hours: 6,
        verified: 'Yes',
      },
    ],
  },
  {
    id: 103,
    name: 'Rayan Gutierrez',
    activities: [
      {
        description: 'Hung sign at new entrance of park',
        hours: 1,
        verified: 'Yes',
      },
      {
        description: 'Refilled maps at trail head 3',
        hours: 1,
        verified: 'Yes',
      },
      {
        description: 'Replaced trail markers for red trail',
        hours: 3,
        verified: 'Yes',
      },
    ],
  },
];

````

## wolf-point-log.ts
````
export type WolfPointVolunteers = {
  id: string;
  name: string;
  activities: WolfPointActivity[];
};

export type WolfPointActivity = {
  notes: string;
  time: number;
  verified: boolean;
};

export const wolfPointVolunteers = [
  {
    id: '400sg',
    name: 'Sarah Galloway',
    activities: [
      {
        notes: 'Cleaned up rock slide on south bend',
        time: 7,
        verified: true,
      },
    ],
  },
  {
    id: '401cm',
    name: 'Cormac Mcfarlane',
    activities: [
      {
        notes: 'Mowed Wolf Pup Landing',
        time: 3,
        verified: true,
      },
      {
        notes: 'Trimmed branches at Sit Point Lookout',
        time: 2,
        verified: true,
      },
    ],
  },
  {
    id: '402mm',
    name: 'Maisha Mcconnell',
    activities: [
      {
        notes: 'Picked up litter, hung signs about littering',
        time: 2,
        verified: false,
      },
    ],
  },
  {
    id: '403jr',
    name: 'Joanna Reilly',
    activities: [
      {
        notes: 'Mapped trail for Trail Lupine proposal',
        time: 5,
        verified: true,
      },
      {
        notes: 'Closed Howler Café for winter',
        time: 3,
        verified: true,
      },
    ],
  },
];
````
## tsconfig.json
````
{
  "compilerOptions": {
    "target": "ES6",
    "module": "commonjs"
  },
  "include": ["**/*.ts"]
}
````
## output

```
[
  { id: 403, name: 'Joanna Reilly', hours: 8 },
  { id: 400, name: 'Sarah Galloway', hours: 7 },
  { id: 102, name: 'Raj Wardle', hours: 6 },
  { id: 401, name: 'Cormac Mcfarlane', hours: 5 },
  { id: 103, name: 'Rayan Gutierrez', hours: 5 },
  { id: 101, name: 'Leigh Gilmour', hours: 4 },
  { id: 100, name: 'Rose Sutton', hours: 3 },
  { id: 402, name: 'Maisha Mcconnell', hours: 0 }
]
```


# TypeScript Project - Codecademy - "Self Driving Car"

## index.ts

````
import { getObstacleEvents } from './computer-vision';

//types
interface AutonomousCar {
  isRunning?: boolean;
  respond: (events: Events) => void;
}

interface AutonomousCarProps {
  isRunning?: boolean;
  steeringControl: Steering;
}

interface Events {
  [event: string]: boolean;
}

interface Control {
  execute: (command: string) => void;
}

interface Steering extends Control {
  turn: (direction: string) => void;

}

//classes
class Car implements AutonomousCar {
  isRunning;
  steeringControl;
  constructor(props: AutonomousCarProps) {
    this.isRunning = props.isRunning;
    this.steeringControl = props.steeringControl;
  }
  respond(events: Events){
    if(!this.isRunning) {
      return console.log('The car is off')
    }
    Object.keys(events).forEach(eventKey => {
      if(!events[eventKey]) {
        return
      }
      if(eventKey === 'ObstacleLeft'){
        this.steeringControl.turn('right');
      }
      if(eventKey === 'ObstacleRight'){
        this.steeringControl.turn('left');
      }
    })
  };
}

class SteeringControl implements Steering {
  execute(command: string) {
    console.log(`Executing: ${command}`);
  }
  turn(direction: string) {
    this.execute(`Turn ${direction}`);
  }
}

const steering = new SteeringControl();
const autonomousCar = new Car({ isRunning: true, steeringControl: steering})



//execution
autonomousCar.respond(getObstacleEvents())
// steering.turn('right');
````
## computer-vision.ts
````
export function getObstacleEvents() {
  const coinFlip = Boolean(Math.random() > 0.5);
  return { 
    'ObstacleLeft': coinFlip, 
    'ObstacleRight': !coinFlip 
  };
}
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
## Output

`Executing: Turn right`
or
`Executing: Turn left`
