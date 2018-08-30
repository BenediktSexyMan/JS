### 1
Eru í rauninni sami hluturinn, merkja einhverja óskilgreind type eða gildi.

### 2
Use strict seigir þýðandanum að ekki reyna að laga kóðann minn heldur frekar kasta villu.

### 3
'let' býr til breytuna bara í local scope-inu meðan 'var' vistar breytuna í efstu _"global"_ breytuna (oftast window)

### 4
```javascript
/* Classic */
function add(a, b) {
	return a + b;
}

/* Function expression */
let add = function(a, b) {
	return a + b;
};

/* Arrow notation */
let add = (a, b) => a + b;
```

### 5
Býr til nafnlaust fall inn í tímabundnu scope og kallar á það.

### 6
Þýðandinn byrjar að færa allar falls skilgreiningar eins ofarlega og hægt er og breytist þá kóðinn svona:
```javascript
function foo(){
	function bar() {
		return 3;
	}
	function bar() {
		return 8;
	}
	return bar();
}
alert(foo()); 
```
Skrifar þá seinna 'bar' fallið yfir hitt fyrra áður en að er kallað á það.

### 7
for-in lykkja býr til breytu þar sem að hún breytist í hvert skipti sem að lykkjan keyrir sem fylgir þessari málskipan:
```javascript
for (ob in arr) {
	console.log(ob);
}
```
for-of lykkja hinsvegar býr til einskonar 'iterator' sem kallast (C++ og Python forritarar kannast vel við þá). Þessi iterator yield-ar nýtt gildi í hvert skipti sem er kallað á hann.
```javascript
let arr = [1, 5, 2, 9]
let iterator = arr[Symbol.iterator]
console.log( iterator.next().value ) /* 1 */
console.log( iterator.next().value ) /* 5 */
console.log( iterator.next().value ) /* 2 */
console.log( iterator.next().value ) /* 9 */
```

### 8
```javascript
var test = [12, 929, 11, 3, 199, 1000, 7, 1, 24, 37, 4,
    19, 300, 3775, 299, 36, 209, 148, 169, 299,
    6, 109, 20, 58, 139, 59, 3, 1, 139
];

test.forEach(i => {
  if(i%3===0) test[test.indexOf(i)] += 100;
});
```

### 9
```javascript
var bills = [50.23, 19.12, 34.01,
    100.11, 12.15, 9.90, 29.11, 12.99,
    10.00, 99.22, 102.20, 100.10, 6.77, 2.22
];

totals = bills.map(a => Number((a+(0.15*a)).toFixed(2)));

console.log(totals);
```

### 10
```javascript
var numbers = [
    [243, 12, 23, 12, 45, 45, 78, 66, 223, 3],
    [34, 2, 1, 553, 23, 4, 66, 23, 4, 55],
    [67, 56, 45, 553, 44, 55, 5, 428, 452, 3],
    [12, 31, 55, 445, 79, 44, 674, 224, 4, 21],
    [4, 2, 3, 52, 13, 51, 44, 1, 67, 5],
    [5, 65, 4, 5, 5, 6, 5, 43, 23, 4424],
    [74, 532, 6, 7, 35, 17, 89, 43, 43, 66],
    [53, 6, 89, 10, 23, 52, 111, 44, 109, 80],
    [67, 6, 53, 537, 2, 168, 16, 2, 1, 8],
    [76, 7, 9, 6, 3, 73, 77, 100, 56, 100]
];

for(let i = 0; i < numbers.length; i++) {
    for(let j = 0; j < numbers[i].length; j++)
    numbers[i][j] = ["odd", "even"][Number(numbers[i][j]%2===0)];
}

console.log(numbers);
```
