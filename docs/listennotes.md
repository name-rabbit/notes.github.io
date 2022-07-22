



# 听课笔记

## OOP

面向对象的程序设计

面向对象三大特征：封装、继承、多态

## 继承

解决代码复用问题

父类的private属性不能继承，只能通过getter和setter方法取值和赋值

类名大写区分创建对象时的变量名

## 多态

主要是针对行为而不是属性，一个行为在不同条件下有不同的执行结果

Electricityequipment ee = new Electricityequipment();

Mobile m =(Mobile)ee;

//这样是错误的映射错误	 #cast转换

（可以这样理解子类是对父类的扩展和重写，因此父类是没有子类的特性，强转不了）

### 向上转型

是自动向上提升的，就像byte->int自动提升一样

### 向下转型

![image-20220715093000292](img/%E5%90%91%E4%B8%8B%E8%BD%AC%E5%9E%8B.png)

![image-20220715111934318](img/%E5%A4%9A%E6%80%81%E6%89%A7%E8%A1%8C%E9%A1%BA%E5%BA%8F.png)

### 重载和重写的区别

==（数字大小比较，引用类型比较地址值）、equals（字符串比较），但他们两对于对象判断为false,这里重写（为了比较某些属性）了父类的equals方法

![image-20220715100944841](img/%E9%87%8D%E5%86%99.png)

![image-20220715100532712](img/%E9%87%8D%E5%86%99%E7%88%B6%E7%B1%BB%E6%96%B9%E6%B3%95.png)

![image-20220715100759235](img/%E9%87%8D%E5%86%99%E6%89%93%E5%8D%B0TRUE.png)

### 

重写方法（一般出现在类的继承里面）的规则：

1）、参数列表必须完全与被重写的方法相同，否则不能称其为重写而是重载。

2）、返回的类型必须一直与被重写的方法的返回类型相同，否则不能称其为重写而是重载。

![image-20220715101234951](img/%E9%87%8D%E5%86%99.png)

### instanceof 

严格来说是Java中的一个双目运算符，用来测试一个对象是否为一个类的实例，用法为：

```java
boolean result = obj  instanceof Class
```

编译器会检查 obj 是否能转换成右边的class类型，如果不能转换则直接报错

### 短路原则

尽早让不合格的先行离开

![image-20220715103222495](img/%E7%9F%AD%E8%B7%AF%E5%8E%9F%E5%88%99%E4%BB%A5%E5%8F%8AJDK%E7%9A%84%E6%96%B0%E7%89%B9%E6%80%A7%EF%BC%88instanceof%20Point%20point%EF%BC%89.png)

lombok简化代码（getter和setter以及equals）的插件

## 抽象类

![image-20220715143053699](img/%E6%8A%BD%E8%B1%A1%E7%B1%BB%E7%89%B9%E7%82%B9.png)

### final

修饰基本类型，表示是常量，不可修改

修饰类，表示类不能被继承，不可扩展

修饰引用还可以通过setXXX()修改值，但不能重新new一个对象给她 

修饰方法，表示最终版本，并不能被重写

新特性：final 修饰的变量可以在构造器中进行第一次赋值初始化

![image-20220715152959907](img/final.png)

### static

静态（只有一份，只加载一次）优先，父类优先，new对象打印再构造方法打印

静态方法只能引用静态属性

静态代码块：只执行一次，并且时间点在构造器之前，在静态属性初始化之后

![image-20220715154047027](img/static.png)

```java
hasNextInt()//判断下一一个输入是否是整数，如是返回TRUE
Class.forName(className).newInstance()//创建这个类的实例对象
```



# 7.18

# 接口

## 什么是接口

是当我们去抽象对象的行为时，所封装的类型，它本质上是定义了一种行为的契约、规约。因为我们从接口中定义的抽象方法上，只能看到方法的参数input，还有返回类型output

代码训练 、画好导图、理清思维再动手

## 1.1用法：

1.解耦 

2.形成多态

 3.接口最终形成了一种跨界类型

## 1.2抽象类和接口的区别：

1、抽象类既有抽象方法也有具体方法;接口中主要都是抽象方法（除default方法)

2、抽象类中可以定义成员变量，而接口中只能定义常量
3、抽象类只能被单继承，而接口可以被实现多个
4、抽象类体现的是is a的关系,而接口体现的是like a的关系

## 1.3语法特点：

1、接口中主要定义的是方法，而且默认都是public abstract
2、它也能定义变量，但是都是public final static，并且必须要对其进行初始化
3、接口可以被类所实现，实现它的时候，需要实现其中所有的抽象方法，否则，这个类必须声明为abstract class4、接口可以继承其它接口(继承多个),达到复用方法的定义
5、其他类在implements接口的时候，可以实现多个接口6、接口中也可以定义带方法体的default方法
——————————————————————————————————

继承is j接口like

先写继承再写实现(A extends B implements C)，

可以将接口理解为抽象类的一种特殊情况（抽象有属性可定义为private，接口叫共有的变量 public static final

面向接口编程（抽象化，避免牵一发而动全身），如果要改变方法只需再添加一个具体的类去实现它就可以了，可以做到开闭原则（里氏代换原则：对扩展开放，对修改关闭）

实现了类型跨界，强转为WiFi（接口）都可以传到方法里面调用connect行为

![image-20220718102529631](D:%5Cmy-project%5Cnotes.github.io%5Cdocs%5Cjavase%5Cimg%5Cimage-20220718102529631.png)

贷款计算案例

```
// 1 - 新增一个接口，把要提取的方法封装到接口中来
// 2 - 实现接口中的方法
// 3 - 以接口的方式定义成员变量
    private MonthlyCalculator rateCalc;// = new MonthlyCalculatorImpl1(); // 计算月利率的变量
    // 4 - 通过构造器从外部传递一个具体的实现者
        this.rateCalc = rateCalc;
```

![image-20220718104214099](D:%5Cmy-project%5Cnotes.github.io%5Cdocs%5Cjavase%5Cimg%5Cimage-20220718104214099.png)

jdk新特性，默认default方法可以具体实现

![image-20220718141510843](D:%5Cmy-project%5Cnotes.github.io%5Cdocs%5Cjavase%5Cimg%5Cimage-20220718141510843.png)

 通过创建接口，并进行实现，构造有参构造方法，传入接口参数，然后调用方法

![image-20220718173943161](D:%5Cmy-project%5Cnotes.github.io%5Cdocs%5Cjavase%5Cimg%5Cimage-20220718173943161.png)





# 7.19

推荐使用“百度脑图”

ctr shift r全局搜索

getClass instanceof

hashcode

toString

equals(包装类TRUE)

128之内为TRUE否则为FALSE，语法糖效果

toCharArray getBytes

计算日期间隔

![image-20220720092537633](D:%5Cmy-project%5Cnotes.github.io%5Cdocs%5Cjavase%5Cimg%5Cimage-20220720092537633.png)







# 7.20

# 集合

## 1.数组优缺点

既然已经有数组了，为什么还要开发出这么多集合类?
优点：

1、随机访问速度理论上是最快的，访问anr[6]与访问an[n]， n趋近于无穷大，这个访问速度几乎是没有差异的，唯一受限于内存的主频，索引可以理解2、它是唯一可以存储多个基本类型元素的容器

缺点：

1、长度一旦初始化以后就固定了

2、操作数组的方法非常少，几乎只能根据索引来赋值

3、只能存储一个固定的类型

## 2.Collection

Collection是大部分集合组件的父接口

1、能保存多个元素
2、提供了操作他们的一些基本方法CRUD (create research update delete)

3、可以被迭代的(可以被循环输出)

4、其中元素的顺序无法得到保证，具体要看实例化的是什么样的容器

## （1）迭代器

```java
// 迭代：挨个儿访问其中的每一个元素

// 获取到能访问这个容器中的元素的一个指针，它默认是指向这个容器中第一个元素的上方

Iterator<Object> it = c1.iterator();

// 它会往下移动一格，然后查看这个时候，指针指向的位置是否有数据
while(it.hasNext()){
    System.out.println(it.next()); // 读取此时指针指向的元素
}
```

## （2）arraycopy(System)

```java
// 参数1：从哪个数组拷贝出来
// 参数2：从原先这个数组的第几个位置开始拷贝
// 参数3：拷贝到哪里去
// 参数4：拷贝的元素放到目标数组里面，是从第几个位置开始放置
// 参数5：一共需要拷贝多少元素
System.arraycopy(data, index + 1, data, index, (size - index - 1));
```

## （3）泛型

```
泛型是用来限定类型的一种参数
所有的集合在使用泛型的时候，只能使用封装类型，不能使用基本类型
```

## L ist特点

1、有序的(插入有序性)
2、可以放置重复元素

### 1.ArrayList

![image-20220720184937872](D:%5Cmy-project%5Cnotes.github.io%5Cdocs%5Cjavase%5Cimg%5Cimage-20220720184937872.png)

1、基于数组实现的额，具备了数组所有的优点
2、动态扩容
3、随机查找速度非常快(基于下标访问的)，随机插入非常慢，如果插入的index非常靠前， 那么后面的每一 个元素都要为前一个元素腾出位置来

### 2.LinkedList 

是一个基于Node (节点)来实现的虚拟容器 (没有具体的边界)，每个节点都会 从 ”前"和"后”两个方向记住临近节点的信息
双向链表
优点:随机访问的速度比较慢，但是随机插入、删除的速度比较快

## Map特点

### HashMap

1、基于键值对(key-vaLue )的数据结构
2、它的key是不能重复的，value是可以重复的
3、元素的排列顺序是无法得到保障的

HashMap的常用方法

![image-20220720172145896](D:%5Cmy-project%5Cnotes.github.io%5Cdocs%5Cjavase%5Cimg%5Cimage-20220720172145896.png)

HashSet不可放重复元素