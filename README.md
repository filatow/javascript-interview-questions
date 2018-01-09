A list of helpful Javascript and front-end related questions you can use to interview potential candidates or yourself.

## Table of Contents

  1. [General Questions](#general-questions)
  1. [HTML Questions](#html-questions)
  1. [CSS Questions](#css-questions)
  1. [JS Questions](#js-questions)
  1. [Coding Snippets](#coding-questions)

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
* How would you approach fixing browser-specific styling issues?
* Describe pseudo-elements and discuss what they are used for.
* What's the difference between inline and inline-block?
* What's the difference between a relative, fixed, absolute and statically positioned element?

#### JS Questions:

* Explain event delegation
* Explain how `this` works in JavaScript
* What is NaN? What is its type? How can you reliably test if a value is equal to NaN?
* Explain how prototypal inheritance works
* What is a closure, and how/why would you use one?
* How do you organize your code? (module pattern, classical inheritance?)
* What's the difference between .call and .apply?
* Explain Function.prototype.bind.
* Why is extending built-in JavaScript objects not a good idea?
* Explain the difference between synchronous and asynchronous functions.
* What is the extent of your experience with Promises and/or their polyfills?
* What are the pros and cons of using Promises instead of callbacks?
* Explain the difference between mutable and immutable objects.
* What is event loop? What is the difference between call stack and task queue?
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
* What are the differences between Long-Polling, Websockets and Server-Sent Events?
* How do you clone an object?

#### Coding Snippets:

*1. What will the code below output to the console and why ?*
```javascript
console.log(4 + 3 + 2 + "1");
console.log(typeof typeof 1);
console.log(1 < 2 < 3);
console.log(3 > 2 > 1);
```

*2. What value is returned from the following statement?*
```javascript
"12345".split("").reverse().join("");
```

*3. What does the following code print?*
```javascript
var a = [1, 2, 3];
var b = [4, 5, 6];

Array.prototype.push.apply(a, b);
console.log(a); // ?
console.log(b); // ?
```

*4. Write a function*
```javascript
spacify('hello world') // outputs 'h e l l o  w o r l d'
```

*5. What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```

*6. What will the code below output to the console and why ?*
```javascript
var User = {
  count: 1,

  getCount: function() {
    return this.count;
  }
};

console.log(User.getCount());

var func = User.getCount;
console.log(func());
```

*7. In what order the console.log statements will be invoked?*
```javascript
(function() {
  console.log('1');

  setTimeout(() => {
    console.log('2');
  }, 0);

  console.log('3');

  setTimeout(() => {
    console.log('4');
  }, 0);

  console.log('5');
})();
```

*8. What does the following code print?*
```javascript
say('Python'); // ?

var phrase = 'Hello';

function say(name) {
  console.log(name + ", " + phrase);
}
```

*9. What does the following code print?*
```javascript
for (var i = 0; i < 10; i++) {
  setTimeout(function() {
    console.log(i); // ?
  }, 10);
}
```

*10. What does the following code print?*
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

*11. How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```

*12. Write an implementation of `isPalindrome` function*
```javascript
console.log(isPalindrome("level"));                   // logs 'true'
console.log(isPalindrome("levels"));                  // logs 'false'
console.log(isPalindrome("A car, a man, a maraca"));  // logs 'true'
```

*13. What does the following code print?*
```javascript
var module = {
  exports: {}
};

// If you require a module, it's basically wrapped in a function
(function(module, exports) {
  exports = function (n) { return n * 1000 };
}(module, module.exports))

console.log(module.exports);
```
