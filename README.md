A list of helpful Javascript and front-end related questions you can use to interview potential candidates or yourself.

## Table of Contents

  1. [General Questions](#general-questions)
  1. [HTML Questions](#html-questions)
  1. [CSS Questions](#css-questions)
  1. [JS Questions](#js-questions)
  1. [Network Questions](#network-questions)
  1. [Coding Snippets](#coding-questions)
  1. [Entry Tasks](#entry-tasks)
  1. [Entry Solutions](#entry-solutions)

#### General Questions:

* What did you learn yesterday/this week?
* Do you participate in conferences/meetups/opensource community? Any side projects?
* What is a recent technical challenge you experienced and how did you solve it?
* Talk about your preferred development environment.
* Which version control systems are you familiar with?
* If you could master one technology this year, what would it be?
* What does CORS stand for and what issue does it address?
* What is functional programming?

#### HTML Questions:

* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?

#### CSS Questions:

* What are the advantages/disadvantages of using CSS preprocessors?

#### JS Questions:

* Explain event delegation
* Explain how `this` works in JavaScript
* What is a closure, and how/why would you use one?
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`. What needs to be changed to properly make it an IIFE?
* What's the difference between .call and .apply?
* Explain Function.prototype.bind.
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
* Explain the difference between synchronous and asynchronous functions.
* What is the extent of your experience with Promises and/or their polyfills?
* What are the pros and cons of using Promises instead of callbacks?
* Explain the difference between mutable and immutable objects.
* What is event loop? What is the difference between call stack and task queue?

#### Network Questions:

* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
* What are the differences between Long-Polling, Websockets and Server-Sent Events?

#### Coding Snippets:

*What will the code below output to the console and why ?*
```javascript
console.log(1 +  "2" + "2");
console.log(1 +  +"2" + "2");
console.log(1 +  -"1" + "2");
console.log(+"1" +  "1" + "2");
console.log( "A" - "B" + "2");
console.log( "A" - "B" + 2);
```

*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```

*Question: What value is returned from the following statement?*
```javascript
"12345".split("").reverse().join("");
```

*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```

*Question: In what order the console.log statements will be invoked?*
```javascript
(function() {

  console.log('1');

  setTimeout(function cb() {
    console.log('2');
  });

  console.log('3');

  setTimeout(function cb1() {
    console.log('4');
  }, 0);

  console.log('5');

})();
```

*Question: What does the following code print?*
```javascript
say('Python'); // ?

var phrase = 'Hello';

function say(name) {
  console.log(name + ", " + phrase);
}
```

*Question: What does the following code print?*
```javascript
for (var i = 0; i < 10; i++) {
  setTimeout(function() {
    console.log(i); // ?
  }, 10);
}
```

*Question: What does the following code print?*
```javascript
var num = 10,
    obj1 = {
      value: "first value"
    },
    obj2 = {
     value: "second value"
    },
    obj3 = obj2;

function change(num, obj1, obj2) {
    num = num * 10;
    obj1 = obj2;
    obj2.value = "new value";
}

change(num, obj1, obj2);

console.log(num); // ?
console.log(obj1.value); // ?
console.log(obj2.value); // ?
console.log(obj3.value); // ?
```

*Question: What does the following code print?*
```javascript
var a = [1, 2, 3];
var b = [4, 5, 6];

Array.prototype.push.apply(a, b);
console.log(a); // ?
console.log(b); // ?
```

*Question: How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```

*Write an implementation of `isPalindrome` function*
```javascript
console.log(isPalindrome("level"));                   // logs 'true'
console.log(isPalindrome("levels"));                  // logs 'false'
console.log(isPalindrome("A car, a man, a maraca"));  // logs 'true'
```

*What gets logged to the console when the user clicks on “Button 4” and why?*
```javascript
for (var i = 0; i < 5; i++) {
  var btn = document.createElement('button');
  btn.appendChild(document.createTextNode('Button ' + i));
  btn.addEventListener('click', function(){ console.log(i); });
  document.body.appendChild(btn);
}
```

*Create a function that, given a DOM Element on the page, will visit the element itself and all of its descendents (not just its immediate children). For each element visited, the function should pass that element to a provided callback function.*
```javascript

// The arguments to the function should be:
//
// a DOM element
// a callback function (that takes a DOM element as its argument)
function Traverse(p_element,p_callback) { ... }
```

#### Entry Tasks:

*1. Write an implementation of `partialApply` function*
```javascript
it('partialApply() should partially apply functions', () => {
  const add = (a, b) => a + b;
  const add10 = partialApply(add, 10);

  const actual = add10(5);
  const expected = 15;

  expect(actual).to.equal(expected);
});
```
[Open solution](#entry-solution-1)

*2. Write an implementation of `checkBrackets` function*
```javascript
it('checkBrackets() should partially apply functions', () => {
  const truthy = "function test(){ alert(); }";
  const firstFalsy = "function test)({ alert(); }";
  const secondFalsy = "[{()(}]";

  expect(checkBrackets(truthy)).to.equal(true));
  expect(checkBrackets(firstFalsy)).to.equal(false));
  expect(checkBrackets(secondFalsy)).to.equal(false));
});
```
[Open solution](#entry-solution-2)

#### Entry Solutions:
##### Entry Solution 1:
```javascript
function partialApply(fn) {
  const slice = Array.prototype.slice;
  const args = slice.call(arguments, 1);

  return function() {
    return fn.apply(this, args.concat(slice.call(arguments, 0)));
  };
}
```

##### Entry Solution 2:
```javascript
const checkBrackets = (str) => {
  const openingBrackets = {
    '{': '}',
    '[': ']',
    '(': ')',
  };

  const closingBrackets = {
    '}': '{',
    ')': '(',
    ']': '[',
  };

  const stack = [];
  for (var i = 0; i < str.length; i++) {
    const symbol = str[i];
    if (openingBrackets[symbol]) {
      stack.push(openingBrackets[symbol]);
    } else if (stack.length && stack[stack.length - 1] === symbol) {
      stack.pop();
    } else if (closingBrackets[symbol]) {
      return false;
    }
  }
  return stack.length === 0;
};
```
