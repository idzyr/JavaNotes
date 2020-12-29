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
 public static 返回值类型 方法名(){
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



