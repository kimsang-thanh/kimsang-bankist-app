/\*
/////////////////////////////////////////////////
// Simple array methods
let arr = ['a', 'b', 'c', 'd', 'e'];

// SLICE
console.log(arr.slice(2));
console.log(arr.slice(2, 4));
console.log(arr.slice(-2));
console.log(arr.slice(-1));
console.log(arr.slice(1, -2));
console.log(arr.slice());
console.log([...arr]);

// SPLICE
// console.log(arr.splice(2));
arr.splice(-1);
console.log(arr);
arr.splice(1, 2);
console.log(arr);

// REVERSE
arr = ['a', 'b', 'c', 'd', 'e'];
const arr2 = ['j', 'i', 'h', 'g', 'f'];
console.log(arr2.reverse());
console.log(arr2);

// CONCAT
const letters = arr.concat(arr2);
console.log(letters);
console.log([...arr, ...arr2]);

// JOIN
console.log(letters.join(' - '));
const arr = [23, 11, 64];
console.log(arr[0]);
console.log(arr.at(1));

console.log(arr[arr.length - 1]);
////////////////////
// at method
console.log(arr.slice(-1)[0]);
console.log(arr.at(-1));

console.log('jonas'.at(-1));
\*/

/\*
//////////////////////////////////////
// Looping Array: forEach method
const movements = [200, 450, -400, 3000, -650, -130, 70, 1300];

// for (const movement of movements) {
for (const [i, movement] of movements.entries()) {
if (movement > 0) {
console.log(`Movement ${i + 1}: You deposited ${movement}`);
} else {
console.log(`Movement ${i + 1}: You withdrew ${Math.abs(movement)}`);
}
}

console.log('--------------forEach----------------');
movements.forEach(function (mov, i, arr) {
if (mov > 0) {
console.log(`Movement ${i + 1}: You deposited ${mov}`);
} else {
console.log(`Movement ${i + 1}: You withdrew ${Math.abs(mov)}`);
}
});

// 0: function(200)
// 1: function(450)
// 2: function(400)
// Map
const currencies = new Map([
['USD', 'United States dollar'],
['EUR', 'Euro'],
['GBP', 'Pound sterling'],
]);

currencies.forEach(function (value, key, map) {
console.log(`${key}: ${value}`);
});

// Set
const currenciesUnique = new Set(['USD', 'GBP', 'USD', 'EUR', 'EUR']);
console.log(currenciesUnique);

currenciesUnique.forEach(function (value, \_, map) {
console.log(`${value}: ${value}`);
});
\*/

/\*
////////////////////////
// challeng 1
const checkDogs = function (dogsJulia, dogKate) {
const dogsJuliaCorrected = dogsJulia.slice();

dogsJuliaCorrected.splice(0, 1);
dogsJuliaCorrected.splice(-2);

const dogs = dogsJuliaCorrected.concat(dogKate);

dogs.forEach((dog, i) => {
if (dog >= 3)
console.log(`Dog number ${i + 1} is an adult, and is ${dog} years old`);
else console.log(`Dog number ${i + 1} is still puppy 🐶`);
});
};
checkDogs([3, 5, 2, 12, 7], [4, 1, 15, 8, 3]);
const eurToUsd = 1.1;

const movementsUSD = movements.map(mov => mov _ eurToUsd);
console.log(movements);
console.log(movementsUSD);
_/

/\*
////////////////////////////
// Filter method
const deposits = movements.filter(mov => {
return mov > 0;
});
console.log(movements);
console.log(deposits);

const depositFor = [];
for (const mov of movements) {
if (mov > 0) depositFor.push(mov);
}
console.log(depositFor);

const withdrawals = movements.filter(mov => mov < 0);
console.log(withdrawals);
\*/

/\*
/////////////////////////////
// reduce method
console.log(movements);
const balance = movements.reduce((acc, cur, i, arr) => acc + cur, 0);
console.log(balance);

let balance2 = 0;
for (const mov of movements) {
balance2 += mov;
}
console.log(balance2);

// Maximum value
const max = movements.reduce((acc, mov) => {
if (acc > mov) return acc;
else return mov;
}, movements[0]);
console.log(max);
\*/

/_
////////////////////////////////////////////////
// challenge #2
const calAverageHumanAge = function (ages) {
const humanAges = ages.map(age => (age <= 2 ? 2 _ age : 16 + age \* 4));
const adults = humanAges.filter(age => age >= 18);
console.log(humanAges);
console.log(adults);

// const average = adults.reduce((acc, age) => acc + age, 0) / adults.length;
const average = adults.reduce(
(acc, age, i, arr) => acc + age / arr.length,
0
);

return average;
};
const age1 = calAverageHumanAge([5, 24, 1, 15, 8, 3]);
const age2 = calAverageHumanAge([16, 6, 10, 5, 6, 1, 4]);
console.log(age1);
console.log(age2);
\*/

/\*
//////////////////////////////
// chaining method
const eurToUsd = 1.1;

// PIPELINE
const totalDepositsUsd = movements
.filter(mov => mov > 0)
.map(mov => mov _ eurToUsd)
.reduce((acc, mov) => acc + mov, 0);
console.log(totalDepositsUsd);
_/

/\*
/////////////////////////////////////////////////////////
// find method
const firstWithdrawal = movements.find(mov => mov < 0);
console.log(movements);
console.log(firstWithdrawal);

const account = accounts.find(acc => acc.owner === 'Jessica Davis');
console.log(account);

// for (const acc of accounts) {
// if (acc.owner === 'Jessica Davis') {
// console.log(acc);
// }
// }
\*/

/\*
///////////////////////////////////////////
// The NEW findlast and findLastIndex Methods

console.log(movements);
const lastWithdrawal = movements.findLast(mov => mov < 0);
console.log(lastWithdrawal);

// ('Your latest large movement was X movements ago');

const latestLargeMovementIndex = movements.findLastIndex(
mov => Math.abs(mov) > 1000
);
console.log(latestLargeMovementIndex);
// ('Your latest large movement was X movements ago');

console.log(
`Your latest large movement was ${
    movements.length - latestLargeMovementIndex
  } movements ago`
);
\*/

/\*
////////////////////////////////////////////////////////
// some and every methods

console.log(movements);

// EQUALITY
console.log(movements.includes(-130));

// SOME: CONDITION
const anyDeposits = movements.some(mov => mov > 0);
console.log(anyDeposits);

// EVERY
console.log(movements.every(mov => mov > 0));
console.log(account4.movements.every(mov => mov > 0));

// Separate callback
const deposit = mov => mov > 0;
console.log(movements.some(deposit));
console.log(movements.every(deposit));
console.log(movements.filter(deposit));
\*/

/\*
///////////////////////////////////////////////////////
// flat and flatMap methods
const arr = [[[1, 2], 3], [[4, 5], 6], 7, 8];
console.log(arr.flatMap(mov => mov));

const accountMovements = accounts
.flatMap(acc => acc.movements)
.reduce((acc, mov) => acc + mov, 0);
console.log(accountMovements);
\*/

/\*
/////////////////////////////////////////////////////////////////
// sort method
// Strings
const owners = ['Jonas', 'Zach', 'Adam', 'Martha'];
console.log(owners.sort());

// Numbers
console.log(movements);

//
console.log(movements.sort((a, b) => {}));
\*/
