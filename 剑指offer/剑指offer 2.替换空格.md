因为新开了StringBuilder, 所以time: O(n） space:O(n);

```java
class Solution {
    public String replaceSpace(String s) {
        StringBuilder res = new StringBuilder();
        for(Character c : s.toCharArray())
        {
            if(c == ' ') res.append("%20");
            else res.append(c);
        }
        return res.toString();
    }
}

```

所以原地修改 space：O(1)是更好的选择

```java
class Solution {
    public static String replaceSpace(String s) {
        //边界条件
        int count = 0;
        int len = s.length();

        //统计空格,修改数组长度
        char[] originS = s.toCharArray();
        for (char c : originS) {
            if (c == ' ') {
                count++;
            }
        }
        char[] result = new char[len + 2 * count];

        //从后往前遍历修改
        for (int i = len - 1, j = result.length - 1;i >= 0;i--,j--){
           
            if (originS[i] != ' '){
                result[j] = originS[i];
            }else {
                result[j - 2] = '%';
                result[j - 1] = '2';
                result[j] = '0';
                j-=2;
            }
        }
        return new String(result);
    }
}
```

