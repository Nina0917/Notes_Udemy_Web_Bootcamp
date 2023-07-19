## Add Event

[reference](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)

```javascript
element.addEventListener(type, listener);
```

- type: case sensitive, example can be "click"
- listener: usually a function's name, **don't add parenthesis, or the function will be triggered immediately**

<br>

```javascript
function add(num1, num2) {
  return num1 + num2;
}

function multiply(num1, num2) {
  return num1 * num2;
}

function calculate(num1, num2, operator) {
  return operator(num1, num2);
}

// call function
calculate(1, 2, add); // will return 3
```

- pass function as paramater

<br>

```javascript
button.addEventListener("click", function () {
  alert("I got clicked");
});
```

- anonymous function

<br>

## How to debug in google chrome

```
debugger;
function_you_want_to_debug(param1, param2);
```

- click the third one (Step into next function call)

<br>

## JS Object

```javascript
function BellBoy(name, age, hasWorkPermit, languages) {
  this.name = name;
  this.age = age;
  this.hasWorkPermit = hasWorkPermit;
  this.languages = languages;
  // this is a function
  this.moveSuitcase = function () {
    alert("May I take your suitcase?");
  };
}

var bellBoy1 = new BellBoy("Timmy", 19, true, ["French", "English"]);
bellBoy1.moveSuitcase();
```

- constructor function: the first letter is capitalized
- bellBoy1 is a object

<br>

```javascript
document.addEventListener("keydown", function (event) {
  play_sound(event.key);
});
```

- keydown is the event type
- parameter "event" represents the keydown event

<br>

## Callbacks

- the above function "function (event)" is actually a callback function. It gets triggered when the event happened.

```javascript
setTimeout(myGreeting, 5000);
```

- myGreeting is a function name, can also be anonymous function.
