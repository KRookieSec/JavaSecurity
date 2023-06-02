# 一、Number类
1. 所有的包装类**（Integer、Long、Byte、Double、Float、Short）**都是抽象类 Number 的子类。

|包装类|基本数据类型|
|---|---|
|Boolean|boolean|
|Byte|byte|
|Short|short|
|Integer|int|
|Long|long|
|Character|char|
|Float|float|
|Double|double|
# 二、Math 类
1. Java 的 Math 包含了用于执行基本数学运算的属性和方法，如初等指数、对数、平方根和三角函数。
2. Math 的方法都被定义为 static 形式，通过 Math 类可以在主函数中直接调用。
# 三、Number & Math 类方法
1. Number & Math 类常用的一些方法：

|序号|方法与描述|
|---|---|
|1|xxxValue()  <br>将 Number 对象转换为xxx数据类型的值并返回。|
|2|compareTo() <br>将number对象与参数比较。|
|3|equals() <br>判断number对象是否与参数相等。|
|4|valueOf() <br>返回一个 Number 对象指定的内置数据类型|
|5|toString() <br>以字符串形式返回值。|
|6|parseInt() <br>将字符串解析为int类型。|
|7|abs() <br>返回参数的绝对值。|
|8|ceil() <br>返回大于等于( >= )给定参数的的最小整数，类型为双精度浮点型。|
|9|floor() <br>返回小于等于（<=）给定参数的最大整数 。|
|10|rint() <br>返回与参数最接近的整数。返回类型为double。|
|11|round() <br>它表示**四舍五入**，算法为 Math.floor(x+0.5)，即将原来的数字加上 0.5 后再向下取整，所以，Math.round(11.5) 的结果为12，Math.round(-11.5) 的结果为-11。|
|12|min() <br>返回两个参数中的最小值。|
|13|max() <br>返回两个参数中的最大值。|
|14|exp() <br>返回自然数底数e的参数次方。|
|15|log() <br>返回参数的自然数底数的对数值。|
|16|pow() <br>返回第一个参数的第二个参数次方。|
|17|sqrt() <br>求参数的算术平方根。|
|18|sin() <br>求指定double类型参数的正弦值。|
|19|cos() <br>求指定double类型参数的余弦值。|
|20|tan() <br>求指定double类型参数的正切值。|
|21|asin() <br>求指定double类型参数的反正弦值。|
|22|acos() <br>求指定double类型参数的反余弦值。|
|23|atan() <br>求指定double类型参数的反正切值。|
|24|atan2() <br>将笛卡尔坐标转换为极坐标，并返回极坐标的角度值。|
|25|toDegrees() <br>将参数转化为角度。|
|26|toRadians() <br>将角度转换为弧度。|
|27|random() <br>返回一个随机数。|
# 四、Math 的 floor,round 和 ceil 方法实例比较

|参数|Math.floor|Math.round|Math.ceil|
|---|---|---|---|
|1.4|1|1|2|
|1.5|1|2|2|
|1.6|1|2|2|
|-1.4|-2|-1|-1|
|-1.5|-2|-1|-1|
|-1.6|-2|-2|-1|
# 五、Character 类
1. Character 类用于对单个字符进行操作。
2. Character 类在对象中包装一个基本类型 **char** 的值
3. Character类提供了一系列方法来操纵字符。
# 六、转义序列
1. 前面有反斜杠（\）的字符代表转义字符，它对编译器来说是有特殊含义的。

|转义序列|描述|
|---|---|
|\t|在文中该处插入一个tab键|
|\b|在文中该处插入一个后退键|
|\n|在文中该处换行|
|\r|在文中该处插入回车|
|\f|在文中该处插入换页符|
|\'|在文中该处插入单引号|
|\"|在文中该处插入双引号|
|\\|在文中该处插入反斜杠|
# 七、Character 方法

|序号|方法与描述|
|---|---|
|1|isLetter()  <br>是否是一个字母|
|2|isDigit() <br>是否是一个数字字符|
|3|isWhitespace() <br>是否是一个空白字符|
|4|isUpperCase() <br>是否是大写字母|
|5|isLowerCase() <br>是否是小写字母|
|6|toUpperCase() <br>指定字母的大写形式|
|7|toLowerCase() <br>指定字母的小写形式|
|8|toString() <br>返回字符的字符串形式，字符串的长度仅为1|