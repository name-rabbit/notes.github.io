##  1. 数组对象的创建
第一步： 创建数组并初始化空间：int[] Student = new Student(10);
第二步：student[i]=new Student();(# student[i].不了任何对象)
## 2. 对象的应用
![地球大爆炸](img/%E5%9C%B0%E7%90%83%E5%A4%A7%E7%88%86%E7%82%B8.png)
> 第一个打印的value为10(因为方法出栈后就毁灭了),第二个ca.value打印的是11(改变的是地址的引用，指向堆内存中真正的值11)