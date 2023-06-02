字符串广泛应用 在 Java 编程中，在 Java 中字符串属于对象，Java 提供了 String 类来创建和操作字符串。
# 一、创建字符串
1. 创建字符串最简单的方式如下:
	``` Java
	String str = "Runoob";
	```
2. 在代码中遇到字符串常量时，这里的值是 "**Runoob**"，编译器会使用该值创建一个 String 对象。
和其它对象一样，可以使用关键字和构造方法来创建 String 对象。
3. 用构造函数创建字符串：
	``` Java
	String str2=new String("Runoob");
	```
4. String 创建的字符串存储在公共池中，而 new 创建的字符串对象在堆上：
	``` Java
	// String 直接创建 
	String s1 = "Java"; 
	// 相同引用 
	String s2 = s1; 
	// String 对象创建 
	String s3 = new String("Java"); 
	```
5. 注意:String 类是不可改变的，所以你一旦创建了 String 对象，那它的值就无法改变了
6. 如果需要对字符串做很多修改，那么应该选择使用 StringBuffer & StringBuilder 类。
# 二、字符串长度
1. 用于获取有关对象的信息的方法称为访问器方法。
2. String 类的一个访问器方法是 length() 方法，它返回字符串对象包含的字符数。
# 三、连接字符串
1. String 类提供了连接两个字符串的方法：
	``` Java
	string1.concat(string2);
	```
2. 返回 string2 连接 string1 的新字符串。也可以对字符串常量使用 concat() 方法，如：
	``` Java
	"我的名字是 ".concat("Java");
	```
3. 更常用的是使用'+'操作符来连接字符串，如：
	``` Java
	"Hello," + " Java" + "!"
	```
# 四、创建格式化字符串
1. 我们知道输出格式化数字可以使用 printf() 和 format() 方法。
2. String 类使用静态方法 format() 返回一个String 对象而不是 PrintStream 对象。
3. String 类的静态方法 format() 能用来创建可复用的格式化字符串，而不仅仅是用于一次打印输出。
4. 例：
	``` Java
	System.out.printf("浮点型变量的值为 " + 
					  "%f, 整型变量的值为 " + 
					  " %d, 字符串变量的值为 " + 
					  "is %s", floatVar, intVar, stringVar);
	```
# 五、String 方法

|SN(序号)|方法描述|
|---|---|
|1|char charAt(int index)  <br>返回指定索引处的 char 值。|
|2|int compareTo(Object o) <br>把这个字符串和另一个对象比较。|
|3|int compareTo(String anotherString) <br>按字典顺序比较两个字符串。|
|4|int compareToIgnoreCase(String str) <br>按字典顺序比较两个字符串，不考虑大小写。|
|5|String concat(String str) <br>将指定字符串连接到此字符串的结尾。|
|6|boolean contentEquals(StringBuffer sb) <br>当且仅当字符串与指定的StringBuffer有相同顺序的字符时候返回真。|
|7|static String copyValueOf(char[] data) <br>返回指定数组中表示该字符序列的 String。|
|8|static String copyValueOf(char[] data, int offset, int count) <br>返回指定数组中表示该字符序列的 String。|
|9|boolean endsWith(String suffix) <br>测试此字符串是否以指定的后缀结束。|
|10|boolean equals(Object anObject) <br>将此字符串与指定的对象比较。|
|11|boolean equalsIgnoreCase(String anotherString) <br>将此 String 与另一个 String 比较，不考虑大小写。|
|12|byte[] getBytes() <br> 使用平台的默认字符集将此 String 编码为 byte 序列，并将结果存储到一个新的 byte 数组中。|
|13|byte[] getBytes(String charsetName) <br>使用指定的字符集将此 String 编码为 byte 序列，并将结果存储到一个新的 byte 数组中。|
|14|void getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin) <br>将字符从此字符串复制到目标字符数组。|
|15|int hashCode() <br>返回此字符串的哈希码。|
|16|int indexOf(int ch) <br>返回指定字符在此字符串中第一次出现处的索引。|
|17|int indexOf(int ch, int fromIndex) <br>返回在此字符串中第一次出现指定字符处的索引，从指定的索引开始搜索。|
|18|int indexOf(String str) <br> 返回指定子字符串在此字符串中第一次出现处的索引。|
|19|int indexOf(String str, int fromIndex) <br>返回指定子字符串在此字符串中第一次出现处的索引，从指定的索引开始。|
|20|String intern() <br> 返回字符串对象的规范化表示形式。|
|21|int lastIndexOf(int ch) <br> 返回指定字符在此字符串中最后一次出现处的索引。|
|22|int lastIndexOf(int ch, int fromIndex)  <br>返回指定字符在此字符串中最后一次出现处的索引，从指定的索引处开始进行反向搜索。|
|23|int lastIndexOf(String str) <br>返回指定子字符串在此字符串中最右边出现处的索引。|
|24|int lastIndexOf(String str, int fromIndex) <br> 返回指定子字符串在此字符串中最后一次出现处的索引，从指定的索引开始反向搜索。|
|25|int length() <br>返回此字符串的长度。|
|26|boolean matches(String regex) <br>告知此字符串是否匹配给定的正则表达式。|
|27|boolean regionMatches(boolean ignoreCase, int toffset, String other, int ooffset, int len) <br>测试两个字符串区域是否相等。|
|28|boolean regionMatches(int toffset, String other, int ooffset, int len) <br>测试两个字符串区域是否相等。|
|29|String replace(char oldChar, char newChar) <br>返回一个新的字符串，它是通过用 newChar 替换此字符串中出现的所有 oldChar 得到的。|
|30|String replaceAll(String regex, String replacement) <br>使用给定的 replacement 替换此字符串所有匹配给定的正则表达式的子字符串。|
|31|String replaceFirst(String regex, String replacement) <br> 使用给定的 replacement 替换此字符串匹配给定的正则表达式的第一个子字符串。|
|32|String[] split(String regex) <br>根据给定正则表达式的匹配拆分此字符串。|
|33|String[] split(String regex, int limit) <br>根据匹配给定的正则表达式来拆分此字符串。|
|34|boolean startsWith(String prefix) <br>测试此字符串是否以指定的前缀开始。|
|35|boolean startsWith(String prefix, int toffset) <br>测试此字符串从指定索引开始的子字符串是否以指定前缀开始。|
|36|CharSequence subSequence(int beginIndex, int endIndex) <br> 返回一个新的字符序列，它是此序列的一个子序列。|
|37|String substring(int beginIndex)  <br>返回一个新的字符串，它是此字符串的一个子字符串。|
|38|String substring(int beginIndex, int endIndex) <br>返回一个新字符串，它是此字符串的一个子字符串。|
|39|char[] toCharArray() <br>将此字符串转换为一个新的字符数组。|
|40|String toLowerCase() <br>使用默认语言环境的规则将此 String 中的所有字符都转换为小写。|
|41|String toLowerCase(Locale locale) <br> 使用给定 Locale 的规则将此 String 中的所有字符都转换为小写。|
|42|String toString() <br> 返回此对象本身（它已经是一个字符串！）。|
|43|String toUpperCase() <br>使用默认语言环境的规则将此 String 中的所有字符都转换为大写。|
|44|String toUpperCase(Locale locale) <br>使用给定 Locale 的规则将此 String 中的所有字符都转换为大写。|
|45|String trim() <br>返回字符串的副本，忽略前导空白和尾部空白。|
|46|static String valueOf(primitive data type x) <br>返回给定data type类型x参数的字符串表示形式。|
|47|contains(CharSequence chars) <br>判断是否包含指定的字符系列。|
|48|isEmpty() <br>判断字符串是否为空。|
# 六、StringBuffer 和 StringBuilder 类
1. 当对字符串进行修改的时候，需要使用 StringBuffer 和 StringBuilder 类。
2. 和 String 类不同的是，StringBuffer 和 StringBuilder 类的对象能够被多次的修改，并且不产生新的未使用对象。
3. 在使用 StringBuffer 类时，每次都会对 StringBuffer 对象本身进行操作，而不是生成新的对象，所以如果需要对字符串进行修改推荐使用 StringBuffer。
4. StringBuilder 类在 Java 5 中被提出，它和 StringBuffer 之间的最大不同在于 StringBuilder 的方法不是线程安全的（不能同步访问）。
5. 由于 StringBuilder 相较于 StringBuffer 有速度优势，所以多数情况下建议使用 StringBuilder 类。
# 七、StringBuffer 方法
1. StringBuffer 类支持的主要方法：

|序号|方法描述|
|---|---|
|1|public StringBuffer append(String s)  <br>将指定的字符串追加到此字符序列。|
|2|public StringBuffer reverse()  <br> 将此字符序列用其反转形式取代。|
|3|public delete(int start, int end)  <br>移除此序列的子字符串中的字符。|
|4|public insert(int offset, int i)  <br>将 `int` 参数的字符串表示形式插入此序列中。|
|5|insert(int offset, String str)  <br>将 `str` 参数的字符串插入此序列中。|
|6|replace(int start, int end, String str)  <br>使用给定 `String` 中的字符替换此序列的子字符串中的字符。|
2. StringBuffer 类的其他常用方法：

|序号|方法描述|
|---|---|
|1|int capacity()  <br>返回当前容量。|
|2|char charAt(int index)  <br>返回此序列中指定索引处的 `char` 值。|
|3|void ensureCapacity(int minimumCapacity)  <br>确保容量至少等于指定的最小值。|
|4|void getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin)  <br>将字符从此序列复制到目标字符数组 `dst`。|
|5|int indexOf(String str)  <br>返回第一次出现的指定子字符串在该字符串中的索引。|
|6|int indexOf(String str, int fromIndex)  <br>从指定的索引处开始，返回第一次出现的指定子字符串在该字符串中的索引。|
|7|int lastIndexOf(String str)  <br>返回最右边出现的指定子字符串在此字符串中的索引。|
|8|int lastIndexOf(String str, int fromIndex)  <br>返回 String 对象中子字符串最后出现的位置。|
|9|int length()  <br> 返回长度（字符数）。|
|10|void setCharAt(int index, char ch)  <br>将给定索引处的字符设置为 `ch`。|
|11|void setLength(int newLength)  <br>设置字符序列的长度。|
|12|CharSequence subSequence(int start, int end)  <br>返回一个新的字符序列，该字符序列是此序列的子序列。|
|13|String substring(int start)  <br>返回一个新的 `String`，它包含此字符序列当前所包含的字符子序列。|
|14|String substring(int start, int end)  <br>返回一个新的 `String`，它包含此序列当前所包含的字符子序列。|
|15|String toString()  <br>返回此序列中数据的字符串表示形式。|