### 1
Object Oriented Programming (OOB) er forritunar skilmáli sem segir að maður getur verið með Objects og hver Object er independant/sovereign. Prototype forritun er mjög svipuð í því að sá skilmáli segir að það séu til Objects en hvenær sem hægt er þá í stað þess að búa til nýtt Object þá er frekar búið til Prototype Object sem að bendir til á annan Object sem var fyrirfram til.

### 2
#### A
Þegar maður sleppir prototype þá verður fallið getIsbn hluti af Book Object-inu.
#### B
Þegar mapur sleppir ekki prototype þá verður fallið getIsbn hluti af prototype Object-inu í Book Object-inu.

### 3
Kóðinn sem að gerir skrítið stuff
```javascript
function SpaceShip(name, life=10, speed=10) {
	this.name  = name;
	this.life  = life;
	this.speed = speed;
}

let ship0 = new SpaceShip("ISS Siren");
let ship1 = new SpaceShip("ISS Contour", 5, 15);
let ship2 = new SpaceShip("ISS Warpspeed", 15, 5);

SpaceShip.prototype.fly = function SpaceShipFly() {
	this.speed++;
};

function Vessel(name, parent, life=5, speed=5) {
	this.name    = name;
	this.parent  = parent;
	this.life    = life;
	this.speed   = speed;
	this.fly     = SpaceShip.prototype.fly;
	this.setLife = function VesselSetLife() {
		this.life++;
	};
}

let ship2_Vessel0 = new Vessel("ISS Warpspeed Vessel 000", ship2, 5, 5);
let ship2_Vessel1 = new Vessel("ISS Warpspeed Vessel 001", ship2, 4, 5);
```

Kóðinn sem gerir ekki skrítið stuff

```javascript
function SpaceShip(name, life=10, speed=10) {
	this.name  = name;
	this.life  = life;
	this.speed = speed;
}

let ship0 = new SpaceShip("ISS Siren");
let ship1 = new SpaceShip("ISS Contour", 5, 15);
let ship2 = new SpaceShip("ISS Warpspeed", 15, 5);

SpaceShip.prototype.fly = function SpaceShipFly() {
	this.speed++;
};

function Vessel(name, parent, life=5, speed=5) {
	this.name    = name;
	this.parent  = parent;
	this.life    = life;
	this.speed   = speed;
	this.setLife = function VesselSetLife() {
		this.life++;
	};
}

Vessel.prototype = SpaceShip;

let ship2_Vessel0 = new Vessel("ISS Warpspeed Vessel 000", ship2, 5, 5);
let ship2_Vessel1 = new Vessel("ISS Warpspeed Vessel 001", ship2, 4, 5);
```

### 4

```javascript
class SpaceShip {
	constructor(name, life=10, speed=10) {
		this.name = name;
		this.life = life;
		this.speed = speed;
	}
	
	fly() {
		this.speed++;
	}
}

let ship0 = new SpaceShip("ISS Siren");
let ship1 = new SpaceShip("ISS Contour", 5, 15);
let ship2 = new SpaceShip("ISS Warpspeed", 15, 5);

class Vessel extends SpaceShip {
	constructor(name, parent, life=5, speed=5) {
		super(name, life, speed);
		this.parent = parent;
	}
	
	setLife() {
		this.life++;
	}
}

let ship2_vessel0 = new Vessel("ISS Warpspeed Vessel 000", ship2, 5, 5);
let ship2_vessel1 = new Vessel("ISS Warpspeed Vessel 001", ship2, 4, 5);
```
