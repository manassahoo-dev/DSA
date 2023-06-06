```
|  Char  | Lowercase Decimal |  Uppercase Decimal |
|--------|------------------|--------------------|
|   a    |        97        |        65          |
|   b    |        98        |        66          |
|   c    |        99        |        67          |
|   d    |        100       |        68          |
|   e    |        101       |        69          |
|   f    |        102       |        70          |
|   g    |        103       |        71          |
|   h    |        104       |        72          |
|   i    |        105       |        73          |
|   j    |        106       |        74          |
|   k    |        107       |        75          |
|   l    |        108       |        76          |
|   m    |        109       |        77          |
|   n    |        110       |        78          |
|   o    |        111       |        79          |
|   p    |        112       |        80          |
|   q    |        113       |        81          |
|   r    |        114       |        82          |
|   s    |        115       |        83          |
|   t    |        116       |        84          |
|   u    |        117       |        85          |
|   v    |        118       |        86          |
|   w    |        119       |        87          |
|   x    |        120       |        88          |
|   y    |        121       |        89          |
|   z    |        122       |        90          |
```

**Given a character array toggle every character.**

```
Input: char[] chars = {'H', 'e', 'l', 'L', 'o', '!', 'W', 'o', 'r', 'l', 'D'};
Output: {'h', 'E', 'L', 'l', 'O', '!', 'w', 'O', 'R', 'L', 'd'}
```

```java
public void toggleCharacters(char[] chars) {
    for (int i = 0; i < chars.length; i++) {
        if (chars[i] >= 'A' && chars[i] <= 'Z') {
            // If the character is uppercase, toggle it to lowercase
            chars[i] = (char) (chars[i] + ('a' - 'A'));
        } else if (chars[i] >= 'a' && chars[i] <= 'z') {
            // If the character is lowercase, toggle it to uppercase
            chars[i] = (char) (chars[i] - ('a' - 'A'));
        }
        // Ignore non-alphabetic characters
    }
}
```

How many ways can we toggle a charcter?

1. Using the `Character` class methods:
```java
if (Character.isLowerCase(ch)) {
    ch = Character.toUpperCase(ch);
} else if (Character.isUpperCase(ch)) {
    ch = Character.toLowerCase(ch);
}
```
2. Using ASCII manipulation:
```java
if (ch >= 'A' && ch <= 'Z') {
    ch = (char) (ch + ('a' - 'A'));
} else if (ch >= 'a' && ch <= 'z') {
    ch = (char) (ch - ('a' - 'A'));
}
```
3. Using bitwise operations:
```
ch = (char) (ch ^ 32);
```


