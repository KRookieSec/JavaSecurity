# 一、Servlet生命周期概述

1. Servlet没有main方法，不能独立运行，他的处理完全由Servlet引擎来调度控制。
2. 所谓的生命周期是指Servlet容器从创建到销毁的整改过程。
   
   # 二、Servlet的执行过程
3. Servlet初始化。当请求到达容器时，容器查找servlet对象是否存在，如果不存在创建示例并调用init()方法进行初始化。
4. Servlet调用service()方法处理客户端的请求，在整个生命周期中可以多次被调用，一球请求方式起来调用doGet()或doPost()方法。
5. Servlet销毁前调用destrory()方法
6. JVM垃圾回收期进行垃圾回收
   
   # 三、Servlet的生命周期方法
7. init()方法。在Servlet实例创建后执行
   
   ```java
   public void init(ServletConfig config) throws ServletException{
   System.out.println("实例创建");
   }
   ```
8. service()方法。每次有请求到达某个Servlet方法时执行，用来处理请求。
   
   ```java
   public void service(HttpServletRequest req,HttpServletRespone resp) throws ServletException, IOException{
     System.out.println("请求处理");
   }
   ```
9. destroy()方法，Servlet实例销毁时执行
   
   ```java
   public void destroy(){
    System.out.println("实例销毁");
   }
   ```
10. 
