The Collatz Conjecture or 3x+1 problem can be summarized as follows:

Take any positive integer n. If n is even, divide n by 2 to get n / 2. If n is odd, multiply n by 3 and add 1 to get 3n + 1. Repeat the process indefinitely. The conjecture states that no matter which number you start with, you will always reach 1 eventually.

Given a number n, return the number of steps required to reach 1. 1. must be an Intiger , positive 2. if 1 step must be return 0 3. if step odd it want \*\* with 3 +1 4. if steps even /2

```

function steps(count: number): number {

  let val = count;
  console.log("val", val);

  for (let i = val; i === 1; i++) {

    if (val % 2 === 0) {
      val = val / 2
      console.log("val of even", val)
    } else {
      val = val * 3 + 1
      console.log("val of odd", val)
    }
  }

  return val

}

steps(12)
```

```

function steps(count: number): number {
  let val = count;
  console.log("val", val);

do{
    if (val % 2 === 0) {
      val = val / 2
      console.log("val of even", val)
    } else {
      val = val \* 3 + 1
      console.log("val of odd", val)
    }
  }while(val===1)

return 0
}

```

### Answer

```

export function steps(count: number): number | void {

let val = count;
let counting = 0
console.log("val", val);
if (val >0 && Number.isInteger(val)) {
do {
if (val % 2 === 0) {
val = val / 2
counting += 1
// console.log("val of even", val)
}else if(val ===1){
counting =0
} else {
val = val \* 3 + 1
counting += 1
// console.log("val of odd", val)
}
} while (val !== 1)
} else {
throw new Error("Only positive integers are allowed'")

}
console.log("counting", counting)
return counting
}

```

fibonacci series

```

```
