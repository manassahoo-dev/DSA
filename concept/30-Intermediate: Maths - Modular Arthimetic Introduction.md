**Modular Arithmetic:**
- `(a + b) % m = ((a % m) + (b % m)) % m`
- `(a - b) % m = ((a % m) - (b % m) + m) % m`
- `(a * b) % m = ((a % m) * (b % m)) % m`
- `(a^b) % m = ((a % m)^b) % m`

Q.1 You are given A, B and C. Calculate the value of `(A ^ B) % C`
```java
public int solve(int A, int B, int C) {
  long result = 1;
  for (int i = 0; i < B; i++) {
    result = (result * A) % C;
  }
  return (int) result % C;
}
```
