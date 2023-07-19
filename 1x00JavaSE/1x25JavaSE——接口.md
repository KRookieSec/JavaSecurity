# 一、接口概述
1. 接口（中文：Interface），在JAVA编程语言中是一个抽像类，是抽像方法的集合，接口通常以接口来声明。一个类通过继承接口的方式，从而而来继承接口的抽像方式。
2. 接口并不是类，写接口的方式和类很相像，但它们属于不同的概念。类描述对象的性质和方法。接口则包含类要现实的方法。
3. 除了实际接口的类是抽像类，否则该类要确定接口中的所有方法。
4. 接口无法被实例化，但可以被实现。一个实际接口的类，必须实际接口内所描述的所有方法，否则就必须声明为抽象类。另外，在 Java 中，接口类类型可以使用来声明一个变量，他们可以成为一个空指针，或者被绑定在一个以此类推接口现实的对象。
# 二、接口与类
1. 接口与类相似点：
	- 一个接口可以有多个方法。
	- 接口文件保存在 .java 结尾的文件中，文件名使用接口名。
	- 接口的字节码文件保存在 .class 结尾的文件中。
	- 接口相应的字节码文件必须在与包名称相匹配的目录结构中。
2. 接口与类的区别：
	- 接口不能用于实例化对象。
	- 接口没有构造方法。
	- 接口中所有的方法必须是抽象方法，Java 8 之后 接口中可以使用 default 关键字修饰的非抽象方法。
	- 接口不能包含成员变量，除了 static 和 final 变量。
	- 接口不是被类继承了，而是要被类实现。
	- 接口支持多继承。
3. 接口特性
	- 接口中每一个方法也是隐式抽象的,接口中的方法会被隐式的指定为 **public abstract**（只能是 public abstract，其他修饰符都会报错）。
	- 接口中可以含有变量，但是接口中的变量会被隐式的指定为 **public static final** 变量（并且只能是 public，用 private 修饰会报编译错误）。
	- 接口中的方法是不能在接口中实现的，只能由实现接口的类来实现接口中的方法。
4. 抽象类和接口的区别
	- 抽象类中的方法可以有方法体，就是能实现方法的具体功能，但是接口中的方法不行。
	- 抽象类中的成员变量可以是各种类型的，而接口中的成员变量只能是 **public static final** 类型的。
	- 接口中不能含有静态代码块以及静态方法(用 static 修饰的方法)，而抽象类是可以有静态代码块和静态方法。
	- 一个类只能继承一个抽象类，而一个类却可以实现多个接口。
> **注**：JDK 1.8 以后，接口里可以有静态方法和方法体了。
> **注**：JDK 1.8 以后，接口允许包含具体实现的方法，该方法称为"默认方法"，默认方法使用 default 关键字修饰。
> **注**：JDK 1.9 以后，允许将方法定义为 private，使得某些复用的代码不会把方法暴露出去。
# 三、接口的声明
1. 接口的声明语法格式如下：
	``` Java
	[可见度] interface 接口名称 [extends 其他的接口名] { // 声明变量 // 抽象方法 }
	```
2. Interface关键字用来声明一个接口。下面是接口声明的一个简单例子。
	``` Java
	import java.lang.*; //引入包 
	public interface NameOfInterface { 
		//任何类型 final, static 字段 
		//抽象方法 
	}
	```
3. 接口有以下特性：
	- 接口是隐式抽象的，当声明一个接口的时候，不必使用**abstract**关键字。
	- 接口中每一个方法也是隐式抽象的，声明时同样不需要**abstract**关键字。
	- 接口中的方法都是公有的。
# 四、接口的实现
1. 当类实现接口的时候，类要实现接口中所有的方法。否则，类必须声明为抽象的类。
2. 类使用implements关键字实现接口。在类声明中，Implements关键字放在class声明后面。
3. 实现一个接口的语法，可以使用这个公式：
	``` Java
	...implements 接口名称[, 其他接口名称, 其他接口名称..., ...] ...
	```
4. 例
	``` Java
	public class MammalInt implements Animal{ 
		public void eat(){ 
			System.out.println("Mammal eats"); 
		} 
		
		public void travel(){ 
			System.out.println("Mammal travels"); 
		} 
		
		public int noOfLegs(){ 
			return 0; 
		} 
		
		public static void main(String args[]){ 
			MammalInt m = new MammalInt(); 
			m.eat(); 
			m.travel(); 
		} 
	}
	```
5. 重写接口中声明的方法时，需要注意以下规则：
	- 类在实现接口的方法时，不能抛出强制性异常，只能在接口中，或者继承接口的抽象类中抛出该强制性异常。
	- 类在重写方法时要保持一致的方法名，并且应该保持相同或者相兼容的返回值类型。
	- 如果实现接口的类是抽象类，那么就没必要实现该接口的方法。
6. 在实现接口的时候，也要注意一些规则：
	- 一个类可以同时实现多个接口。
	- 一个类只能继承一个类，但是能实现多个接口。
	- 一个接口能继承另一个接口，这和类之间的继承比较相似。
# 五、接口的继承
1. 一个接口能继承另一个接口，和类之间的继承方式比较相似。接口的继承使用extends关键字，子接口继承父接口的方法。
2. 例
	``` Java
	public interface Sports { 
		public void setHomeTeam(String name); 
		public void setVisitingTeam(String name); 
	}
	
	public interface Football extends Sports { 
		public void homeTeamScored(int points); 
		public void visitingTeamScored(int points); 
		public void endOfQuarter(int quarter); 
	} 
	
	public interface Hockey extends Sports { 
		public void homeGoalScored(); 
		public void visitingGoalScored(); 
		public void endOfPeriod(int period); 
		public void overtimePeriod(int ot); 
	}
	```
# 六、接口的多继承
1. 在Java中，类的多继承是不合法，但接口允许多继承。
2. 在接口的多继承中extends关键字只需要使用一次，在其后跟着继承接口。 如下所示：
	``` Java
	public interface Hockey extends Sports, Event
	```
3. 以上的程序片段是合法定义的子接口，与类不同的是，接口允许多继承，而 Sports及 Event 可以定义或是继承相同的方法
# 七、标记接口
1. 最常用的继承接口是没有包含任何方法的接口。
2. 标记接口是没有任何方法和属性的接口.它仅仅表明它的类属于一个特定的类型,供其他代码来测试允许做一些事情。
3. 标记接口作用：简单形象的说就是给某个对象打个标（盖个戳），使对象拥有某个或某些特权。
4. 例如：java.awt.event 包中的 MouseListener 接口继承的 java.util.EventListener 接口定义如下：
	``` Java
	package java.util; 
	public interface EventListener {
	
	}
	```
5. 没有任何方法的接口被称为标记接口。标记接口主要用于以下两种目的：
- **建立一个公共的父接口：**
    正如EventListener接口，这是由几十个其他接口扩展的Java API，你可以使用一个标记接口来建立一组接口的父接口。例如：当一个接口继承了EventListener接口，Java虚拟机(JVM)就知道该接口将要被用于一个事件的代理方案。
- **向一个类添加数据类型：**
    这种情况是标记接口最初的目的，实现标记接口的类不需要定义任何接口方法(因为标记接口根本就没有方法)，但是该类通过多态性变成一个接口类型。