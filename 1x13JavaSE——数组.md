# 一、声明数组变量
1. 首先必须声明数组变量，才能在程序中使用数组。下面是声明数组变量的语法：
``` Java
	dataType[] arrayRefVar; // 首选的方法 
	或 
	dataType arrayRefVar[]; // 效果相同，但不是首选方法
```
2. 注意:建议使用 dataType\[] arrayRefVar的声明风格声明数组变量。 dataType arrayRefVar\[] 风格是来自 C/C++ 语言 ，在Java中采用是为了让 C/C++ 程序员能够快速理解java语言。
# 二、创建数组
1. Java语言使用new操作符来创建数组，语法如下：
	``` Java
	arrayRefVar = new dataType[arraySize];
	```
2. 上面的语法语句做了两件事：
	- 一、使用 dataType\[arraySize] 创建了一个数组。
	- 二、把新创建的数组的引用赋值给变量 arrayRefVar。
3. 数组变量的声明，和创建数组可以用一条语句完成，如下所示：
	``` Java
	dataType[] arrayRefVar = new dataType[arraySize];
	```
4. 另外，你还可以使用如下的方式创建数组。
	``` Java
	dataType[] arrayRefVar = {value0, value1, ..., valuek};
	```
5. 数组的元素是通过索引访问的。数组索引从 0 开始，所以索引值从 0 到 arrayRefVar.length-1。
# 三、处理数组
1. 数组的元素类型和数组的大小都是确定的，所以当处理数组元素时候，我们通常使用基本循环或者 For-Each 循环。
2. JDK 1.5 引进了一种新的循环类型，被称为 For-Each 循环或者加强型循环，它能在不使用下标的情况下遍历数组。
	- 语法格式如下：
		``` Java
		for(type element: array)
		{
		    System.out.println(element);
		}
		```
3. 数组可以作为参数传递给方法。
4. 数组作为函数的返回值
# 四、多维数组
1. 多维数组可以看成是数组的数组，比如二维数组就是一个特殊的一维数组，其每一个元素都是一个一维数组，例如：
	``` Java
	String[][] str = new String[3][4];
	```
## （一）多维数组的动态初始化（以二维数组为例）
1. 直接为每一维分配空间，格式如下：
	``` Java
	type[][] typeName = new type[typeLength1][typeLength2];
	```
2. type 可以为基本数据类型和复合数据类型，typeLength1 和 typeLength2 必须为正整数，typeLength1 为行数，typeLength2 为列数。
## （二）多维数组的引用（以二维数组为例）
1. 对二维数组中的每个元素，引用方式为 arrayName\[index1]\[index2]
# 五、Arrays 类
1. java.util.Arrays 类能方便地操作数组，它提供的所有方法都是静态的。
2. 具有以下功能：
	- 给数组赋值：通过 fill 方法。
	- 对数组排序：通过 sort 方法,按升序。
	- 比较数组：通过 equals 方法比较数组中元素值是否相等。
	- 查找数组元素：通过 binarySearch 方法能对排序好的数组进行二分查找法操作。

|序号|方法和说明|
|---|---|
|1|**public static int binarySearch(Object[] a, Object key)**  <br>用二分查找算法在给定数组中搜索给定值的对象(Byte,Int,double等)。数组在调用前必须排序好的。如果查找值包含在数组中，则返回搜索键的索引；否则返回 (-(_插入点_) - 1)。|
|2|**public static boolean equals(long[] a, long[] a2)**  <br>如果两个指定的 long 型数组彼此_相等_，则返回 true。如果两个数组包含相同数量的元素，并且两个数组中的所有相应元素对都是相等的，则认为这两个数组是相等的。换句话说，如果两个数组以相同顺序包含相同的元素，则两个数组是相等的。同样的方法适用于所有的其他基本数据类型（Byte，short，Int等）。|
|3|**public static void fill(int[] a, int val)**  <br>将指定的 int 值分配给指定 int 型数组指定范围中的每个元素。同样的方法适用于所有的其他基本数据类型（Byte，short，Int等）。|
|4|**public static void sort(Object[] a)**  <br>对指定对象数组根据其元素的自然顺序进行升序排列。同样的方法适用于所有的其他基本数据类型（Byte，short，Int等）。|
