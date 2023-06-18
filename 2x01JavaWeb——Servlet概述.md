# 一、Servlet概述
1. Servlet 是运行在服务器端的 Java 类，它可以接收来自客户端的请求并返回响应。Servlet 可以动态生成 HTML 页面、处理表单数据、响应 AJAX 请求等。Servlet 通常运行在 Web 服务器上，如 Tomcat、Jetty 等。Servlet 可以通过 Servlet API 进行访问和操作，其中包括 HttpServletRequest、HttpServletResponse、ServletContext 等类和接口。Servlet 是 Java Enterprise Edition（Java EE）技术的一部分，它为开发 Web 应用程序提供了强大的支持。
2. 严格来说，Servlet 只是一套 Java Web 开发的规范，或者说是一套 Java Web 开发的技术标准。只有规范并不能做任何事情，必须要有人去实现它。所谓实现 Servlet 规范，就是真正编写代码去实现 Servlet 规范提到的各种功能，包括类、方法、属性等。
3. Servlet 规范是开放的，除了 Sun 公司，其它公司也可以实现 Servlet 规范，目前常见的实现了 Servlet 规范的产品包括 Tomcat、Weblogic、Jetty、Jboss、WebSphere 等，它们都被称为“Servlet 容器”。Servlet 容器用来管理程序员编写的 Servlet 类。
# 二、Servlet接口
 1. Servlet接口是Java Servlet API中的核心接口之一，它定义了一种Java类，用于处理HTTP请求和响应。Servlet接口包含了以下几个方法：
    - init(ServletConfig config)：该方法在Servlet被创建时调用，用于初始化Servlet。其中，ServletConfig对象包含了Servlet的配置信息。
    - service(ServletRequest request, ServletResponse response)：该方法用于处理客户端的HTTP请求，并生成响应。其中，ServletRequest对象包含了客户端的请求信息，ServletResponse对象用于生成响应。
    - destroy()：该方法在Servlet被销毁时调用，用于释放资源。
    - getServletConfig()：该方法返回ServletConfig对象，包含了Servlet的配置信息。
    - getServletInfo()：该方法返回Servlet的描述信息。
 2. Servlet接口还包含了一些常量，如：
    - String METHOD_GET：表示HTTP请求的GET方法。
    - String METHOD_POST：表示HTTP请求的POST方法。
    - String HEADER_IF_MODIFIED_SINCE：表示HTTP请求头中的If-Modified-Since字段。
 3. Servlet接口是Java Servlet API中最基本的接口之一，所有的Servlet都必须实现该接口。同时，Servlet接口也是其他Servlet API中的一些接口的父接口，如GenericServlet、HttpServlet等。
 4. 直接实现 Servlet 接口比较麻烦，需要实现很多方法，所以 Servlet 规范又提供了两个抽象类，分别是 GenericServlet 类和 HttpServlet 类，它们都实现了 Servlet 接口的很多常用功能。和 GenericServlet 类相比，HttpServlet 类更加方便，所以实际开发中一般都继承自 HttpServlet 类。
    ``` java
    public class ServletDemo implements Servlet {
        //TODO:
    }
    ```
# 三、JSP
1. JSP是什么？ 
JSP是一种基于Java技术的服务器端网页开发技术，它允许开发人员将Java代码和HTML标记混合在一起来生成动态网页。JSP页面可以通过JavaBean、JSTL等技术访问数据库、执行业务逻辑等操作。 
2. JSP的优点 
    - JSP易于学习和使用，可以使用HTML和Java代码混合编写网页。 
    - JSP可以轻松地与JavaBean、JSTL等技术集成，访问数据库、执行业务逻辑等操作。 
    - JSP可以生成动态的HTML、XML、JSON等格式的网页。 
    - JSP可以通过标签库、自定义标签等技术扩展其功能。 
3. JSP的基本语法
    - 指令：用于指定JSP页面的属性和选项。 
    - 脚本元素：用于插入Java代码。 
    - 表达式：用于在HTML标记中插入Java表达式。 
    - 声明：用于声明Java方法和变量。 
4. JSP的执行过程。JSP页面在第一次请求时会被编译成Servlet，并将其保存在服务器上。当下一次请求到达时，服务器会直接调用该Servlet，生成响应并返回给客户端。 
5. JSP的开发工具。JSP可以使用各种Java开发工具进行开发，如Eclipse、IntelliJ IDEA等。这些工具提供了丰富的JSP开发功能和调试工具，可以大大提高JSP开发效率。 
# 四、JSP与Servlet的关系
JSP（JavaServer Pages）和Servlet是Java Web应用程序的两个核心技术。它们都是Java Servlet API的一部分，可以协同工作来生成动态网页。JSP和Servlet之间的关系如下： 
1. JSP本质上是Servlet。JSP页面在第一次请求时会被编译成Servlet，并将其保存在服务器上。当下一次请求到达时，服务器会直接调用该Servlet，生成响应并返回给客户端。因此，JSP本质上是Servlet的一种简化形式。 
2. Servlet可以生成动态的HTML，而JSP可以更方便地生成动态的HTML。Servlet可以使用Java代码来生成动态的HTML，但需要将Java代码和HTML标记混合在一起。而JSP可以更方便地将Java代码和HTML标记混合在一起来生成动态的HTML。 
3. JSP和Servlet可以相互调用。JSP页面可以使用JavaBean、JSTL等技术来访问数据库、执行业务逻辑等操作。而Servlet可以通过调用JSP页面来生成动态的HTML。因此，JSP和Servlet可以相互调用，实现更复杂的Web应用程序。 
4. 总之，JSP和Servlet是Java Web应用程序的两个核心技术，它们可以协同工作来生成动态网页。JSP本质上是Servlet的一种简化形式，可以更方便地生成动态的HTML。同时，JSP和Servlet可以相互调用，实现更复杂的Web应用程序。