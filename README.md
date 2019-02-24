## [Answers preview](https://htmlpreview.github.io/?https://github.com/wendellpereira/mean-coding-challenge/blob/master/challenge-answers.html)
  

# MarketVision Node Coding Challenge

Fork this repo with the answers and submit back!

## Challenge 1: Data Transformations

Take the following data of student test scores:

```js
[{
    name: 'Bobby',
    scores: [62,88,91,56,70]
},{
    name: 'Katie',
    scores: [93,70,66,85,89]
},{
    name: 'Michael',
    scores: [61,82,90,79,89]
},{
    name: 'Sarah',
    scores: [80,94,86,91,81]
}]
```

Write a ES6 function that will take that array of student data and return the following stats:
- The students' average, min, and max scores
- The student with the highest average score

## Challenge 2: Data Transformations II

Write a single ES6 expression to take `'a=4,b=15,c=42'` and convert it into an object.

## Challenge 3: Serialize Promises

Write a function `serialPromise()` that will execute promises in series.

Example promise function:
```js
function delayPromise(ms) {
    return new Promise(resolve => {
        setTimeout(() => {
            console.log('delayPromise(%d) done', ms);
            resolve(2*ms);
        }, ms);
    });
}
```
I should be able to run:

```js
console.time('serialPromise')
serialPromise(delayPromise, [100,200,700,1000]).then(() => console.timeEnd('serialPromise'));
```
Resulting in something like:
```
delayPromise(100) done
delayPromise(200) done
delayPromise(700) done
delayPromise(1000) done
serialPromise: 2002.3681640625ms
```

### Bonus
Have `serialPromise()` resolve to an array of the individual promise resolutions:

```js
serialPromise(delayPromise, [100,500,100,600]).then(console.log);
```

Would result in:
```js
[200, 1000, 200, 1200]
```

Because of the `resolve(2*ms)` in the `delayPromise()` function.
