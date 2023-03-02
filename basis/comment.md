# 注释



## 单行注释

```java
// 我是被注释的内容
```



## 多行注释

```java
/*
	我是被注释的内容
	……
*/
```



## 文档注释

文档注释以`/**`开头，并以*/结束，可以通过 Javadoc 生成 API 帮助文档，Java 帮助文档主要用来说明类、成员变量和方法的功能。

```java
/**
* @author C语言中文网
* @version jdk1.8.0
*/
public class Test{
    /**
     * 求输入两个参数范围以内整数的和
     * @param n 接收的第一个参数，范围起点
     * @param m 接收的第二个参数，范围终点
     * @return 两个参数范围以内整数的和
     */
    public int add(int n, int m) {
        int sum = 0;
        for (int i = n; i <= m; i++) {
            sum = sum + i;
        }
        return sum;
    }
} 
```



文档注释只放在类、接口、成员变量、方法之前，因为 Javadoc 只处理这些地方的文档注释，而忽略其它地方的文档注释。

API 帮助文档相当于产品说明书，而说明书只需要介绍那些供用户使用的部分，所以 Javadoc 默认只提取 public、protected 修饰的部分。如果要提取 private 修饰的部分，需要使用 -private。

### Javadoc标签

Javadoc 工具可以识别文档注释中的一些特殊标签，这些标签一般以`@`开头，后跟一个指定的名字，有的也以`{@`开头，以`}`结束。Javadoc 可以识别的标签如下表所示：

| 标签          | 描述                                                   | 示例                                                         |
| ------------- | ------------------------------------------------------ | ------------------------------------------------------------ |
| @author       | 标识一个类的作者，一般用于类注释                       | @author description                                          |
| @deprecated   | 指名一个过期的类或成员，表明该类或方法不建议使用       | @deprecated description                                      |
| {@docRoot}    | 指明当前文档根目录的路径                               | Directory Path                                               |
| @exception    | 可能抛出异常的说明，一般用于方法注释                   | @exception exception-name explanation                        |
| {@inheritDoc} | 从直接父类继承的注释                                   | Inherits a comment from the immediate surperclass.           |
| {@link}       | 插入一个到另一个主题的链接                             | {@link name text}                                            |
| {@linkplain}  | 插入一个到另一个主题的链接，但是该链接显示纯文本字体   | Inserts an in-line link to another topic.                    |
| @param        | 说明一个方法的参数，一般用于方法注释                   | @param parameter-name explanation                            |
| @return       | 说明返回值类型，一般用于方法注释，不能出现再构造方法中 | @return explanation                                          |
| @see          | 指定一个到另一个主题的链接                             | @see anchor                                                  |
| @serial       | 说明一个序列化属性                                     | @serial description                                          |
| @serialData   | 说明通过 writeObject() 和 writeExternal() 方法写的数据 | @serialData description                                      |
| @serialField  | 说明一个 ObjectStreamField 组件                        | @serialField name type description                           |
| @since        | 说明从哪个版本起开始有了这个函数                       | @since release                                               |
| @throws       | 和 @exception 标签一样.                                | The @throws tag has the same meaning as the @exception tag.  |
| {@value}      | 显示常量的值，该常量必须是 static 属性。               | Displays the value of a constant, which must be a static field. |
| @version      | 指定类的版本，一般用于类注释                           | @version info                                                |

对两种标签格式的说明：

- @tag 格式的标签（不被`{ }`包围的标签）为块标签，只能在主要描述（类注释中对该类的详细说明为主要描述）后面的标签部分（如果块标签放在主要描述的前面，则生成 API 帮助文档时会检测不到主要描述）。
- {@tag} 格式的标签（由`{ }`包围的标签）为内联标签，可以放在主要描述中的任何位置或块标签的注释中。


Javadoc 标签注意事项：

- Javadoc 标签必须从一行的开头开始，否则将被视为普通文本。
- 一般具有相同名称的标签放在一起。
- Javadoc 标签区分大小写，代码中对于大小写错误的标签不会发生编译错误，但是在生成 API 帮助文档时会检测不到该注释内容。

### Javadoc命令

Javadoc 用法格式如下：

javadoc [options] [packagenames] [sourcefiles]

对格式的说明：

- options 表示 Javadoc 命令的选项；
- packagenames 表示包名；
- sourcefiles 表示源文件名。


在 cmd（命令提示符）中输入`javadoc -help`就可以看到 Javadoc 的用法和选项（前提是安装配置了JDK），下面列举 Javadoc 命令的常用选项：



| 名称                | 说明                                     |
| ------------------- | ---------------------------------------- |
| -public             | 仅显示 public 类和成员                   |
| -protected          | 显示 protected/public 类和成员（默认值） |
| -package            | 显示 package/protected/public 类和成员   |
| -private            | 显示所有类和成员                         |
| -d <directory>      | 输出文件的目标目录                       |
| -version            | 包含 @version 段                         |
| -author             | 包含 @author 段                          |
| -splitindex         | 将索引分为每个字母对应一个文件           |
| -windowtitle <text> | 文档的浏览器窗口标题                     |

输入`javadoc -author -version Test.java`











