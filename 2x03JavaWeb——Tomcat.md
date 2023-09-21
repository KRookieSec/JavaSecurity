# 一、Tomcat的目录结构

| 子目录 | 说明 |
|-------|------|
|bin|命令中心（启动命令，关闭命令……）|
|conf |配置中心（端口号，内存大小……）|
|lib|Tomcat 的库文件。Tomcat 运行时需要的 jar 包所在的目录。|
|logs|存放日志文件。|
|temp|存储临时产生的文件，即缓存。|
|webapps|存放项目的文件，web 应用放置到此目录下浏览器可以直接访问。|
|work|编译以后的 class 文件。|
# 二、Tomcat各目录的作用
1. bin目录用来存放 Tomcat 命令，主要分为两大类，一类是以.sh结尾的 Linux 命令，另一类是以.bat结尾的 Windows 命令。很多环境变量都在此处设置，例如 JDK 路径、Tomcat 路径等。
2. conf 目录主要是用来存放 Tomcat 的配置文件。下面是常用到的几个文件：
    - server.xml 用来设置域名、IP、端口号、默认加载的项目、请求编码等；
    - context.xml 用来配置数据源等；
    - tomcat-users.xml 用来配置和管理 Tomcat 的用户与权限；
    - web.xml 可以设置 Tomcat 支持的文件类型；
    - 在 Catalina 目录下可以设置默认加载的项目。 
3. lib。Tomcat 的库文件。Tomcat 运行时需要的 jar 包所在的目录。
4. logs。存放日志文件，logs 目录用来存放 Tomcat 在运行过程中产生的日志文件，清空该目录中的文件不会对 Tomcat 的运行带来影响。在 Windows 系统中，控制台的输出日志在 catalina.xxxx-xx-xx.log 文件中；在 Linux 系统中，控制台的输出日志在 catalina.out 文件中。
5. temp。存储临时产生的文件，即缓存。
6. webapps。存放项目的文件，web 应用放置到此目录下浏览器可以直接访问。webapps 目录用来存放应用程序（也就是通常所说的网站），当 Tomcat 启动时会去加载 webapps 目录下的应用程序，我们编写的 Servlet 程序就可以放在这里。Tomcat 允许以文件夹、war 包、jar 包的形式发布应用。
7. work。编译以后的 class 文件。work 目录用来存放 Tomcat 在运行时的编译文件（也即 class 字节码文件），例如 JSP 编译后的文件。清空 work 目录，然后重启 Tomcat，可以达到清除缓存的作用。

