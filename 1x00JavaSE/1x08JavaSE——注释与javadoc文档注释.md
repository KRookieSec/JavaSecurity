# 一、单行注释与多行注释
1. 单行注释
	``` Java
	//单行注释
	```
2. 多行注释
	``` Java
	/*
	 *多行注释
	 */
	```
# 二、javadoc文档注释
1. javadoc标签

|标签|描述|示例|
|---|---|---|
|@author|标识一个类的作者，一般用于类注释|@author description|
|@deprecated|指名一个过期的类或成员，表明该类或方法不建议使用|@deprecated description|
|{@docRoot}|指明当前文档根目录的路径|Directory Path|
|@exception|可能抛出异常的说明，一般用于方法注释|@exception exception-name explanation|
|{@inheritDoc}|从直接父类继承的注释|Inherits a comment from the immediate surperclass.|
|{@link}|插入一个到另一个主题的链接|{@link name text}|
|{@linkplain}|插入一个到另一个主题的链接，但是该链接显示纯文本字体|Inserts an in-line link to another topic.|
|@param|说明一个方法的参数，一般用于方法注释|@param parameter-name explanation|
|@return|说明返回值类型，一般用于方法注释，不能出现再构造方法中|@return explanation|
|@see|指定一个到另一个主题的链接|@see anchor|
|@serial|说明一个序列化属性|@serial description|
|@serialData|说明通过 writeObject() 和 writeExternal() 方法写的数据|@serialData description|
|@serialField|说明一个 ObjectStreamField 组件|@serialField name type description|
|@since|说明从哪个版本起开始有了这个函数|@since release|
|@throws|和 @exception 标签一样.|The @throws tag has the same meaning as the @exception tag.|
|{@value}|显示常量的值，该常量必须是 static 属性。|Displays the value of a constant, which must be a static field.|
|@version|指定类的版本，一般用于类注释|@version info|
2. javadoc文档注释
	``` Java
	/**
	 *javadoc文档注释
	 *@author 作者
	 *@version 版本
	 */
	```
3. javadoc命令
	- 语法格式
		``` Java
		javadoc [options] [packagenames] [sourcefiles]
		如：
		javadoc -author -version Test.java
		```
	- options 表示 Javadoc 命令的选项
	- packagenames 表示包名
	- sourcefiles 表示源文件名
4. javadoc常用命令选项

|名称|说明|
|---|---|
|-public|仅显示 public 类和成员|
|-protected|显示 protected/public 类和成员（默认值）|
|-package|显示 package/protected/public 类和成员|
|-private|显示所有类和成员|
|-d \<directory>|输出文件的目标目录|
|-version|包含 @version 段|
|-author|包含 @author 段|
|-splitindex|将索引分为每个字母对应一个文件|
|-windowtitle \<text>|文档的浏览器窗口标题|
