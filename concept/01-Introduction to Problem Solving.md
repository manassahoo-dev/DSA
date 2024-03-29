## Table of Contents

- [Count the number of factors](#Count-the-number-of-factors)
- [Check if Number is Prime](#check-if-Number-is-Prime)

## Count the number of factors

**Brute Force Approach:**

*   Iterate through all the numbers from 1 to the given number
*   For each number, check if it is a divisor of the given number
*   If it is a divisor, increment a counter
*   Return the final count of divisors as the number of factors

```java
public static int countFactorsBruteForce(int num) {
    int count = 0;
    for (int i = 1; i <= num; i++) {
        if (num % i == 0) {
            count++;
        }
    }
    return count;
}
```
Tme complexity: O(n), where n is the given number.

**Optimal Approach:**

*   Find the square root of the given number
*   Iterate through all the numbers from 1 to the square root of the given number
*   For each number, check if it is a divisor of the given number
*   If it is a divisor, count it twice (because each divisor has a complementary divisor)
*   If the given number is a perfect square, only count its square root once
*   Return the final count of divisors as the number of factors

```java
public static int countFactorsOptimal(int num) {
    int count = 0;
    for (int i = 1; i*i <= num; i++) {
        if (num % i == 0) {
            count += 2;
            // If the number is a perfect square, don't count its square root twice
            if (i * i == num) {
                count--;
            }
        }
    }
    return count;
}
```
Tme complexity: O(sqrt(n)), where n is the given number.

**Notes**
1. A factor of a number is a positive integer that divides the number without leaving a remainder. 
For example, the factors of 12 are 1, 2, 3, 4, 6, and 12.
1. Every number has at least two factors: 1 and itself.
1. If a number has an odd number of factors, it must be a perfect square. 
This is because the factors of a perfect square come in pairs, except for the square root itself, which is a factor only once.

## Check if Number is Prime
- If the given number N is less than or equal to 1, we return false because 1 and all numbers less than 1 are not prime.
- We loop through all the numbers from 2 to the square root of N.
- If N is divisible by any number i, where i is between 2 and the square root of N, then N is not a prime number and we return false.
- If the loop completes without finding any divisor of N, then N is a prime number and we return true.

```java
public static boolean isPrime(int N) {
    if (N <= 1) {
        return false;
    }
    for (int i = 2; i*i <= N; i++) {
        if (N % i == 0) {
            return false;
        }
    }
    return true;
}
```

More optimised solution

- The first thing it does is to check whether the number is less than or equal to 1. If it is, then it immediately returns false because 1 and any number less than 1 cannot be a prime number.
- If the number is greater than 1, it checks whether the number is less than or equal to 3. If it is, then it returns true because 2 and 3 are both prime numbers.
- If the number is greater than 3, it checks whether the number is divisible by 2 or 3. If it is, then it immediately returns false because any number that is divisible by 2 or 3 cannot be a prime number.
- If the number is not divisible by 2 or 3, it then checks whether the number is divisible by any other potential factor of the form 6k ± 1 (where k is a non-negative integer) up to the square root of the number. If the number is divisible by any of these potential factors, then it immediately returns false because the number is not a prime number.
- If the number is not divisible by any potential factors up to the square root of the number, then it returns true because the number is a prime number.
```java
public static boolean isPrime(int N) {
    if (N <= 1) {
        return false;
    } else if (N <= 3) {
        return true;
    } else if (N % 2 == 0 || N % 3 == 0) {
        return false;
    }
    for (int i = 5; i * i <= N; i += 6) {
        if (N % i == 0 || N % (i + 2) == 0) {
            return false;
        }
    }
    return true;
}
```
