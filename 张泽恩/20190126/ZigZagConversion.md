题解：对题理解错了，以为是要打印出Z字形的，然后就肝了两个小时终于做出来了，结果发现是以Z字形顺序排列最后输出是这样的

![1548527118268](C:\Users\Zeen\AppData\Roaming\Typora\typora-user-images\1548527118268.png)

![1548527134653](C:\Users\Zeen\AppData\Roaming\Typora\typora-user-images\1548527134653.png)

![1548527159092](C:\Users\Zeen\AppData\Roaming\Typora\typora-user-images\1548527159092.png)

按原来的题意写应该是比较简单的，以2*numRows-2作为循环数重新按顺序排列就完了

顺着我的思路写呢，就是把这个循环对应到数组里去然后打印数组，改代码改了有一个小时最后终于可以睡觉了（2:28了）把代码放出来吧

```java
public String convert(String s, int numRows) {
    int cycle=numRows*2-2;
    int numColumuns=numRows-1;
    int cyclenum=s.length()/cycle;
    char[][] array=new char[numRows][numColumuns*(cyclenum+1)];
    int positon=0;
    for (int i=0;i<=cyclenum;i++)
    {
        try {
            int row = 0, column = 0;
            do {
                array[row][i * numColumuns] = s.charAt(positon);
                row++;
                positon++;
            } while (row < array.length);
            row--;row--;
            column++;
            while (row > 0) {
                array[row][i * numColumuns + column] = s.charAt(positon);
                row--;column++;
                positon++;
            }
        }catch (Exception e){break;}
    }
    String result="";
    for (int i=0;i<array.length;i++)
    {
        for (int j=0;j<array[0].length;j++)
        {
            result+=array[i][j]+" ";
        }
        result+="\n";
    }
    return result;
}
```
