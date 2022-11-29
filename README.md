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

Cairo is not a high-level language. It’s a low-level language with some powerful syntactic sugar to allow writing maintainable code. The advantage is that the Cairo language allows you to write very efficient code (you can write in the Cairo language almost anything you can run on the Cairo machine).

## Recursion instead of loops

The main reason for this is that `the Cairo memory is immutable` – once you write the value of a memory cell, this cell cannot change in the future. This is similar to pure functional languages, whose objects are also immutable, where you also have to replace loops with recursion for the same reason.

## The assert statement

```sh
assert <expr0> = <expr1>;
```

which we use below, allows us to do two things: verify that two values are the same (as you may have expected), but `also to assign a value to a memory cell`. For example, assert [ptr] = 0; will set the value of the memory cell at address ptr to 0 (if it was not set before).
    
## The primitive type - field element (felt)

In Cairo when you don’t specify a type of a variable/argument, its type is a `field element` (represented by the keyword `felt`). In the context of Cairo, when we say “a field element” we mean an integer in the range **-P/2 < x < P/2** where **P** is a very large (prime) number (currently it is a 252-bit number, which is a number with 76 decimal digits). 

The most important difference between integers and field elements is `division`: Division of field elements (and therefore division in Cairo) is not the integer division you have in many programming languages, where the integral part of the quotient is returned (so you get 7 / 3 = 2)
