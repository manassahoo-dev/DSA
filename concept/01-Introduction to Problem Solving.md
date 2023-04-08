## count the number of factors of a given number

**Brute Force Approach:**
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
The above code iterates through all the numbers from 1 to the given number, checks if each number is a divisor of the given number, and increments a counter if it is. 
This approach has a time complexity of O(n), where n is the given number.

**Optimal Approach:**
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
The above code finds all the divisors of the given number by iterating through all the numbers from 1 to the square root of the given number. 
It then counts each divisor twice, except for perfect squares where the square root is only counted once. 
This approach has a time complexity of O(sqrt(n)), which is much faster than the brute force approach for large numbers.
