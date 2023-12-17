# 一、反射操作泛型

1. Java采用泛型擦除的机制来引入泛型，Java中的泛型仅仅是给编译器javac使用的，确保数据的安全性和免去强制类型转换问题，但是一旦编译完成，所有和泛型有关的类型全部擦除

2. 为了通过反射操作这些类型，Java新增了ParameterizedType，GenericArrayType，TypeVariable和WildcardType几种类型来代表不能被归一到Class类中的类型但是又和原始类型齐名的类型
   
   - ParameterizedType：表示一种参数化类型，比如`Collection<String>`
   
   - GenericArrayType：表示一种元素类型是参数化类型或类型变量的数组类型
   
   - TypeVariable：是各种类型变量的公共父接口
   
   - WildcardType：代表一种通配符类型表达式

```java

```
