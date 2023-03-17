# adv.java.object
Name : dhruv shrimali
 MODULE: 2 (Data Types and Objects)

1. Write the code, one line for each action: 
a) Create an empty object user. 
b) Add the property name with the value John. 
c) Add the property surname with the value Smith. 
d) Change the value of the name to Pete. 
e) Remove the property name from the object.
Ans. const user = {};
user.name = "John";
user.surname = "Smith";
user.name = "Pete";
delete user.name;

2. Is array copied? 
let fruits = ["Apples", "Pear", "Orange"]; // push a new value into the "copy" 
let shoppingCart = fruits; shoppingCart.push("Banana"); // what's in fruits? 
alert( fruits.length ); // ?
Ans. In the given code, the shoppingCart variable is not a copy of the fruits array, but it is referencing the same array object as fruits. This means that any changes made to shoppingCart will also affect the fruits array, because they both point to the same array object in memory. 
Therefore, after the code runs, the fruits array will contain the additional value "Banana" that was pushed onto shoppingCart. The alert(fruits.length) statement will output 4, because there are now four elements in the fruits array: ["Apples", "Pear", "Orange", "Banana"].

3. Map to names let john = { name: "John", age: 25 }; let pete = { name: "Pete", age: 30 }; let mary = { name: "Mary", age: 28 }; let users = [ john, pete, mary ]; let names = /* ... your code */ alert( names ); // John, Pete, Mary
Ans. let john = { name: "John", age: 25 };
let pete = { name: "Pete", age: 30 };
let mary = { name: "Mary", age: 28 };
let users = [ john, pete, mary ];
let names = users.map(user => user.name);
alert(names); // John, Pete, Mary

4. Map to objects let john = { name: "John", surname: "Smith", id: 1 }; let pete = { name: "Pete", surname: "Hunt", id: 2 }; let mary = { name: "Mary", surname: "Key", id: 3 }; let users = [ john, pete, mary ]; let usersMapped = /* ... your code ... */
/* 
usersMapped = [ 
{ fullName: "John Smith", id: 1 }, 
{ fullName: "Pete Hunt", id: 2 }, 
{ fullName: "Mary Key", id: 3 } 
] 
*/ alert( usersMapped[0].id ) // 1 alert( usersMapped[0].fullName ) // John Smith
Ans. let john = { name: "John", surname: "Smith", id: 1 };
let pete = { name: "Pete", surname: "Hunt", id: 2 };
let mary = { name: "Mary", surname: "Key", id: 3 };
let users = [ john, pete, mary ];
let usersMapped = users.map(user => ({ fullName: `${user.name} ${user.surname}`, id: user.id }));
/*
usersMapped = [
  { fullName: "John Smith", id: 1 },
  { fullName: "Pete Hunt", id: 2 },
  { fullName: "Mary Key", id: 3 }
]
*/
alert(usersMapped[0].id); // 1
alert(usersMapped[0].fullName); // John Smith

5. Sum the properties There is a salaries object with arbitrary number of salaries. Write the function sumSalaries(salaries) that returns the sum of all salaries using Object.values and the for..of loop.If salaries is empty, then the result must be 0. 
let salaries = {
	"John": 100, 
"Pete": 300, 
"Mary": 250 
}; 
alert( sumSalaries(salaries) ); // 650
Ans. function sumSalaries(salaries) {
  let sum = 0;
  for (let salary of Object.values(salaries)) {
    sum += salary;
  }
  return sum;
}
let salaries = {
  "John": 100,
  "Pete": 300,
  "Mary": 250
};
alert(sumSalaries(salaries)); // 650

6. Destructuring assignment We have an object: Write the Destructuring assignment that reads: 
a) Name property into the variable name. 
b) Year’s property into the variable age. 
c) isAdmin property into the variable isAdmin (false, if no such property) 
d) let user = { name: "John", years: 30};
Ans. let user = { name: "John", years: 30 };
let { name, years: age, isAdmin = false } = user;
console.log(name);     // "John"
console.log(age);      // 30
console.log(isAdmin);  // false

7. Turn the object into JSON and back Turn the user into JSON and then read it back into another variable. 
user = { name: "John Smith", age: 35};
Ans. let user = { name: "John Smith", age: 35 };
let userJson = JSON.stringify(user); 
console.log(userJson);
let userObject = JSON.parse(userJson);
console.log(userObject);  
