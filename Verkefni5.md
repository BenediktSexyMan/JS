## 1. **DOM** (Walking the dom)
### 1
```html
<html>
<body>
  <div>Users:</div>
  <ul>
    <li>John</li>
    <li>Pete</li>
  </ul>
  <script>
	console.log(document.body.children[0]);
	console.log(document.body.children[1]);
	console.log(document.body.children[1].children[1]);
  </script>
</body>
</html>
```
### 2
1: true
2: false

### 3
```html
<html>
<head>
  <style>
    table {
      border-collapse: collapse;
    }

    td {
      border: 1px solid black;
      padding: 3px 5px;
    }
  </style>
</head>

<body>
  <table>
    <tr>
      <td>1:1</td>
      <td>2:1</td>
      <td>3:1</td>
      <td>4:1</td>
      <td>5:1</td>
    </tr>
    <tr>
      <td>1:2</td>
      <td>2:2</td>
      <td>3:2</td>
      <td>4:2</td>
      <td>5:2</td>
    </tr>
    <tr>
      <td>1:3</td>
      <td>2:3</td>
      <td>3:3</td>
      <td>4:3</td>
      <td>5:3</td>
    </tr>
    <tr>
      <td>1:4</td>
      <td>2:4</td>
      <td>3:4</td>
      <td>4:4</td>
      <td>5:4</td>
    </tr>
    <tr>
      <td>1:5</td>
      <td>2:5</td>
      <td>3:5</td>
      <td>4:5</td>
      <td>5:5</td>
    </tr>
  </table>
  <script>
    let table = document.body.firstElementChild.firstElementChild;
	for(var i = 0; i < table.children.length; i++) {	
		table.children[i].children[i].style.backgroundColor = 'red';
	}
    // your code
  </script>
</body>
</html>
```
## 2. **Events** (Browser events)
### 1
```html
<button onClick="hideText()">Click to hide text</button>
<div id="text">Text</div>
<script>
function hideText() {
	text.setAttribute("style", "display:none;");
}
</script>
```
### 2
```html
<button onClick="this.hidden=true;">Click me</button>
```
## 3. **Javascript30**
### Day 1
[Code](https://github.com/wesbos/JavaScript30/blob/master/01%20-%20JavaScript%20Drum%20Kit/index-FINISHED.html)
#### Comments
Line 12: Hann býr til sinn eiginn attribute sem heitir "data-key" til þess að halda utan um hvaða key þarf að ýta á til þess að hafa áhrif á það element.

Line 50: Hann setur data-key attribute-ið á audio tag-in sín.

Line 66: Hann sækir öll þau nauðsylegu fyrir keypress-ið, spilar hljóðin og bætir viðeigandi effect á element-ið (Ef takkin er réttur).

### Day 2
[Code](https://github.com/wesbos/JavaScript30/blob/master/02%20-%20JS%20and%20CSS%20Clock/index-FINISHED.html)
#### Comments
Line 77: Í falli sem hann kallar á hverji sekúndu (setTimeout) sækir hann allar hendurnar og stillir snúningin að viðeigandi gildi samkvæmt Date object-inu.

### Day 3
[Code](https://github.com/wesbos/JavaScript30/blob/master/03%20-%20CSS%20Variables/index-FINISHED.html)
#### Comments
Line 24: Hann býr til CSS breyturnar.

Line 65: Hann hlustar á change og mouseMove event-in og stillir breyturnar aftur útfrá nýju gildunum.
