题解：写完虽然一遍过了，但是还需要优化，运行速度只超过了29.53的用户，用的方法比较笨，就是用switch分支分别对四位数的千位、百位、十位、个位去处理通过字符串拼接得到结果，对分支的处理比较简单粗暴也就是复制粘贴了三次，其实可以写个辅助方法来的，但是比较懒了，看评论区才想到其实可以利用数组的，明天有空了再看看吧，顺便明天写一下罗马数字转整数。

```java
public String intToRoman(int num) {
    String result="";
    char a='M';char b='D';char c='C';
    int carry;
    carry=num/1000;
    switch (carry)
    {
        case 0:
            break;
        case 3:
            result+="M";
        case 2:
            result+="M";
        case 1:
            result+="M";
            break;
    }
    carry=(num%1000)/100;
    switch (carry)
    {
        case 0:
            break;
        case 3:
            result+=c;
        case 2:
            result+=c;
        case 1:
            result+=c;
            break;
        case 4:
            result+=c;
        case 5:
            result+=b;
            break;
        case 6:
            result+=""+b+c;
            break;
        case 7:
            result+=""+b+c+c;
            break;
        case 8:
            result+=""+b+c+c+c;
            break;
        case 9:
            result+=c;
        case 10:
            result+=a;
            break;
    }
    carry=(num%100)/10;
    a='C';b='L';c='X';
    switch (carry)
    {
        case 0:
            break;
        case 3:
            result+=c;
        case 2:
            result+=c;
        case 1:
            result+=c;
            break;
        case 4:
            result+=c;
        case 5:
            result+=b;
            break;
        case 6:
            result+=""+b+c;
            break;
        case 7:
            result+=""+b+c+c;
            break;
        case 8:
            result+=""+b+c+c+c;
            break;
        case 9:
            result+=c;
        case 10:
            result+=a;
            break;
    }
    carry=num%10;
    a='X';b='V';c='I';
    switch (carry)
    {
        case 0:
            break;
        case 3:
            result+=c;
        case 2:
            result+=c;
        case 1:
            result+=c;
            break;
        case 4:
            result+=c;
        case 5:
            result+=b;
            break;
        case 6:
            result+=""+b+c;
            break;
        case 7:
            result+=""+b+c+c;
            break;
        case 8:
            result+=""+b+c+c+c;
            break;
        case 9:
            result+=c;
        case 10:
            result+=a;
            break;
    }
    return result;
}
```