# 一、爬虫生命周期
1. 页面下载。
2. 链接提取
3. URL管理
4. 内容抽取及持久化
# 二、Java爬虫用到的技术
1. 模拟浏览器。HttpClient
2. html解析。jsoup
# 三、创建java爬虫项目
1. eclipse创建一个maven项目
2. 修改poc.xml文件，添加依赖，将jsoup、httpcore、httpclient、commons-io添加进去
	``` xml
	<dependency>
		<groupId>org.jsoup</groupId>
		<artifactId>jsoup</artifactId>
		<version>1.16.1</version>
	</dependency>
	<dependency>
		<groupId>org.apache.httpcomponents</groupId>
		<artifactId>httpcore</artifactId>
		<version>4.4.16</version>
	</dependency>
	<dependency>
		<groupId>org.apache.httpcomponents</groupId>
		<artifactId>httpclient</artifactId>
		<version>4.5.14</version>
	</dependency>
	<dependency>
		<groupId>commons-io</groupId>
		<artifactId>commons-io</artifactId>
		<version>20030203.000550</version>
	</dependency>
	```
3. 在src下新建java目录用于存放java源文件，在这里面新建java类