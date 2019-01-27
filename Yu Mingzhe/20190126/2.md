## 1.Can you solve this equation?

题解：对于等式8*x^4 + 7*x^3 + 2*x^2 + 3*x + 6 == Y 找到在0到100中符合此等式的x值，abs(Y)<=1e10,精         				确到小数点后四位。思路是先观察等式左边，是一个单调递增的函数，找出最小值和最大值，当输入的Y值超出这一个范围的时候，直接输出结果：No solution！ 使用二分法找到符合要求的x值。

```java
import java.util.*;

public class Main{
	public static void main(String[]args) {
		Scanner in = new Scanner(System.in);
		int T = in.nextInt();
		int []a = new int[T];
		for(int i = 0;i < T;i++) {
			a[i] = in.nextInt();
		}
		int lowest =6;
		int highest = 807020306;
		for(int i = 0 ; i < T ; i++) {
			double lb = -1,ub = 100;
			if(a[i] > highest || a[i] < lowest) {
				System.out.println("No solution!");
				continue;
			}
			while (ub - lb > 1e-8) {
				double mid = (lb + ub)/2.0;
				double sum = 8*Math.pow(mid,4)+7*Math.pow(mid,3)+2*Math.pow(mid, 2)+3*mid+6;
				if(a[i] >= sum)
					lb = mid;
				else
					ub = mid;
			}
			System.out.printf("%.4f\n",ub);
		}
	}
}

```

