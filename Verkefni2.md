### 1
```javascript
let Person = function(pName, pPhone, pGsm) { return {name: pName, phone: pPhone, gsm: pGsm} };
let benedikt = new Person("Benedikt Aron S.", 1423567, 8854982);
console.log(benedikt.gsm);
```

### 2
```javascript
console.log(family.parents.fathers[1].name);
```

### 3
```javascript
let breakfast = {
    name: "The Lumberjack",
    price: 9.95,
    ingredients: ["eggs", "sausage", "toast", "hashbrowns", "pancakes"]
};

console.log(breakfast.name + " - " + breakfast.price.toString());
let ings = "";
for(let i = 0; i < breakfast.ingredients.length; i++){
    ings += ["", ", "][Number(!!i)] + breakfast.ingredients[i];
}
console.log(ings);
```

### 4
```javascript
printAccountSummary: function showAccountStat() {
    return "Welcome!\nYour balance is currently $" + this.balance.toString() + " and your interest rate is " + this.interestRatePercent.toString() + "%.";
}
```

### 5
```javascript
donuts.forEach(x => console.log(x.type + " donuts cost $" + x.cost.toString() + " each"));
```

### 6
```javascript
let Pizza = function makePizza(price=2195, size="Large", toppings=["Cheese", "Oregano"]) {
	return {price: price, size: size, toppings: toppings};
};

let margharita = new Pizza();
```
