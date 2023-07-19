# 一、日期时间
1. java.util 包提供了 Date 类来封装当前的日期和时间。 Date 类提供两个构造函数来实例化 Date 对象。
2. 第一个构造函数使用当前日期和时间来初始化对象。
	``` Java
	Date( )
	```
3. 第二个构造函数接收一个参数，该参数是从 1970 年 1 月 1 日起的毫秒数。
	``` Java
	Date(long millisec)
	```
4. Date 对象创建以后，可以调用下面的方法。

|序号|方法和描述|
|---|---|
|1|**boolean after(Date date)**  <br>若当调用此方法的Date对象在指定日期之后返回true,否则返回false。|
|2|**boolean before(Date date)**  <br>若当调用此方法的Date对象在指定日期之前返回true,否则返回false。|
|3|**Object clone( )**  <br>返回此对象的副本。|
|4|**int compareTo(Date date)**  <br>比较当调用此方法的Date对象和指定日期。两者相等时候返回0。调用对象在指定日期之前则返回负数。调用对象在指定日期之后则返回正数。|
|5|**int compareTo(Object obj)**  <br>若obj是Date类型则操作等同于compareTo(Date) 。否则它抛出ClassCastException。|
|6|**boolean equals(Object date)**  <br>当调用此方法的Date对象和指定日期相等时候返回true,否则返回false。|
|7|**long getTime( )**  <br>返回自 1970 年 1 月 1 日 00:00:00 GMT 以来此 Date 对象表示的毫秒数。|
|8|**int hashCode( )**  <br> 返回此对象的哈希码值。|
|9|**void setTime(long time)**  <br>   <br>用自1970年1月1日00:00:00 GMT以后time毫秒数设置时间和日期。|
|10|**String toString( )**  <br>把此 Date 对象转换为以下形式的 String： dow mon dd hh:mm:ss zzz yyyy 其中： dow 是一周中的某一天 (Sun, Mon, Tue, Wed, Thu, Fri, Sat)。|
# 二、日期时间的使用
## （一）获取当前时间
1. 使用 Date 对象的 toString() 方法来打印当前日期和时间
## （二）日期比较
1. Java使用以下三种方法来比较两个日期：
	- 使用 getTime() 方法获取两个日期（自1970年1月1日经历的毫秒数值），然后比较这两个值。
	- 使用方法 before()，after() 和 equals()。例如，一个月的12号比18号早，则 new Date(99, 2, 12).before(new Date (99, 2, 18)) 返回true。
	- 使用 compareTo() 方法，它是由 Comparable 接口定义的，Date 类实现了这个接口。
# 三、时间日期的格式化
## （一）使用 SimpleDateFormat 格式化日期
1. SimpleDateFormat 是一个以语言环境敏感的方式来格式化和分析日期的类。SimpleDateFormat 允许你选择任何用户自定义日期时间格式来运行。
	``` Java
	import java.util.*; 
	import java.text.*; 
	public class DateDemo { 
		public static void main(String[] args) {
			Date dNow = new Date( ); 
			SimpleDateFormat ft = new SimpleDateFormat ("yyyy-MM-dd hh:mm:ss");
			System.out.println("当前时间为: " + ft.format(dNow)); 
		} 
	}
	```
## （二）日期和时间的格式化编码
时间模式字符串用来指定时间格式。在此模式中，所有的 ASCII 字母被保留为模式字母，定义如下：

|**字母**|**描述**|**示例**|
|---|---|---|
|G|纪元标记|AD|
|y|四位年份|2001|
|M|月份|July or 07|
|d|一个月的日期|10|
|h|A.M./P.M. (1~12)格式小时|12|
|H|一天中的小时 (0~23)|22|
|m|分钟数|30|
|s|秒数|55|
|S|毫秒数|234|
|E|星期几|Tuesday|
|D|一年中的日子|360|
|F|一个月中第几周的周几|2 (second Wed. in July)|
|w|一年中第几周|40|
|W|一个月中第几周|1|
|a|A.M./P.M. 标记|PM|
|k|一天中的小时(1~24)|24|
|K|A.M./P.M. (0~11)格式小时|10|
|z|时区|Eastern Standard Time|
|'|文字定界符|Delimiter|
|"|单引号|`|
## （三）使用printf格式化日期
1. printf 方法可以很轻松地格式化时间和日期。使用两个字母格式，它以 %t 开头并且以下面表格中的一个字母结尾。
	- %tY：输出四位数的年份，例如：2023
	- %ty：输出两位数的年份，例如：23
	- %tm：输出两位数的月份，例如：02
	- %tB：输出月份的全名，例如：February
	- %tb：输出月份的缩写，例如：Feb
	- %tA：输出星期的全名，例如：Wednesday
	- %ta：输出星期的缩写，例如：Wed
	- %td：输出两位数的日期，例如：24
	- %te：输出一位或两位数的日期，例如：24 或 02
	- %tH：输出24小时制的小时数，例如：23
	- %tI：输出12小时制的小时数，例如：11
	- %tM：输出分钟数，例如：45
	- %tS：输出秒数，例如：30
	- %tp：输出上午还是下午，例如：AM 或 PM
	- %tZ：输出时区，例如：GMT+08:00

|转换符|说明|示例|
|---|---|---|
|%tc|包括全部日期和时间信息|星期六 十月 27 14:21:20 CST 2007|
|%tF|"年-月-日"格式|2007-10-27|
|%tD|"月/日/年"格式|10/27/07|
|%tr|"HH:MM:SS PM"格式（12时制）|02:25:51 下午|
|%tT|"HH:MM:SS"格式（24时制）|14:28:16|
|%tR|"HH:MM"格式（24时制）|14:28|
## （四）解析字符串为时间
1. SimpleDateFormat 类有一些附加的方法，特别是parse()，它试图按照给定的SimpleDateFormat 对象的格式化存储来解析字符串。
## （五）sleep()
1. sleep()使当前线程进入停滞状态（阻塞当前线程），让出CPU的使用、目的是不让当前线程独自霸占该进程所获的CPU资源，以留一定时间给其他线程执行的机会。
# 四、Calendar类
1. 我们现在已经能够格式化并创建一个日期对象了，但是我们如何才能设置和获取日期数据的特定部分呢，比如说小时，日，或者分钟? 我们又如何在日期的这些部分加上或者减去值呢? 答案是使用Calendar 类。
	- Calendar类的功能要比Date类强大很多，而且在实现方式上也比Date类要复杂一些。
	- Calendar类是一个抽象类，在实际使用时实现特定的子类的对象，创建对象的过程对程序员来说是透明的，只需要使用getInstance方法创建即可。
2. 创建一个代表系统当前日期的Calendar对象
	``` Java
	Calendar c = Calendar.getInstance();//默认是当前日期
	```
3. 创建一个指定日期的Calendar对象。使用Calendar类代表特定的时间，需要首先创建一个Calendar的对象，然后再设定该对象中的年月日参数来完成。
	``` Java
	//创建一个代表2009年6月12日的Calendar对象
Calendar c1 = Calendar.getInstance();
c1.set(2009, 6 - 1, 12);
	```
## （一）Calendar类对象字段类型
1. Calendar类中用以下这些常量表示不同的意义，jdk内的很多类其实都是采用的这种思想

|常量|描述|
|---|---|
|Calendar.YEAR|年份|
|Calendar.MONTH|月份|
|Calendar.DATE|日期|
|Calendar.DAY_OF_MONTH|日期，和上面的字段意义完全相同|
|Calendar.HOUR|12小时制的小时|
|Calendar.HOUR_OF_DAY|24小时制的小时|
|Calendar.MINUTE|分钟|
|Calendar.SECOND|秒|
|Calendar.DAY_OF_WEEK|星期几|
## （二）Calendar类对象信息的设置
1. Set设置。如：
	``` Java
	Calendar c1 = Calendar.getInstance();
	```
	- 调用：
	``` Java
	public final void set(int year,int month,int date)
	
	c1.set(2009, 6, 12);//把Calendar对象c1的年月日分别设这为：2009、6、12
	```
	- 利用字段类型设置
		- 如果只设定某个字段，例如日期的值，则可以使用如下set方法：
			``` Java
			public void set(int field,int value)
			```
		- 把 c1对象代表的日期设置为10号，其它所有的数值会被重新计算
			``` Java
			c1.set(Calendar.DATE,10);
			```
		- 把c1对象代表的年份设置为2008年，其他的所有数值会被重新计算
			``` Java
			c1.set(Calendar.YEAR,2008);
			```
	- 其他字段属性set的意义以此类推
2. Add设置
	``` Java
	Calendar c1 = Calendar.getInstance();
	```
	- 把c1对象的日期加上10，也就是c1也就表示为10天后的日期，其它所有的数值会被重新计算
		``` Java
		c1.add(Calendar.DATE, 10);
		```
	- 把c1对象的日期减去10，也就是c1也就表示为10天前的日期，其它所有的数值会被重新计算
		``` Java
		c1.add(Calendar.DATE, -10);
		```
	- 其他字段属性的add的意义以此类推
## （三）Calendar类对象信息的获得
``` Java
Calendar c1 = Calendar.getInstance(); 
// 获得年份 
int year = c1.get(Calendar.YEAR); 
// 获得月份 
int month = c1.get(Calendar.MONTH) + 1; 
// 获得日期 
int date = c1.get(Calendar.DATE); 
// 获得小时 
int hour = c1.get(Calendar.HOUR_OF_DAY); 
// 获得分钟 
int minute = c1.get(Calendar.MINUTE); 
// 获得秒 
int second = c1.get(Calendar.SECOND); 
// 获得星期几（注意（这个与Date类是不同的）：1代表星期日、2代表星期1、3代表星期二，以此类推） 
int day = c1.get(Calendar.DAY_OF_WEEK);
```
# 五、GregorianCalendar类
1. Calendar类实现了公历日历，GregorianCalendar是Calendar类的一个具体实现。
2. Calendar 的getInstance（）方法返回一个默认用当前的语言环境和时区初始化的GregorianCalendar对象。GregorianCalendar定义了两个字段：AD和BC。这是代表公历定义的两个时代。
3. 下面列出GregorianCalendar对象的几个构造方法：

|**序号**|**构造函数和说明**|
|---|---|
|1|**GregorianCalendar()**  <br>在具有默认语言环境的默认时区内使用当前时间构造一个默认的 GregorianCalendar。|
|2|**GregorianCalendar(int year, int month, int date)**  <br>在具有默认语言环境的默认时区内构造一个带有给定日期设置的 GregorianCalendar|
|3|**GregorianCalendar(int year, int month, int date, int hour, int minute)**  <br>为具有默认语言环境的默认时区构造一个具有给定日期和时间设置的 GregorianCalendar。|
|4|**GregorianCalendar(int year, int month, int date, int hour, int minute, int second)**  <br>  为具有默认语言环境的默认时区构造一个具有给定日期和时间设置的 GregorianCalendar。|
|5|**GregorianCalendar(Locale aLocale)**  <br>在具有给定语言环境的默认时区内构造一个基于当前时间的 GregorianCalendar。|
|6|**GregorianCalendar(TimeZone zone)**  <br>在具有默认语言环境的给定时区内构造一个基于当前时间的 GregorianCalendar。|
|7|**GregorianCalendar(TimeZone zone, Locale aLocale)**  <br> 在具有给定语言环境的给定时区内构造一个基于当前时间的 GregorianCalendar。|
4. 这里是GregorianCalendar 类提供的一些有用的方法列表：

|**序号**|**方法和说明**|
|---|---|
|1|**void add(int field, int amount)**  <br>根据日历规则，将指定的（有符号的）时间量添加到给定的日历字段中。|
|2|**protected void computeFields()**  <br>转换UTC毫秒值为时间域值|
|3|**protected void computeTime()**  <br>覆盖Calendar ，转换时间域值为UTC毫秒值|
|4|**boolean equals(Object obj)**  <br>比较此 GregorianCalendar 与指定的 Object。|
|5|**int get(int field)**  <br>获取指定字段的时间值|
|6|**int getActualMaximum(int field)**  <br>返回当前日期，给定字段的最大值|
|7|**int getActualMinimum(int field)**  <br>返回当前日期，给定字段的最小值|
|8|**int getGreatestMinimum(int field)**  <br> 返回此 GregorianCalendar 实例给定日历字段的最高的最小值。|
|9|**Date getGregorianChange()**  <br>获得格里高利历的更改日期。|
|10|**int getLeastMaximum(int field)**  <br>返回此 GregorianCalendar 实例给定日历字段的最低的最大值|
|11|**int getMaximum(int field)**  <br>返回此 GregorianCalendar 实例的给定日历字段的最大值。|
|12|**Date getTime()**  <br>获取日历当前时间。|
|13|**long getTimeInMillis()**  <br>获取用长整型表示的日历的当前时间|
|14|**TimeZone getTimeZone()**  <br>获取时区。|
|15|**int getMinimum(int field)**  <br>返回给定字段的最小值。|
|16|**int hashCode()**  <br>重写hashCode.|
|17|**boolean isLeapYear(int year)**  <br>确定给定的年份是否为闰年。|
|18|**void roll(int field, boolean up)**  <br>在给定的时间字段上添加或减去（上/下）单个时间单元，不更改更大的字段。|
|19|**void set(int field, int value)**  <br>用给定的值设置时间字段。|
|20|**void set(int year, int month, int date)**  <br>设置年、月、日的值。|
|21|**void set(int year, int month, int date, int hour, int minute)**  <br>设置年、月、日、小时、分钟的值。|
|22|**void set(int year, int month, int date, int hour, int minute, int second)**  <br>设置年、月、日、小时、分钟、秒的值。|
|23|**void setGregorianChange(Date date)**  <br>设置 GregorianCalendar 的更改日期。|
|24|**void setTime(Date date)**  <br>用给定的日期设置Calendar的当前时间。|
|25|**void setTimeInMillis(long millis)**  <br>用给定的long型毫秒数设置Calendar的当前时间。|
|26|**void setTimeZone(TimeZone value)**  <br>用给定时区值设置当前时区。|
|27|**String toString()**  <br>返回代表日历的字符串。|