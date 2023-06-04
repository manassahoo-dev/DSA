**Modular Arithmetic:**
- `(a + b) % m = ((a % m) + (b % m)) % m`
- `(a - b) % m = ((a % m) - (b % m) + m) % m`
- `(a * b) % m = ((a % m) * (b % m)) % m`
- `(a^b) % m = ((a % m)^b) % m`

**Q.1 Q1. Power with Modules**

You are given A, B and C. Calculate the value of `(A ^ B) % C`
```java
public int solve(int A, int B, int C) {
  long result = 1;
  for (int i = 0; i < B; i++) {
    result = (result * A) % C;
  }
  return (int) result % C;
}
```
**Q2. Mod Array**

_Problem Description_

You are given a large number in the form of a array **A** of size **N** where each element denotes a digit of the number.
You are also given a number **B**. You have to find out the value of **A % B** and return it.

Input 1:

A = [1, 4, 3], B = 2
Output: 1 (143 is an odd number so 143 % 2 = 1)

Input 2:

A = [4, 3, 5, 3, 5, 3, 2, 1], B = 47
Output: 20 (43535321 % 47 = 20)

```java
public int solve(int[] A, int B) {
  int number = 0;
  int multiplier = 1;
  for (int i = A.length - 1; i >= 0; i--) {
    number = (number + A[i] * multiplier) % B;
    multiplier *= 10;
  }
  return number % B;
}
```
**Q3. Divisibility by 8**

Given a number A in the form of a string. Check if the number is divisible by eight or not.
Return 1 if it is divisible by eight else, return 0.

Input 1: A = "16"
Output 1: **1**

Input 2: A = "123"
Output 2: **0**

```java
public int solve(String A) {
  int n = A.length();
  int sum = 0;
  if (n == 1) {
    sum = A.charAt(0);
  } else if (n == 2) {
    sum = A.charAt(1) + 10 * A.charAt(0);
  } else {
    sum = A.charAt(n - 1) + 10 * A.charAt(n - 2) + 100 * A.charAt(n - 3);
  }
  return sum%8 == 0 ? 1 : 0;
}
```
