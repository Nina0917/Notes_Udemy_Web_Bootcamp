## Javascript Alerts

rick click -> inspect -> console

- Now you can input js code drectly
- shift + enter: input multiple lines

rick click -> inspect -> Sources -> Snippets -> New snippet

- write js in a file

</br>

```javascript
alert("hello");
```

---

## Data Types

String

Numbers

Boolean : true/false

```javascript
typeof "hello";
typeof 123;
```

---

## Javascript Variables

```javascript
prompt("What is your name?");

var yourName = prompt("What is your name?");
```

clean console:

- CTRL+ k

</br></br>

```javascript
var name = "Some String";
// get String length
name.length;
```

```javascript
var name = "Some String";

var result = name.slice(0, 4); // result is some

var upperCaseStr = name.toUpperCase(); // 'SOME STRING'
```

- first index included, second is excluded.

</br></br>

```
6/4
> 1.5 (there is no integer in js)

6 % 4
> 2
```

```javascript
var x = 3;

var y = x++; // y=3

var y = ++x; // y=4
```

```javascript
function func_name(parameter1, parameter2) {
    code...
}

func_name(); // call function
```

- for parameters, no need to declare type

```javascript
const cars = ["Saab", "Volvo", "BMW"];

const cars = new Array("Saab", "Volvo", "BMW");

const cars = [];
cars[0] = "Saab";
cars[1] = "Volvo";
cars[2] = "BMW";

var size = cars.length;
var arrToStr = cars.toString();

var popElement = cars.pop();

var pushEle = "Honda";
cars.push(pushEle); // cars = ["Saab", "Volvo", "BMW", "Honda"];

cars.shift(); //remove the first element, don't use delete because it leaves undefined hole
```
