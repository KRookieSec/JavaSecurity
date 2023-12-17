1. 发送方
   
   ```java
   package com.JavaSocket.chat;
   
   import java.io.BufferedReader;
   import java.io.InputStreamReader;
   import java.net.DatagramPacket;
   import java.net.DatagramSocket;
   import java.net.InetSocketAddress;
   import java.net.SocketException;
   
   public class UdpSend {
       public static void main(String[] args) throws Exception {
           //开放端口
           DatagramSocket socket = new DatagramSocket(9000);
           while (true){
               //准备数据，利用System.in从控制台输入
               BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));
               //将输入的数据转换为字节流
               String data = bufferedReader.readLine();
               byte[] datas = data.getBytes();
               //发送数据
               DatagramPacket packet = new DatagramPacket(datas,0,datas.length,new InetSocketAddress("localhost",9090));
               socket.send(packet);
               if(data.equals("bye")){
                   break;
               }
           }
           //关闭连接
           socket.close();
   
       }
   }
   
   ```

2. 接收方
   
   ```java
   
   ```


