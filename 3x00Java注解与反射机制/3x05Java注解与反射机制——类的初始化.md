# 一、什么时候会发生类的初始化

1. 类的主动引用（一定会发生类的初始化）
   
   - 当虚拟机启动，先初始化main方法的所在类
   
   - new一个类的对象
   
   - 调用类的静态成员除了（final常量）和静态方法
   
   - 使用java.lang.reflect包的方法对类进行反射调用

2. 类的被动引用（不会发生类的初始化）
   
   - 当访问一个静态域时，只有真正声明这个域的类才会被初始化。
   - 通过数组定义类引用，不会触发此类的初始化（常量在链接阶段就存入调用类的常量池中了）

# 二、类加载器的作用

1. 类加载器的作用：将class文件字节码内容加载到内存中，并将这些静态数据转换为方法区的运行时数据结构，然后再堆中生成一个代表这个类的java.lang.Class对象，作为方法中类数据的访问入口

2. 类缓存：标准的JavaSE类加载器可以按要求查找类，但一旦某个类被加载到类加载器中，它将维持加载（缓存）一段时间。不过JVM垃圾回收机制可以回收这些Class对象

3. JVM规范定义类如下类型的类的加载器：
   
   - 引导类加载器：用C++编写的，是JVM自带的类加载器，负责java平台的核心库，用来装载核心类库。该加载器无法直接获取
   
   - 扩展类加载器：负责jre/lib/ext目录下的jar包或-D java.ext.dirs指定目录下的jar包装入工作库
   
   - 系统类加载器：负责java -classpath或-D java.class.path所指目录下的类与jar包装入工作，是最常用的加载器

# 三、双亲委派机制

1. Java的双亲委派机制是指在类加载时，如果一个类没有被加载到当前类加载器中，那么Java虚拟机会尝试加载这个类，并将其加载到当前类加载器中。如果当前类加载器无法加载这个类，那么Java虚拟机会尝试使用父类加载器来加载这个类。如果父类加载器也无法加载这个类，那么Java虚拟机会继续尝试使用祖先类加载器来加载这个类，直到找到能够加载这个类的类加载器为止。

2. 这个机制可以保证Java应用程序中类的加载顺序，避免类加载器之间的冲突。例如，如果应用程序中有两个不同的依赖库，其中一个依赖于另一个，那么如果没有双亲委派机制，那么可能会出现类加载器之间的冲突，导致应用程序无法正常运行。

3. 需要注意的是，双亲委派机制并不是一定能够解决所有类加载器之间的冲突。在某些情况下，如果两个类加载器都能够加载同一个类，那么可能会出现版本冲突或其他问题。因此，在使用双亲委派机制时，需要仔细考虑类加载器之间的依赖关系，以避免出现问题。
