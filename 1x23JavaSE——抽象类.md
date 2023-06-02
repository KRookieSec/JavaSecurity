# 一、抽象类概述
1. 在正面对象的概念中，所有的对象都是通过类来描绘的，但是是反过来的，并不是所有的类都是用描绘对象的，如果一个类中没有包含足够的信息来描述一个完整的对比图，这种的就是抽像类。
2. 抽象类排除了不能实例化对象之外，类的其他功能仍然存在，成员变量、成员方法和构造方法的访问方式和通用类一种。
3. 由于抽象类不能实例化对象，所以抽象类必须被继承，才能被使用。也就是因为这个原因，通常在设计阶段决定要不要设置计抽象类。
4. 父类包包含了子类集合的常见的方法，但由于父类本身是抽像的，所以不能使用这些方法。
5. 在Java中抽象类表示的是一种继承关系，一个类只能继承一个抽象类，而一个类却可以实现多个接口。
	``` Java
	public abstract class Employee { 
		private String name; 
		private String address; 
		private int number; 
		public Employee(String name, String address, int number) { 
			System.out.println("Constructing an Employee"); 
			this.name = name; 
			this.address = address; 
			this.number = number; 
		} 
		
		public double computePay() { 
			System.out.println("Inside Employee computePay"); 
			return 0.0; 
		} 
		
		public void mailCheck() { 
			System.out.println("Mailing a check to " + this.name + " " + this.address);
		} 
		
		public String toString() { 
			return name + " " + address + " " + number; 
		} 
		
		public String getName() { 
			return name; 
		} 
		
		public String getAddress() { 
			return address; 
		} 
		
		public void setAddress(String newAddress) { 
			address = newAddress; 
		} 
		
		public int getNumber() { 
			return number; 
		} 
	}
	```
# 二、继承抽象类
1. 我们可以通过以下方式继承 Employee 类的属性：
	``` Java
	public class Salary extends Employee { 
		private double salary; 
		//Annual salary 
		public Salary(String name, String address, int number, double salary) {
			super(name, address, number); 
			setSalary(salary); 
		} 
		
		public void mailCheck() { 
			System.out.println("Within mailCheck of Salary class "); 
			System.out.println("Mailing check to " + getName() + " with salary " + salary); 
		} 
		
		public double getSalary() { 
			return salary; 
		} 
		
		public void setSalary(double newSalary) { 
			if(newSalary >= 0.0) { 
				salary = newSalary; 
			} 
		} 
		
		public double computePay() { 
			System.out.println("Computing salary pay for " + getName()); 
			return salary/52; 
		} 
	}
	```
# 三、抽象方法
1. Abstract 关键字同样可以用来声明抽象方法，抽象方法只包含一个方法名，而没有方法体。
2. 抽象方法没有定义，方法名后面直接跟一个分号，而不是花括号。
	``` Java
	public abstract class Employee { 
		private String name; 
		private String address; 
		private int number; 
		public abstract double computePay(); 
		//其余代码 
	}
	```
2. 声明抽象方法会造成以下两个结果：
	- 如果一个类包含抽象方法，那么该类必须是抽象类。
	- 任何子类必须重写父类的抽象方法，或者声明自身为抽象类。
3. 继承抽象方法的子类必须重写该方法。否则，该子类也必须声明为抽象类。最终，必须有子类实现该抽象方法，否则，从最初的父类到最终的子类都不能用来实例化对象。
4. 如果Salary类继承了Employee类，那么它必须实现computePay()方法：
	``` Java
	public class Salary extends Employee { 
		private double salary; 
		// Annual salary 
		public double computePay() { 
			System.out.println("Computing salary pay for " + getName()); 
			return salary/52; 
		} 
		//其余代码 
	}
	```
