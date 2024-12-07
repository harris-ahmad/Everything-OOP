# Practice Questions Set

## Topic 1: 2D Arrays/Pointers

### Question 1: Hourglass Sum

Given a 6x6 2D Array, `arr`:

```txt
1 1 1 0 0 0
0 1 0 0 0 0
1 1 1 0 0 0
0 0 2 4 4 0
0 0 0 2 0 0
0 0 1 2 4 0
```

An hourglass in `A` is a subset of values with indices falling in this pattern in `arr`'s graphical representation:

```txt
a b c
  d
e f g
```

Write a function to calculate the hourglass sum for every hourglass in `arr`, then print the maximum hourglass sum.

<details>
<summary>Solution</summary>

```cpp
#include <iostream>
#include <limits.h> // For INT_MIN

#define ROW 6
#define COL 6

// Function to find maximum hourglass sum
int findMaxHourglassSum(int arr[ROW][COL]) {
    int max_sum = INT_MIN;
    for (int i = 0; i < ROW - 2; i++) {
        for (int j = 0; j < COL - 2; j++) {
            int sum = (arr[i][j] + arr[i][j+1] + arr[i][j+2]) +
                      (arr[i+1][j+1]) +
                      (arr[i+2][j] + arr[i+2][j+1] + arr[i+2][j+2]);
            max_sum = sum > max_sum ? sum : max_sum;
        }
    }
    return max_sum;
}
```

</details>

## Topic 2: Functions

### Question 2: Fibonacci Series

Write a function `fibonacci` that takes an integer `n` as input and returns the `n`th Fibonacci number. Use recursion to solve this problem.

<details>
<summary>Solution</summary>

```cpp
#include <iostream>

int fibonacci(int n) {
    if (n <= 1)
        return n;
    return fibonacci(n-1) + fibonacci(n-2);
}
```

</details>

## Topic 3: General Questions on Loops

### Question 3: Prime Numbers

Write a program to print all prime numbers in the range 1 to N. Use loops efficiently.

<details>
<summary>Solution</summary>

```cpp
#include <iostream>

void printPrimes(int N) {
    int i, j, isPrime;
    for (i = 2; i <= N; i++) {
        isPrime = 1;
        for (j = 2; j * j <= i; j++) {
            if (i % j == 0) {
                isPrime = 0;
                break;
            }
        }
        if (isPrime)
            cout << i << " ";
    }
}
```

</details>

## Additional Practice Questions

### 2D Arrays/Pointers

#### Question 4: Matrix Diagonal Sum

Write a function that takes a square matrix (2D array) as input and returns the sum of the two diagonals. For an odd-sized matrix, count the center element twice.

<details>
<summary>Solution</summary>

```cpp
#include <iostream>

int diagonalSum(int** matrix, int n) {
    int sum = 0;
    for (int i = 0; i < n; i++) {
        sum += matrix[i][i]; // Primary diagonal
        sum += matrix[i][n-i-1]; // Secondary diagonal
    }
    if (n % 2 == 1) {
        sum -= matrix[n/2][n/2]; // Subtract the center element once if n is odd
    }
    return sum;
}
```

</details>

### Functions

#### Question 5: Greatest Common Divisor (GCD)

Write a function `gcd` that takes two integers as input and returns their Greatest Common Divisor (GCD) using Euclid's algorithm.

<details>
<summary>Solution</summary>

```cpp
#include <iostream>

int gcd(int a, int b) {
    if (b == 0)
        return a;
    return gcd(b, a % b);
}
```

</details>

### General Questions on Loops

#### Question 6: Sum of Digits

Write a program that takes a positive integer and calculates the sum of its digits. Use a loop to solve this problem.

<details>
<summary>Solution</summary>

```cpp
#include <iostream>

int sumOfDigits(int n) {
    int sum = 0;
    while (n != 0) {
        sum += n % 10;
        n /= 10;
    }
    return sum;
}
```

</details>

#### Question 7: Pattern Printing

Write a program to print the following pattern for a given number `n`. For `n=5`, the pattern would be:

```txt
*
* *
* * *
* * * *
* * * * *
```

<details>
<summary>Solution</summary>

```cpp
#include <stdio.h>

void printPattern(int n) {
    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= i; j++) {
            cout << "* ";
        }
        cout << "\n";
    }
}
```

</details>
