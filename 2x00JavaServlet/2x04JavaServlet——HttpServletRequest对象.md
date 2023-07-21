# 一、HttpServletRequest对象概述
1. HttpServletRequest对象主要用来接收客户端发送过来的请求信息，如请求参数、请求头等，service方法中形参接收的是HttpServletRequest接口的实例化对象，表示该对象主要应用在HTTP协议上，该对象是由Tomcat封装好传递过来
# 二、HttpServletRequest接收请求
1. 常用方法

| 方法名 | 作用 |
| ----- | ----- |
| getRequestURL() | 获取客户端发出请求时的完整URL |
| getRequestURI() | 获取请求行中的资源名称部分（项目名称开始) |
| getQueryString() | 获取请求行中的参数部分 |
| getMethod() | 获取客户端请求方式 |
| getProtocol | 获取HTTP版本号 |

2. 