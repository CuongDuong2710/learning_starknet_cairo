[Cairo language](https://www.cairo-lang.org/docs/index.html)

## Your first function

```sh
// Computes the sum of the memory elements at addresses:
//   arr + 0, arr + 1, ..., arr + (size - 1).
func array_sum(arr: felt*, size) -> felt {
    if (size == 0) {
        return 0;
    }

    // size is not zero.
    let sum_of_rest = array_sum(arr=arr + 1, size=size - 1);
    return arr[0] + sum_of_rest;
}
```

## A low-level language with powerful syntactic sugar

## Recursion instead of loops

## The assert statement

> assert <expr0> = <expr1>;

which we use below, allows us to do two things: verify that two values are the same (as you may have expected), but `also to assign a value to a memory cell`. For example, assert [ptr] = 0; will set the value of the memory cell at address ptr to 0 (if it was not set before).