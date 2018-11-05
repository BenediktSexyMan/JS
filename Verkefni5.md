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
