# Project Euler problem 1: Multiples of 3 and 5
[Project Euler problem 1](https://projecteuler.net/problem=1)
---
___
## Solution:
```fsharp
let ns : int seq = Seq.initInfinite id

let divisibleBy3Or5 (x : int) : bool = x % 3 = 0 || x % 5 = 0

let answer : int =
    ns
    |> Seq.filter divisibleBy3Or5
    |> Seq.takeWhile ((>) 1000)
    |> Seq.sum

printfn "answer = %i" answer
```

## Walkthrough:

#### Define a lazy sequence of all natural numbers:
```fsharp
let ns : int seq = Seq.initInfinite id
```

#### Define a predicate that tests wether a number is divisible by 3 or 5:
```fsharp
let divisibleBy3Or5 (x : int) : bool = x % 3 = 0 || x % 5 = 0
```

#### Answer:

Select all natural numbers that are divisible by 3 or 5
```fsharp
ns
|> Seq.filter divisibleBy3Or5
```

Then take the numbers that are smaller than 1000
```fsharp
|> Seq.takeWhile ((>) 1000)
```

Then sum the numbers
```fsharp
|> Seq.sum
```

#### Print out the answer:
```fsharp
printfn "answer = %i" answer
```
