# LeeCodeRecord
记录刷题过程,坚持!!!!!
371. 两整数之和
不使用运算符 + 和 -，计算两整数a 、b 之和。
示例 1:
输入: a = 1, b = 2
输出: 3
示例 2:
输入: a = -2, b = 3
输出: 1
```java
/*a= 3 b = 5  有关位运算的方法
	 * a^b  是异或操作    0 0 1 1
	 *                  0 1 0 1
	 *                  0 1 1 0   = 6  异或操作就是 1+1=0 0+0=0 1+0=1 0+1=1
	 * a&b << 1   是位与操作     0 0 1 1
	 *                         0 1 0 1
	 *                         0 0 0 1   = 1  异或操作就是 1+1=1 0+0=0 1+0=0 0+1=0
	 *                         同时左移一位  是0 0 1 0 = 2
	 * a|b 是位或操作                                        
	 * a >> 1 是右移操作 
	 * */
    public static int getSum(int a , int b) {
		int sum,carry; 
		sum = a^b;
		carry = (a & b) << 1;
		System.out.print(sum + "\n");
		System.out.print(carry + "\n");
		if (carry != 0) {
			return getSum(sum, carry);
		}
		return sum;
	}
	
	public static void main(String[] args) {
		// TODO Auto-generated method stub
        int sum=  getSum(3, -5);
        System.out.print(sum + "\n");
        int a = 3;
        int b = 5;
	}
```
输出结果:-2
本题当然在知道a,b都是整数的情况下,可以通过从1开始加,利用a++,b--的方式,当b--等于0时,也是可以解决的
