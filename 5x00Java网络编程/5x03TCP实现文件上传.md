1. 创建服务端
   
   - 创建服务
   
   - 监听客户端连接
   
   - 获取输入流
   
   - 文件输出
   
   - 通知客户端已接收完毕
     
     ```java
     package com.JavaSocket.Demo;
     
     import java.io.*;
     import java.net.ServerSocket;
     import java.net.Socket;
     
     public class TcpServerDemo02 {
         public static void main(String[] args) throws IOException {
             //1.创建服务
             ServerSocket serverSocket = new ServerSocket(9000);
             System.out.println("服务启动成功，端口9000");
             //2.监听客户端连接
             //阻塞式监听，会一直等待客户端连接
             Socket socket = serverSocket.accept();
             String clientIP = socket.getInetAddress().getHostAddress();
             System.out.println("客户端已连接,ip：" + clientIP);
             //3.获取输入流
             InputStream is = socket.getInputStream();
             //4.文件输出
             FileOutputStream fos = new FileOutputStream(new File("receive.png"));
             byte[] buffer = new byte[1024];
             int len;
             while((len=is.read(buffer))!=-1){
                 fos.write(buffer,0,len);
             }
             System.out.println("文件上传成功！");
     
             //5.通知客户端已接收完毕
             OutputStream os = socket.getOutputStream();
             os.write("success".getBytes());
             //6.关闭连接
             os.close();
             fos.close();
             is.close();
             socket.close();
             serverSocket.close();
             System.out.println("服务已关闭！");
         }
     }
     ```

2. 创建客户端
   
   - 创建一个socket连接
   
   - 创建一个输出流
   
   - 创建一个文件流，上传一个文件
   
   - 写出文件
   
   - 告诉服务端传输已结束
   
   - 确认服务端已接收
     
     ```java
     package com.JavaSocket.Demo;
     
     import java.io.*;
     import java.net.InetAddress;
     import java.net.Socket;
     import java.net.UnknownHostException;
     
     public class TcpClientDemo02 {
         public static void main(String[] args) throws IOException {
             //1.建立一个socket连接
             Socket socket = new Socket(InetAddress.getByName("127.0.0.1"), 9000);
             System.out.println("服务器连接成功！");
             //2.创建一个输出流
             OutputStream os = socket.getOutputStream();
     
             //3.文件流
             FileInputStream fils = new FileInputStream(new File("/Users/mac/Pictures/helloworld.png"));
     
             //4.写出文件
             byte[] buffer = new byte[1024];
             int len;
             while((len=fils.read(buffer))!=-1){
                 os.write(buffer,0,len);
             }
             //5.告诉服务端传输已结束
             socket.shutdownOutput();
             //6.确认客户端已接收
             InputStream inputStream = socket.getInputStream();
             ByteArrayOutputStream baos = new ByteArrayOutputStream();
             byte[] buffer2 = new byte[2014];
             int len2;
             while ((len2=inputStream.read(buffer2))!=-1){
                 baos.write(buffer2,0,len2);
             }
             System.out.println(baos.toString());
             //7.关闭资源
             baos.close();
             inputStream.close();
             fils.close();
             os.close();
             socket.close();
         }
     }
     ```

3. 先启动服务端，再启动客户端，然后可以看到项目的target目录下多出了一个receive.png文件
