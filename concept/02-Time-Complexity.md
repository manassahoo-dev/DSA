```java
for (int i = 1; i <= n; i += 2) {
  print(i);
}
```
Time Complexity: `O(n)`

---
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

---
```java
for (int i = 1; i <= 100; i *= 2) {
  for (int j = 1; j <= n; j++) {
    print(i + j);
  }
}
```
Time Complexity: `O(n)`

---
