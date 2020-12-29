# 条件语句





## if

当条件成立时布尔表达式为true执行

**语法；**

```java
if(布尔表达式)
{
   //如果布尔表达式为true将执行的语句
}
```



**实例；**

```java
public class Test {
 
   public static void main(String args[]){
      int x = 10;
 	// 如果x小于20条件成立执行if中的代码。
      if( x < 20 ){
         System.out.print("这是 if 语句");
      }
   }
}
```



## if...else

当if条件为false时执行else中的语句。

**语法；**

```java
if(布尔表达式){
   //如果布尔表达式的值为true
}else{
   //如果布尔表达式的值为false
}
```



**实例；**

```java
public class Test {
 
   public static void main(String args[]){
      int x = 30;
 	//当if条件不成立时执行else中的语句
      if( x < 20 ){
         System.out.print("这是 if 语句");
      }else{
         System.out.print("这是 else 语句");
      }
   }
}
```



## if...else if...else 

if 语句后面可以跟 else if…else 语句，这种语句可以检测到多种可能的情况。

使用 if，else if，else 语句的时候，需要注意。

> **注意；**
>
> - if 语句至多有 1 个 else 语句，else 语句在所有的 else if 语句之后。
> - if 语句可以有若干个 else if 语句，它们必须在 else 语句之前。
> - 一旦其中一个 else if 语句检测为 true，其他的 else if 以及 else 语句都将跳过执行。



**语法；**

```java
if(布尔表达式 1){
   //如果布尔表达式 1的值为true执行代码
}else if(布尔表达式 2){
   //如果布尔表达式 2的值为true执行代码
}else if(布尔表达式 3){
   //如果布尔表达式 3的值为true执行代码
}else {
   //如果以上布尔表达式都不为true执行代码
}
```



**实例；**

```java
public class Test {
   public static void main(String args[]){
      int x = 30;
 
      if( x == 10 ){
         System.out.print("Value of X is 10");
      }else if( x == 20 ){
         System.out.print("Value of X is 20");
      }else if( x == 30 ){
         System.out.print("Value of X is 30");
      }else{
         System.out.print("这是 else 语句");
      }
   }
}
```

结果；

```
Value of X is 30
```

## 嵌套的 if…else

使用嵌套的 if…else 语句是合法的。也就是说你可以在另一个 if 或者 else if 语句中使用 if 或者 else if 语句。

**语法；**

```java
if(布尔表达式 1){
   ////如果布尔表达式 1的值为true执行代码
   if(布尔表达式 2){
      ////如果布尔表达式 2的值为true执行代码
   }
}
```

**实例；**

```java
public class Test {
 
   public static void main(String args[]){
      int x = 30;
      int y = 10;
 
      if( x == 30 ){
         if( y == 10 ){
             System.out.print("X = 30 and Y = 10");
          }
       }
    }
}
```

结果；

```'
X = 30 and Y = 10
```



