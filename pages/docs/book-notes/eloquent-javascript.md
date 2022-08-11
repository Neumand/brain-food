# [Eloquent Javascript - Marijn Haverbeke](https://eloquentjavascript.net/)

![](https://eloquentjavascript.net/img/cover.jpg)

## Chapter 1: Values, Types, and Operators

> Bits are any kind of two-valued things, usually described as zeros and ones. Inside the computer, they take forms such as a high or low electrical charge, a strong or weak signal, or a shiny or dull spot on the surface of a CD. Any piece of discrete information can be reduced to a sequence of zeros and ones and thus represented in bits.

Modern computers have more than 30 billion bits in its working memory. We separate them into chunks - called **values** - so that we can represent the bits without getting confused.

JavaScript uses 64 bits. This translates into 2^64 different numbers (18 quintillion). Meaning, we can use 64-bit chunks freely without worrying about memory overflow.

## Chaper 2: Program Structure

An **expression** is a fragment of code that produces a value. A **statement** contains multiple expressions to produce a program. A program, therefore, is a list of statements. Statements are only useful when they change the the state of the world or the internal state of the machine in a way that affects subsequent statements.

**Chessboard Challenge**

The below program outputs a `size` x `size` chessboard. The sum of the inner and outer loop indices reflects the current position in the two-dimensional grid. The logic here is that if the modulus (`%`) of the current position is even we output a space. Otherwise, we output a `#`.

```javascript
function createChessboard(size = 8) {
  let board = ''

  for (let i = 0; i < size; i++) {
    board += '|'
    for (let j = 0; j < size; j++) {
      if ((j + i) % 2 === 0) {
        board += ' '
      } else {
        board += '#'
      }
    }
    board += '|'
    board += '\n'
  }

  console.log(board)
}

createChessboard()

/* Output:

|# # # # |
| # # # #|
|# # # # |
| # # # #|
|# # # # |
| # # # #|
|# # # # |
*/
```
