# TypeScript Project - Codecademy

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
