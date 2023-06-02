# 一、Scanner类概述
1. java.util.Scanner 是 Java5 的新特征，我们可以通过 Scanner 类来获取用户的输入。
2. 下面是创建 Scanner 对象的基本语法：
	``` Java
	Scanner s = new Scanner(System.in);
	```
3. 接下来我们演示一个最简单的数据输入，并通过 Scanner 类的 next() 与 nextLine() 方法获取输入的字符串，在读取前我们一般需要 使用 hasNext 与 hasNextLine 判断是否还有输入的数据：
# 二、使用 next 方法：
``` Java
import java.util.Scanner; 
public class ScannerDemo { 
	public static void main(String[] args) { 
		// 从键盘接收数据
		Scanner scan = new Scanner(System.in); 
		// next方式接收字符串 
		System.out.println("next方式接收："); 
		// 判断是否还有输入 
		if (scan.hasNext()) { 
			String str1 = scan.next(); 
			System.out.println("输入的数据为：" + str1); 
		} 
		scan.close(); 
	} 
}
```
# 三、使用 nextLine 方法：
``` Java
import java.util.Scanner; 
public class ScannerDemo { 
	public static void main(String[] args) {
		// 从键盘接收数据 
		Scanner scan = new Scanner(System.in); 
		// nextLine方式接收字符串 
		System.out.println("nextLine方式接收："); 
		// 判断是否还有输入 
		if (scan.hasNextLine()) { 
			String str2 = scan.nextLine(); 
			System.out.println("输入的数据为：" + str2); 
		} 
		scan.close(); 
	} 
}
```
# 四、next() 与 nextLine() 区别
1. next():
	- 1、一定要读取到有效字符后才可以结束输入。
	- 2、对输入有效字符之前遇到的空白，next() 方法会自动将其去掉。
	- 3、只有输入有效字符后才将其后面输入的空白作为分隔符或者结束符。
	- next() 不能得到带有空格的字符串。
2. nextLine()：
	- 1、以Enter为结束符,也就是说 nextLine()方法返回的是输入回车之前的所有字符。
	- 2、可以获得空白。
3. 如果要输入 int 或 float 类型的数据，在 Scanner 类中也有支持，但是在输入之前最好先使用 hasNextXxx() 方法进行验证，再使用 nextXxx() 来读取：
	``` Java
	import java.util.Scanner; 
	public class ScannerDemo { 
		public static void main(String[] args) { 
			// 从键盘接收数据
			Scanner scan = new Scanner(System.in);  
			int i = 0; 
			float f = 0.0f; 
			System.out.print("输入整数："); 
			if (scan.hasNextInt()) { 
				// 判断输入的是否是整数 
				i = scan.nextInt(); 
				// 接收整数 
				System.out.println("整数数据：" + i); 
			} else { 
				// 输入错误的信息 
				System.out.println("输入的不是整数！"); 
			} 
			System.out.print("输入小数："); 
			if (scan.hasNextFloat()) { 
				// 判断输入的是否是小数 
				f = scan.nextFloat(); 
				// 接收小数 
				System.out.println("小数数据：" + f); 
			} else { 
				// 输入错误的信息 
				System.out.println("输入的不是小数！"); 
			} 
			scan.close(); 
		} 
	}
	```

