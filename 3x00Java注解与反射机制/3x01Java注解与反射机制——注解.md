# 一、什么是注解

1. 注解（Anotation）是从JDK5.0开始引入的新技术

2. 注解的作用
   
   - 不是程序本身，可以对程序作出解释，这一点和注释没什么区别
   
   - 可以被其他程序（如编译器等）读取

3. 注解的格式：注解是以“@注释名”在代码中存在的，还可以添加一些参数值
   
   ```java
   @SuppressWarnings(value="unchecked")
   ```

4. 注解可以在哪些地方使用：可以附加在package、class、method、field等上面，相当于给它们添加了额外的辅助信息，我们可以通过反射机制编程实现对这些元数据的访问

# 二、内置注解

1. `@Override`：定义在java.lang.Override中，此注释只适用于修辞方法，表示一个方法声明打算重写超累中的

2. `@Deprecated`：定义在java.lang.Deprecated中，此注释可以用于修辞方法、属性、类，表示不鼓励程序使用这样的元素，通常因为它很危险或存在更好的选择

3. `@SuppressWarnings`：定义在java.lang.SuppressWarnings中，用来抑制编译时的警告信息。与前两个注释有所不同，需要添加一个参数才可以正确使用，这些参数都是定义好的
   
   - all
   
   - unchecked
   
   - value={"unchecked","deprecation"}
   
   - ...

# 三、元注解

1. 云注解的作用就是负责注解其他注解，java定义了4个标准的meta-annotation类型，它们被用来提供对其他annotation类型作解释说明

2. 这些类型和它们所支持的类在java.lang.annotation包中可以找到`@Target`、`@Retention`、`@Documented`、`@Inherited`
   
   - `@Target`：用于描述注解的使用范围，即被描述的注解可以用于哪些地方
   
   - `@Retention`：表示需要在什么级别保存该注释信息，用于描述注解的生命周期（SOURCE < CLASS < RUNTIME）
   
   - `@Document`：说明该注解将被包含在javadoc中
   
   - `@Inherited`：说明子类可以继承父类中的该注解

# 四、自定义注解

1. 使用`@interface`自定义注解时，自动继承了java.lang.annotation.Annotation接口

2. 分析
   
   - `@interface`用来声明一个注解，格式：`public @interface 注解名{定义内容}`
   
   - 其中的每一个方法实际上是声明了一个配置参数
   
   - 方法的名称就是参数的名称
   
   - 返回值类型就是参数的类型，返回值只能是基本类型：Class、String、enum
   
   - 可以通过defualt来声明参数的默认值
   
   - 如果只有一个参数成员，一般参数名为value
   
   - 注解元素必须要有值，我们定义注解元素师，经常使用空字符作为默认值
     
     ```java
     @Target({ElementType.TYPE,ElementTYpe.METHOD})
     //允许在类、方法使用注解
     @Retention(RetetionPolicy.RUNTIME)
     @interface MyAnnotation{
         //注解的参数：参数类型 + 参数名()；
         String name() defualt "";
         int age() defualt 0;
         int id() defualt -1;//如果默认值为-1代表不存在
         String[] schools defualt{"java"}; 
     }
     ```

3. 
