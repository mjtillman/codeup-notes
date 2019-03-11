# JavaScript ES6
AKA ecmascript2015

#### Block Scoped Variables

- `let` and `const` v `var`
    - `let` limits a variable's scope within its container block
    - `const` cannot be redefined, also limited to block scope
---
#### Exponentiation Operator
You can now use `2 ** 8` instead of `Math.pow(2, 8)` for 2 ^ 8.

---

#### Template Literals (or Template Strings)
ES6 supports string interpolation, which is a more powerful way of concatenating strings.

Code:

    var apples = 4;
    var bananas = 3;
    console.log(`I have ${apples} apples`);
    console.log(`I have ${apples + bananas} fruit`);
    
Note: use of backticks (`)

Output:

    I have 4 apples
    I have 7 fruit
---
#### `for .. of`

    let animals = ['pelican', 'monitor', 'owl', 'salamander', 'newt', 'elk']
    
    for (animal of animals) {
        console.log(animal);
    }
   
Output

    pelican
    monitor
    owl
    salamander
    newt
    elk

Does not work on objects. Use arrays (which are iterable).

---
#### Arrow Functions

    const sayHello = function (name) {
        return 'Hello, ' + name + '!';
    }
is the same as

    const sayHello = (name) => 'Hello, ' + name + '!';
  

#### .map
    var incremented = numbers.map(function(n) {
        return n + 1;
    });
    
    console.log(incremented); // [2, 3, 4, 5, 6, 7, 8, 9, 10, 11]
#### .filter
    var numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

    var evens = numbers.filter(function(n) {
        return n % 2 === 0;
    });
    
    console.log(evens); // [2, 4, 6, 8, 10]
#### .reduce
    const numbers = [1, 2, 3, 4, 5];

    const sum = numbers.reduce((accumulation, currentNumber) => {
        return accumulation + currentNumber;
    }, 0);

#### hello
    function countWords(sentence) {
        const words = sentence.split(' '); // transform a sentence into an array of words
        const wordCountObject = words.reduce((wordCounts, word) => {
            if (typeof wordCounts[word] === 'undefined') {
                // if the word is not yet present in our object, set it's value to 1
                wordCounts[word] = 1;
            } else {
                // otherwise increment the existing count
                wordCounts[word] += 1;
            }
            return wordCounts;
        }, {}); // start with an empty object
        return wordCountObject;
    }
    
    countWords('Mary had a little lamb little lamb little lamb');
    // {Mary: 1, had: 1, a: 1, little: 3, lamb: 3}