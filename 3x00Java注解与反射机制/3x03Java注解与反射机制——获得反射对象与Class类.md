# 一、Class类

1. 在Object类中定义了一下方法，此方法将被所有子类继承，该方法返回值类型是一个Class类，此类是Java反射机制的源头，实际上所谓反射机制从程序的运行结果来看也很好理解，即：可以通过对象反射求出类的名称
   
   ```java
   public final Class getClass()
   ```

2. 对于每个类而言，jre都为其保留一个不变的Class类型的对象。一个Class对象包含了特定某个结构（class/interface/enum/annotation/primitive type/void/[]）的有关信息
   
   - Class本身也是一个类
   
   - Class对象只能由系统建立对象
   
   - 一个加载的类在jvm中只会有一个Class实例
   
   - 一个Class对象对应的是一个加载到jvm中的一个.class文件
   
   - 每个类的实例都会记得自己是由哪个Class实例所生成
   
   - 通过Class可以完整地得到一个类中的所有被加载的结构
   
   - Class类是Reflection的根源，针对任何你想动态加载、运行的类，唯有先获得相应的Class对象

# 二、Class类的常用方法

| 方法名                                      | 功能说明                               |
| ---------------------------------------- | ---------------------------------- |
| static ClassforName(String name)         | 返回指定类名name的Class对象                 |
| Object newInstance()                     | 调用缺省构造函数，返回Class对象的一个实例            |
| getName()                                | 返回此Class对象所表示的实体（类、接口、数组类或void）的名称 |
| Class getSuperClass()                    | 返回当前Class对象的父类的Class对象             |
| Class[] getinterfaces()                  | 获取当前Class对象的接口                     |
| ClassLoader getClassLoader()             | 返回该类的类加载器                          |
| Construtor[] getConstructors()           | 返回一个包含某些Constructor对象数组            |
| Method getMothed(String name, Class.. T) | 返回一个Method对象，此对象的形参类型为paramType    |
| Field[] getDeclaredFields()              | 返回Field对象的一个数组                     |

# 三、获取Class类的实例

1. 若已知具体的类，通过类的class属性获取，该方法最为可靠，程序性能最高
   
   ```java
   Class clazz = Person.class;
   ```

2. 已知某个类的实例，调用该实例的getClass()方法获取Class对象
   
   ```java
   Class clazz = person.getClass();
   ```

3. 已知一个类的全名，且该类在类路径下，可通过Class类的静态方法forName()获取，可能抛出ClassNotFoundException
   
   ```java
   Class clazz = Class.forName("demo01.Student");
   ```

4. 内置基本数据类型可以用类名.TYPE

5. 还可以利用ClassLoader

# 四、所有类型的Class对象

1. 哪些类型可以有Class对象
   
   - class：外部类，成员（成员内部类，静态内部类），局部内部类，匿名内部类
   
   - interface：接口
   
   - []：数组
   
   - enum：枚举
   
   - annotation：注解`@interface`
   
   - primitivate type：基本数据类型
   
   - void

2. 
