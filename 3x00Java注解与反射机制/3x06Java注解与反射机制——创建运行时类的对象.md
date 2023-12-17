# 一、获取运行时类的完整结构

1. 通过反射获取运行时类的完整结构
   
   - Field、Method、Constructor、Superclass、Interface、Annotation
   
   - 实现的全部接口
   
   - 所继承的父类
   
   - 全部的构造器
   
   - 全部的方法
   
   - 全部的Field、注解
   
   - ...

2. 获取类的属性
   
   - getFields()。获取全部的public属性
   
   - getDeclaredFields()。获取全部的属性，包括属性类型、变量类型

3. 获取类的方法
   
   - getMethods()。获取全部的public方法
   
   - getDeclaredFields()。获取全部的方法

4. 获取类的构造器
   
   - getConstructors()。获取全部的public构造器
   
   - getDeclaredConstructors()。

# 二、动态创建对象执行方法

1. 通过反射动态创建
   
   - newInstance()构造对象。不加参数本质是调用了类的无参构造器
     
     ```java
     Class<?> c1 = Class.forName("org.reflection.User");
     User user = (User)c1.newInstance();
     System.out.println(user);
     ```
   
   - 通过构造器构造对象
     
     ```java
     Constructor declaredConstructor = c1.getDeclaredConstructor(String.class,int.class,int.class);
     ```
   
   - invoke。两个参数，第一个参数是要调用的对象，第二个参数是方法的值。
     
     - 若原方法无返回值，则返回null
     
     - 若原方法为静态方法，则形参Object obj可为null
     
     - 若原方法形参列表为空，则Object[] args为null
     
     - 若原方法声明为private，则需要调用此invoke()方法前显示调用方法对象的setAccessible(true)方法，关闭安全检测即可访问private方法
     
     ```java
     Object invoke(Object obj, Object ... args);
     
     setName.invoke(user,"小明");
     ```
   
   - 通过反射操作属性。不能直接操作私有属性，需要关闭程序的安全检测
     
     ```java
     User user4 = (User)c1.newInstance();
     Field name = c1.getDeclaredField("name");
     //关闭程序的安全检测
     name.setAccessiblle(true);
     name.set(user4,"小明");
     ```
   
   - 

2. 
