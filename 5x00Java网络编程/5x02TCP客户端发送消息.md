1. 新建一个服务端，监听并处理指定端口的消息
   
   ```java
   package com.JavaSocket.Demo;
   
   import java.io.ByteArrayOutputStream;
   import java.io.IOException;
   import java.io.InputStream;
   import java.net.ServerSocket;
   import java.net.Socket;
   
   public class testserver {
       public static void main(String[] args) {
           // 使用19999端口接收来自客户度的消息，并打印客户度发送的消息
           ServerSocket server = null;
           try {
               server = new ServerSocket(19999);
               System.out.println("Server is running on port 19999");
               Socket socket = server.accept();
               System.out.println("客户端已连接");
               InputStream is = socket.getInputStream();
               ByteArrayOutputStream bs = new ByteArrayOutputStream();
               byte[] buffer = new byte[1024];
               int len;
               while ((len = is.read(buffer)) != -1) {
                   bs.write(buffer, 0, len);
               }
               System.out.println("Received message: " + bs.toString());
           } catch (IOException e) {
               throw new RuntimeException(e);
           }
   
       }
   }
   ```

2. 新建一个客户端，连接到服务端并发送消息
   
   ```java
   package com.JavaSocket.Demo;
   
   import java.io.IOException;
   import java.io.OutputStream;
   import java.net.Socket;
   
   public class testclient {
       public static void main(String[] args) {
           try {
               Socket socket = new Socket("127.0.0.1", 19999);
               OutputStream os = socket.getOutputStream();
               os.write("hello,java".getBytes());
               os.flush(); // 添加这一行来刷新输出流
               os.close();
               socket.close();
           } catch (IOException e) {
               throw new RuntimeException(e);
           }
       }
   }
   ```

3. 先运行服务端，再运行客户端，在服务端的终端可以看到成功建立连接并打印消息
   
   ```shell
   Server is running on port 19999
   客户端已连接
   Received message: hello,java
   ```
