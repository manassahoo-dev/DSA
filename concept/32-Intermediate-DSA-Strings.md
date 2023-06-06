**Given a character array toggle every character.**

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
