```java
class Solution {
    public String reverseLeftWords(String s, int n) {
    StringBuilder sb = new StringBuilder(s.repeat(2));
    String res = sb.substring(n, n + s.length()).toString();
    return res;
    }
}
```

