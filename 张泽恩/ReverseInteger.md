题解：转化为字符串逆序输出，如果为负数则少输出一位即首位负号，再通过字符串拼接，如果溢出则catch异常返回0

```java
public int reverse(int x) {
    Integer a=x;
    String s=a.toString();
    String result="";
    if (s.charAt(0)=='-')
    {
        result+="-";
        for (int i=1;i<s.length();i++)
        {
            result+=s.charAt(s.length()-i);
        }
    }
    else 
        {
            for (int i=0;i<s.length();i++)
            {
                result+=s.charAt(s.length()-i-1);
            }
        }
    try {
        if (x>=0) return Integer.parseInt(result);
        else return Integer.parseInt(result);
        }catch (Exception e)
        {
            return 0;
        }
    }
```