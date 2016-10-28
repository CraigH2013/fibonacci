# fibonacci-fast

A Node.js module for quickly computing and searching Fibonacci numbers

## Usage

### Fibonacci number at given index

Find the 3000th Fibonacci number and display the amount of time it took:

```javascript
var fibonacci = require('fibonacci-fast');
var result = fibonacci.get(3000);

console.log({
  number: result.number.toFixed(),
  ms: result.ms
});
```

Result:

```javascript
{ number: '410615886307971260333568378719267105220125108637369252408885430926905584274113403731330491660850044560830036835706942274588569362145476502674373045446852160486606292497360503469773453733196887405847255290082049086907512622059054542195889758031109222670849274793859539133318371244795543147611073276240066737934085191731810993201706776838934766764778739502174470268627820918553842225858306408301661862900358266857238210235802504351951472997919676524004784236376453347268364152648346245840573214241419937917242918602639810097866942392015404620153818671425739835074851396421139982713640679581178458198658692285968043243656709796000',
  ms: 23 }
```

### An index for a given Fibonacci number

Find the index for the Fibonacci number 24157817:

```javascript
var fibonacci = require('fibonacci-fast');
var result = fibonacci.find(24157817);

console.log({
  index: result.index,
  ms: result.ms
});
```

Result:

```javascript
{ index: 37, ms: 4 }
```

### Create a Fibonacci iterator

Traverse through the sequence starting at a given index. If no index is given, the sequence will start at index 0.

```javascript
var fibonacci = require('fibonacci-fast');

var fibs = fibonacci.iterator(100);

for (var i = 0; i < 3; i++) {
  console.log(fibs.next().value.number.toString());
}
```

Result:

```javascript
354224848179261915075
573147844013817084101
927372692193078999176
```

## Fast Doubling Algorithm

This module utilizes the [fast doubling algorithm](https://www.nayuki.io/page/fast-fibonacci-algorithms) which allows for much faster calculations of Fibonacci numbers than the traditional recurrence method.

The fast doubling algorithm takes Θ(log _n_) operations, and the recurrence algorithm takes Θ(_n_).

## Big.js

The fibonacci-fast module utilizes the [big.js library](https://www.npmjs.com/package/big.js) to handle large numbers.
