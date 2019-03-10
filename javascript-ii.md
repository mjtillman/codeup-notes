# JavaScript ES6
AKA ecmascript2015

- **Block Scoped Variables**

- `let` and `const` v `var`
    - `let` limits variable scope within its container block
    - `const` cannot be redefined, also limited to block scope

- **Exponentiation Operator**

    - You can now use `2 ** 8` instead of `Math.pow(2, 8)` for 2 ^ 8.

- **Template Literals (or Template Strings)**

ES6 supports string interpolation, which is a more powerful way of concatenating
strings.

var apples = 4;
var bananas = 3;
console.log(`I have ${apples} apples`);
console.log(`I have ${apples + bananas} fruit`);

- **`for .. of`**

# Arrow Functions
    const sayHello = function (name) {
        return 'Hello, ' + name + '!';
    }
is the same as

    const sayHello = (name) => 'Hello, ' + name + '!';
  
