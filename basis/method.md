# 方法

使用方法的作用是我们可以减少代码书写量更好的重用代码。同一个功能我们只需要书写一次就可以多出调用。



## 方法定义

**语法；**

```java
public static void 方法名称(){
    //方法体
};
```

> **注意；**
>
> 1. 方法要从类里面定义（类的大括号中）
> 2. 带有static的是普通方法，可以直接通过类名调用，反之是成员方法不能直接通过类名调用。
> 3. 万法定义位置先后顺序无所谓。
> 4. 方法的定义不能产生嵌套包含关系。
> 5. 方法定义好了之后，不会自动执行的。需要被调用才会执行。



**实例；**

```java
public class TestClass{
    public static void main(String[] args){
        functionDemo(); //调用测试方法
    }
    /**
        定义一个名为functionDemo无返回值类型的方法。
     */
    public static void functionDemo(){
       System.out.println("方法调用测试");
    }
}
```



## 带返回值方法

**语法；**

````java
 修饰符 返回值类型 方法名(){
       //方法体
     return 返回数据给调用出;
}
````

**实例；**

```java
public class TestClass{
    public static void main(String[] args){
        //调用测试方法接受返回值。
        String fnData = functionDemo();
       System.out.println(fnData);
    }
    /**
        定义带返回值方法
     */
    public static String functionDemo(){
        return "被返回的数据";
    }
}
```



> **注意事项；**
>
> - 修饰符：现阶段的固定写法，public static
>
> - 返回值类型：也就是方法最终产生的数据结果是什么类型
> - 方法名称：方法的名字，规则和变量一样，小驼峰
> - 参数类型：进入方法的数据是什么类型
> - 参数名称：进入方法的数据对应的变量名称P5：参数如果有多个，使用逗号进行分隔
> - 方法体：方法需要做的事情，若干行代码
> - return：两个作用，第一停止当前方法，第二将后面的返回值还给调用处返回值：也就是方法执行后最终产生的数据结果，注意：return后面的“返回值”，必须和方法名称前面的“返回值类型”，保持对应。



## 方法重载

 同名方法实现多个功能。

**构成重载的条件；**

1. 参数个数不同

2. 参数类型不同

3. 参数的多类型顺序不同

**重载与下列因素无关：**

1. 与参数的名称无关
2. 与方法的返回值类型无关

**重载示例；**

参数个数不同重载；

```java
public class TestClass{
    public static void main(String[] args){
        add(1,4);
        add(1,4,6); //调用重载
    }
    
    public static void add(int a ,int b){
        System.out.println(a+b);
    }
    /**
        add 方法重载
     */
    public static void add(int a,int b,int c){
        System.out.println(a+b+c);
    }
}
```

参数类型不同；

```java
public class TestClass{
    public static void main(String[] args){
        add(1,4);
        add(1,8L); //调用重载
    }
    
    public static void add(int a ,int b){
        System.out.println(a+b);
    }
    /**
        add 方法重载
     */
    public static void add(int a,long b){
        System.out.println(a+b);
    }
}
```

参数多类型顺序不同；

```java
public class TestClass{
    public static void main(String[] args){
        add(1,4);
        add(1L,8); //调用重载
    }
    
    public static void add(int a ,int b){
        System.out.println(a+b);
    }
    /**
        add 方法重载
     */
    public static void add(long b,int a){
        System.out.println(a+b);
    }
}
```





## 注意事项

1. 方法应该定义在类当中，但是不能在方法当中再定义方法。不能嵌套。
2. 方法定义的前后顺序无所谓。
3. 方法定义之后不会执行，如果希望执行，一定要调用：单独调用、打印调用、赋值调用。
4. 如果方法有返回值，那么必须写上`return`返回值；”，不能没有。
5. return后面的返回值数据，必须和方法的返回值类型，对应起来。
6. 对于一个`void`没有返回值的方法，不能写return后面的返回值，只能写return自己。
7. 对于`void`方法当中最后一行的return可以省略不写。
8. 一个方法当中可以有多个return语句，但是必须保证同时只有一个会被执行到，两个return不能连写



