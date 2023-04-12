**1.**
```java
for (int i = 1; i <= n; i += 2) {
  print(i);
}
```
Time Complexity: `O(n)`

---
**2.**
```java
void solve(int N, int M) {
  for (int i = 1; i <= N; i++) {
    if (N % i == 0)
      print(i);
  }

  for (int i = 1; i <= M; i++) {
    if (M % i == 0)
      print(i);
  }
}
```
Time Complexity: `O(N+M)`

---
**3.**
```java
int func(int n) {
  int s = 0;
  for (int i = 1; i <= 100; i++) {
    s = s + i;
  }
  return s;
}
```
Time Complexity: `O(1)`

---
**4.**
```java
int func(int n) {
  int s = 0;
  for (int i = 0; i < n; i = i * 2) {
    s = s + i;
  }
  return s;
}
```
Time Complexity: `O(∞)`
- The loop is an infinite loop as the value of i initialized with 0 doesn't change on multiplication by 2

---
**5.**
```java
for (int i = 1; i <= 100; i *= 2) {
  for (int j = 1; j <= n; j++) {
    print(i + j);
  }
}
```
Time Complexity: `O(n)`
- The outer loop runs for a constant time. 
- The inner loop runs n times.
- Thus the answer is O(n)

---
