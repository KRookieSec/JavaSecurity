1. udp没有服务端和客户端的概念，只有发送端和接收端的区分，
   
   - 建立socket连接
   
   - 创建数据包
   
   - 发送包
   
   - 关闭流
     
     ```java
     package com.JavaSocket.UDP;
     
     import java.io.IOException;
     import java.net.*;
     import java.nio.charset.StandardCharsets;
     
     public class UdpClient01 {
         public static void main(String[] args) throws Exception {
             //1.建立socket连接
             DatagramSocket socket = new DatagramSocket();
             //2.建个包
             String msg = "hello,java!";
             //服务器地址和端口
             InetAddress localhost = InetAddress.getByName("localhost");
             int port = 9090;
             //参数：数据、数据的长度、发送目标
             DatagramPacket packet = new DatagramPacket(msg.getBytes(),0,msg.getBytes().length,localhost,port);
             //3.发送包
             socket.send(packet);
             //4.关闭流
             socket.close();
         }
     }
     ```

2. 接收端
   
   - 开放端口
   
   - 接收数据
   
   - 处理数据
   
   - 关闭连接
     
     ```java
     
     ```

3. 
