# 一、异常处理概述
1. 异常是程序中的一些错误，但并不是所有的错误都是异常的，而错误有时是可以避免的。
2. 比方说，你的代码少了一个分号，那么运行出来结果是提示是错误的java.lang.Error；如果你用System.out.println(11/0)，那么你是因为你用0做了除数，会抛出 java.lang.ArithmeticException 的异常。
3. 异常发生的原因有很多，通常包含以下几大类：
	- 用户输入了非法数据。
	- 要打开的文件不存在。
	- 网络通信时连接中断，或者JVM内存溢出。
4. 这些异常有的是因为用户错误引起的，有的是程序错误引起的，还有其他一些是因为物理错误引起的。
5. 要理解Java异常处理是如何工作的，你需要掌握以下三种类型的异常：
	- 检测性异常：最典型的检测性异常是用户错误或问题引发的异常，这是程序人员无法预见的。例如要打开一一个不存在的文件时，一个异常就产生了，这些异常在编辑时不能被简单地忽略。
	- 运行时间异常：运行时间异常是可能被程序人员避免的异常。与检查性异常相对，运行时间异常可以在编译时被忽悠。
	- 错误：错误不是异常，而是脱离程序控制人员的问题。错误在代号中经常被忽略。例如，当栈溢出时，一个错误就发生了，他们在编着也查不到的。
# 二、Exception 类的次
1. 所有的异常类都是从java.lang.Exception类继承的子类。
2. Exception类是Throwable类的子类。除去Exception类之外，Throwable还有一个子类Error。
3. Java 程序通常不捕捉错误。错误通常发生在严重故障时，它们在 Java 程序处理的范围之外。
4. Error 使用来指示运行时环境发生的错误。
5. 例如，JVM 内存溢出。一般地，程序不会从错误中恢复。
6. 异常类有两个主要的子类：IOException类和RuntimeException类。
# 三、Java 内部设置异常类
1. Java语言定义了一些异常类在java.lang标准包中。
2. 标准运行时异常类的子类是最常见的异常类。由java.lang包是默认加载到所有的Java程序的，所以大部分从运行时异常类继承而来的异常都可以直接使用。
3. Java 根据各个类库也确定了一些其他的异常，下面的表中列出了 Java 的非检查性异常。

|**异常**|**描述**|
|---|---|
|算术异常|当出现异常的运算时，抛出这种异常。|
|ArrayIndexOutOfBoundsException异常|用非法索引访问分组时抛出的异常。|
|数组存储异常|尝试将错误类型的对象存储到一个对象数据组时抛出的异常。|
|类转换异常|当试图将对象强制转为不是实例的子类时，抛出该异常。|
|非法参数异常|抛出的异常表明向方法传递了一个不合法或不正确的参数。|
|非法监控状态异常|抛出的异常表明某线程序已经尝试图等对象的监控器，或者尝试图通了解其他正确在等对象的监控器和本体没有指定监视器的线路。|
|非法状态异常|在非法或不适当的时间调整使用法时生产的信号。换句话说，即Java环境或Java应用程序程序没有处于请操作所需的合适当前状态下。|
|非法线程状态异常|线路程序没有处用于请求操作所需的适当状态时抛出的异常。|
|索引越界异常|指示某个排序顺序（例如对数字组、字符串或向量的排序）超出范围时抛出。|
|NegativeArraySizeException异常|如果应用程序尝试创建大小为负的数字组，则抛出该异常。|
|空指针异常|当应用程序试图在需要对象的地方使用`null`时，抛出该异常|
|数字格式异常|当应用程序测试将字符串转换成一种数值类型，但应该字符串不能转换为合适的格式时，抛出该异常。|
|安全异常|由安全管理器抛出的异常，表明存在安全违规。|
|StringIndexOutOfBoundsException异常|这种异常通常由`String`方法抛出，指示索引者或为负者，或超出字串的大小。|
|不支持的操作异常|当不支持请求的操作时，抛出该异常。|
4. 下面的表中列出了 Java 定义在 java.lang 包中的检查性异常类。

|**异常**|**描述**|
|---|---|
|ClassNotFoundException异常|应用程序测试图加载类时，找不到相应的类，抛出该异常。|
|克隆不支持异常|当调用`Object`类中的`clone`方法克隆对象，但该对象的类无法实 现`Cloneable`接口时，抛出该异常。|
|非法访问异常|拒绝访问一个类的时候，抛出该异常。|
|实例化异常|当试图使用`Class`类中的`newInstance`方法创建一个类的实例，而指定的类对象因为是一个接口或者是一个抽象类而无法实例化时，抛出该异常。|
|中断异常|一条线路被另一条线路中断，抛出该异常。|
|NoSuchFieldException异常|请要求的量不存在|
|NoSuchMethodException异常|请要求的方法不存在|
# 四、异常方法
1. 下面的列表是 Throwable 类的主要方法：

|**序号**|**方法及说明**|
|---|---|
|1个|**public String getMessage()**  <br>返回关于发生的异常的详细信息。这个消息在Throwable类的构造函数中初化了。|
|2个|**public Throwable getCause()**  <br>返回一个Throwable对象代表异常原因。|
|3个|**public String toString()**  <br>返回此 Throwable 的简短描述。|
|4个|**public void printStackTrace()**  <br>将此Throwable 及其回源打印到标准错误流。。|
|5个|**public StackTraceElement [] getStackTrace()**  <br>返回一个包含栈层次的数组。下标为0的元素代表栈顶，最后一个元素代表方法调用栈栈的栈底。|
|6个|**public Throwable fillInStackTrace()**  <br>用当前的调用栈层填充Throwable对栈层次，添加到栈层任何先消息中。|
# 五、捕捉异常
1. 使用 try 和 catch 关键字可以捕获异常。try/catch 代码块放在异常可能发生的地方。
2. try/catch代码块中的代码称为保护代码，使用try/catch的语法如下：
	``` Java
	try { // 程序代码} catch ( ExceptionName e1 ) { //Catch 块}
	```
3. Catch 语言包含要捕捉异常类型的声音。当保护代码块中出现一个异常时，尝试后面的 catch 块就会被检查。
4. 如果发生的异常包包含在catch块中，异常会被传递到该catch块，这和传递一个参数到方法是一样的。
5. 例
	``` Java
	import java.io.*; 
	public class ExcepTest{ 
		public static void main(String args[]){ 
			try{ int a[] = new int[2]; 
				System.out.println("Access element three :" + a[3]);
			}catch(ArrayIndexOutOfBoundsException e){ 
				System.out.println("Exception thrown :" + e); 
			} 
			System.out.println("Out of the block"); 
		} 
	}
	```
# 六、多重捕获块
1. 一个 try 代码块后面跟随多个 catch 代码块的情况就叫多重捕获。
2. 多重捕获块的语法如下所示：
	``` Java
	try{ 
		// 程序代码 
	}catch(异常类型1 异常的变量名1){ 
		// 程序代码 
	}catch(异常类型2 异常的变量名2){ 
		// 程序代码 
	}catch(异常类型3 异常的变量名3){
		// 程序代码 
	}
	```
	- 上面的代码段包含了 3 个 catch块。
	- 可以在 try 语句后面添加任意数量的 catch 块。
	- 如果保护代码中发生异常，异常被抛给第一个 catch 块。
	- 如果抛出异常的数据类型与 ExceptionType1 匹配，它在这里就会被捕获。
	- 如果不匹配，它会被传递给第二个 catch 块。
3. 例
	``` Java
	try { 
		file = new FileInputStream(fileName); 
		x = (byte) file.read(); 
	} catch(FileNotFoundException f) {
		f.printStackTrace(); 
		return -1; 
	} catch(IOException i) { 
		i.printStackTrace(); 
		return -1; 
	}
	```
# 七、throws/throw 关键字
1. 在Java中， throw 和 throws 关键字是用于处理异常的。
2. throw 关键字用于在代码中抛出异常，而 throws 关键字用于在方法声明中指定可能会抛出的异常类型。
## （一）throw 关键字
1. throw 关键字用于在当前方法中抛出一个异常。
2. 通常情况下，当代码执行到某个条件下无法继续正常执行时，可以使用 throw 关键字抛出异常，以告知调用者当前代码的执行状态。
3. 例如，下面的代码中，在方法中判断 num 是否小于 0，如果是，则抛出一个 IllegalArgumentException 异常。
	``` Java
	public void checkNumber(int num) {  
	  if (num < 0) {  
	    throw new IllegalArgumentException("Number must be positive");  
	  }  
	}  
	```
## （二）throws 关键字
1. throws 关键字用于在方法声明中指定该方法可能抛出的异常。当方法内部抛出指定类型的异常时，该异常会被传递给调用该方法的代码，并在该代码中处理异常。
2. 例如，下面的代码中，当 readFile 方法内部发生 IOException 异常时，会将该异常传递给调用该方法的代码。在调用该方法的代码中，必须捕获或声明处理 IOException 异常。
	``` Java
	public void readFile(String filePath) throws IOException {  
		BufferedReader reader = new BufferedReader(new FileReader(filePath));  
		String line = reader.readLine();  
		while (line != null) {  
		    System.out.println(line);  
		    line = reader.readLine();  
		 }  
		 reader.close();  
	}  
	```
3. 一个方法可以声明抛出多个异常，多个异常之间用逗号隔开。
4. 例如，下面的方法声明抛出 RemoteException 和 InsufficientFundsException：
	``` Java
	import java.io.*; 
	public class className { 
		public void withdraw(double amount) throws RemoteException, InsufficientFundsException { 
			// Method implementation 
		} 
		//Remainder of class definition 
	}
	```
## （三）finally关键字
1. finally 关键字用来创建在 try 代码块后面执行的代码块。
2. 无论是否发生异常，finally 代码块中的代码总会被执行。
3. 在 finally 代码块中，可以运行清理类型等收尾善后性质的语句。
4. finally 代码块出现在 catch 代码块最后，语法如下：
	``` Java
	try{ 
		// 程序代码 
	}catch(异常类型1 异常的变量名1){ 
		// 程序代码 
	}catch(异常类型2 异常的变量名2){ 
		// 程序代码 
	}finally{ 
		// 程序代码 
	}
	```
5. 例
	``` Java
	public class ExcepTest{ 
		public static void main(String args[]){ 
			int a[] = new int[2]; 
			try{ 
				System.out.println("Access element three :" + a[3]);
			}catch(ArrayIndexOutOfBoundsException e){ 
				System.out.println("Exception thrown :" + e); 
			} finally{ 
				a[0] = 6; 
				System.out.println("First element value: " +a[0]); 
				System.out.println("The finally statement is executed"); 
			} 
		} 
	}
	```
6. 注意下面事项：
	- catch 不能独立于 try 存在。
	- 在 try/catch 后面添加 finally 块并非强制性要求的。
	- try 代码后不能既没 catch 块也没 finally 块。
	- try, catch, finally 块之间不能添加任何代码。
## （四）try-with-resources
1. JDK7 之后，Java 新增的 try-with-resource 语法糖来打开资源，并且可以在语句执行完毕后确保每个资源都被自动关闭 。
2. try-with-resources 是一种异常处理机制，它可以简化资源管理代码的编写。
3. JDK7 之前所有被打开的系统资源，比如流、文件或者 Socket 连接等，都需要被开发者手动关闭，否则将会造成资源泄露。
	``` Java
	try (resource declaration) {
	  // 使用的资源
	} catch (ExceptionType e1) {
	  // 异常块
	}
	```
4. 以上的语法中 try 用于声明和实例化资源，catch 用于处理关闭资源时可能引发的所有异常。
5. 注意：try-with-resources 语句关闭所有实现 AutoCloseable 接口的资源。
6. 例
	``` Java
	import java.io.*;  
  
	public class RunoobTest {  
	    public static void main(String[] args) {  
	    String line;  
	        try(BufferedReader br = new BufferedReader(new FileReader("test.txt"))) {  
	            while ((line = br.readLine()) != null) {  
	                System.out.println("Line =>"+line);  
	            }  
	        } catch (IOException e) {  
	            System.out.println("IOException in try block =>" + e.getMessage());  
	        }  
	    }  
	}
	```
## （五）try-with-resources 处理多个资源
1. try-with-resources 语句中可以声明多个资源，方法是使用分号 ; 分隔各个资源：
2. 例
	``` Java
	import java.io.*;  
	import java.util.*;  
	class RunoobTest {  
	    public static void main(String[] args) throws IOException{  
	        try (Scanner scanner = new Scanner(new File("testRead.txt"));  
	            PrintWriter writer = new PrintWriter(new File("testWrite.txt"))) {  
	            while (scanner.hasNext()) {  
	                writer.print(scanner.nextLine());  
	            }  
	        }  
	    }  
	}  
	```
3. 以上实例使用 Scanner 对象从 testRead.txt 文件中读取一行并将其写入新的 testWrite.txt 文件中。
4. 多个声明资源时，try-with-resources 语句以相反的顺序关闭这些资源。 在本例中，PrintWriter 对象先关闭，然后 Scanner 对象关闭。
# 八、声明自定义异常
1. 在 Java 中你可以自定义异常。编写自己的异常类时需要记住下面的几点。  
	- 所有异常都必须是 Throwable 的子类。
	- 如果希望写一个检查性异常类，则需要继承 Exception 类。
	- 如果你想写一个运行时异常类，那么需要继承 RuntimeException 类。
2. 可以像下面这样定义自己的异常类：
	``` Java
	class MyException extends Exception{ }
	```
3. 只继承Exception 类来创建的异常类是检查性异常类。
4. 下面的 InsufficientFundsException 类是用户定义的异常类，它继承自 Exception。
5. 一个异常类和其它任何类一样，包含有变量和方法。
# 九、通用异常
1. 在Java中定义了两种类型的异常和错误。
	- JVM(Java虚拟机)异常：由 JVM 抛出的异常或错误。例如：NullPointerException 类，ArrayIndexOutOfBoundsException 类，ClassCastException 类。
	- 程序级异常：由程序或者API程序抛出的异常。例如 IllegalArgumentException 类，IllegalStateException 类。