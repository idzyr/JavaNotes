# 循环结构

顺序结构的程序语句只能被执行一次。如果您想要同样的操作执行多次,，就需要使用循环结构。



## while循环

while是最基本的循环，它的结构为：适合不知道要循环几次的代码使用。

**格式；**

只要布尔表达式为 true，循环就会一直执行下去。

```java
while( 布尔表达式 ) {
  //循环内容
}
```

**实例；**

```java
public class Test {
   public static void main(String args[]) {
      int x = 10;
      //如果x小于20则一致为真循环中的代码会一只执行
      while( x < 20 ) {
          //往控制台输出内容
         System.out.print("value of x : " + x );
         x++;	//改变x值作为循环结束条件
         System.out.print("\n");
      }
   }
}
```

## do…while 循环
对于 while 语句而言，如果不满足条件，则不能进入循环。但有时候我们需要即使不满足条件，也至少执行一次。

do…while 循环和 while 循环相似，不同的是，do…while 循环至少会执行一次。

**格式；**

```java
do {
       //代码语句
}while(布尔表达式);
```

> **注意；**
>
> ​	布尔表达式在循环体的后面，所以语句块在检测布尔表达式之前已经执行了。 如果布尔表达式的值为 true，则语句块一直执行，直到布尔表达式的值为 false。



**实例；**

```java
public class Test {
   public static void main(String args[]){
      int x = 10;
       // 先执行代买块中的语句。
      do{
         System.out.print("value of x : " + x );
         x++;
         System.out.print("\n");
      }while( x < 20 ); //判断条件是否成立
   }
}
```



## for循环

虽然所有循环结构都可以用 while 或者 do...while表示，但 Java 提供了另一种语句 —— for 循环，使一些循环结构变得更加简单。

**格式；**

for循环执行的次数是在执行前就确定的。

```java
for(初始化循环控制变量; 布尔表达式; 更新循环控制变量) {
    //代码语句或叫循环体
}
```

**关于for循环的执行流程；**

1. 最先执行**初始化**步骤。可以声明一种类型，但可初始化一个或多个循环控制变量，也可以是空语句。

2. 然后，检测**布尔表达式**的值。
   - 如果为 true，循环体被执行。
   - 如果为false，循环终止，开始执行循环体后面的语句。

3. 执行一次循环体后，**更新**循环控制变量。

4. 再次**检测**布尔表达式。循环执行上面（除了1步骤）的过程。

**实例；**

```java
public class Test {
   public static void main(String args[]) {
 
      for(int x = 10; x < 20; x = x+1) {
         System.out.print("value of x : " + x );
      }
      /*--------------------------------------*/ 
      /*
      	1. 先执行int x = 10;为循环控制变量赋值。
      	2. x < 20; 对布尔表达式进行判断。
      		如果为true 那么就执行
      			System.out.print("value of x : " + x );
      		如果为false  循环终止，开始执行循环体后面的语句就不在执行for里面的语句了。
      	3.  x+1 更新循环控制变量。
        4. 再次执行布尔表达式按2 3 4 步骤顺序执行。只到布尔表达式为false才结束循环。
      
      */
       
   }
}
```



## 增强for循环

**特点；**

1. 也是使用的迭代器原理。只是使用了for的格式简化迭代器的书写。
2. 专门用来遍历数组和单列集合。
3. 只能遍历不可以增删除数组或集合。

Java5 引入了一种主要用于数组的增强型 for 循环。用来方便遍历数组和集合。

Java 增强 for 循环语法格式如下:

```java
for(声明语句 : 表达式)
{
   //代码句子
}
```

- 声明语句  用来保存临时从数组中取出的元素这个语句的类型要和数组中的元素相同。
- 表达式 通常是被遍历的数组。

**实例；**

```java
int[] arrayDemo = new int[](1,2,3,4,5);

for(int temp : arrayDemo){
    System.out.println(temp);
}
```

结果；

```
1
2
3
4
5
```



## break关键字

break 主要用在循环语句或者 switch 语句中，用来跳出整个语句块。

break 跳出**最里层的循环**，并且继续执行该循环下面的语句。

**语法；**

```java
break;
```

**实例；**

```java
public class Test {
   public static void main(String args[]) {
      int [] numbers = {10, 20, 30, 40, 50};
 
      for(int i = 0; i < numbers.length; i++ ) {
         // x 等于 30 时跳出循环
         if( numbers[i] == 30 ) {
            break;
         }
          //如果执行了break那么这里的语句将不会执行
         System.out.print( numbers[i] );
         System.out.print("\n");
      }
   }
}
```

执行结果；

```
10
20
```

## continue关键字 

continue 适用于任何循环控制结构中。作用是让程序立刻跳转到下一次循环的迭代。也就是跳出本次循环而不结束整个循环语句。

- 在 for 循环中，continue 语句使程序立即跳转到更新语句。

- 在 while 或者 do…while 循环中，程序立即跳转到布尔表达式的判断语句。

**语法；**

```java
continue;
```

**实例；**

```java
public class Test {
   public static void main(String args[]) {
      int [] numbers = {10, 20, 30, 40, 50};
 
      for(int i; i < numbers.length; i++ ) {
         if(numbers[i] == 30 ) {
       	 	continue; //结束本次循环
         }
         System.out.print( numbers[i] );
         System.out.print("\n");
      }
   }
}
```

结果；

```
10
20
40
50
```