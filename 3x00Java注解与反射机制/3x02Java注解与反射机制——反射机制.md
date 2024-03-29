# 一、动态语言与静态语言

1. 动态语言
   - 在运行时可以改变其结构的语言：如新的函数、对象甚至代码可以被引进，已有的函数可以被删除或其他结构上的变化。通俗点就是代码可以根据某些条件改变自身结构
   
   - 主要的动态语言：Object-C、C#、JavaScript、PHP、Python等
2. 静态语言
   - 运行时结构不可变，如Java、C、C++
   
   - Java不是动态语言，但Java可以成为准动态语言。即Java有一定的动态性，可以利用反射机制获得类似动态语言的特性

# 二、java反射机制概述

1. Reflection（发射）是Java被视为动态语言的关键反射机制允许程序在执行期借助于reflection api取得任何类的内部信息，并能直接操作任意对象的内部属性及方法
   
   ```java
   Class c = Class.froName("java.lang.String")
   ```

2. 加载完类之后，在堆内存的方法区中就产生了一个Class类型的对象（一个类只有一个Class）对象，这个对象就包含了完整的类的结构信息。我们可以通过这个对象看到类的结构。这个对象就像一面镜子，透过这个镜子看到类的结构，称之为：反射
   
   - 正常方式：引入需要的“包类”名称——>通过new实例化——>取得实例化对象
   
   - 反射方式：实例化对象——>getClass()方法——>得到完整的“包类”名称

# 三、Java反射机制提供的功能

1. 在运行时判断任意一个对象所属的类

2. 在运行时构造任意一个类的对象

3. 在运行时判断任意一个类所具有的成员变量和方法

4. 在运行时获取泛型信息

5. 在运行时调用任意一个对象的成员变量和方法

6. 在运行时处理注解

7. 生成动态代理

8. ...

# 四、Java反射机制的优缺点

1. 优点：可以实现动态创建对象和编译，更加灵活

2. 缺点：对性能有影响。使用反射基本上是一种解释操作，我们可以告诉jvm，我们希望做什么并且它满足我们的要求。这类操作总是慢于直接执行相同的操作

# 五、反射相关的主要api

1. java.lang.Class：代表一个类

2. java.lang.reflect.Method：代表类的方法

3. java.lang.reflect.Field：代表类的成员变量

4. java.lang.reflect.Constructor：代表类的构造器
