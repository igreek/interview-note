1.
- 外部调用时，静态方法无需创建对象，实例方法需要
- 静态方法只准许范围静态成员，实例方法没有此限制；之所以不允许静态方法访问实例成员变量，是因为实例成员变量是属于某个对象的，而静态方法在执行时，并不一定存在对象
- 静态方法不能使用this
- static 方法只用加载一次，但一直会占用内存。多了些资源消耗；而实例方法需要加载多次，但不会一直占用内存。少些资源消耗。

> 衍生出静态方法加锁和非静态方法加锁的区别

2. 异常是程序的逻辑错误或系统错误，比如空引用，数值下标越界，内存溢出，可以分为Error和Exception
   - Error无法处理的异常，比如OutOfMemoryError，一般发生这种异常，JVM会选择终止程序。因此我们编写程序时不需要关心这类异常。 
   - Exception，也就是我们经常见到的一些异常情况，比如NullPointerException、IndexOutOfBoundsException，这些异常是我们可以处理的异常。 
        - 运行时异常（unchecked exception）：比如常见的NullPointerException、IndexOutOfBoundsException。对于运行时异常，java编译器不要求必须进行异常捕获处理或者抛出声明，由程序员自行决定
        - 非运行异常：
        
        ![image](http://images.cnitblog.com/i/288799/201406/051650515056805.jpg  )
        
    [详情参考](http://www.importnew.com/18994.html)  
        
>  [衍生出java异常处理的误区和经验总结](https://www.ibm.com/developerworks/cn/java/j-lo-exception-misdirection/)

7.
- ==比较是两个变量的数值是否相同，若要比较的内容是引用类型的变量和基本类型的数据是否相同，则只能用==
- equals方法比较的是2个独立对象的内容是否相同，
比如
```
    String a = new String("foo");  
    String b = new String("foo");  
```
> 两条new语句创建了两个对象，然后用a,b这两个变量分别指向了其中一个对象，这是两个不同的对象，它们的首地址是不同的，即a和b中存储的数值是不相同的，所以，表达式a==b将返回false，而这两个对象中的内容是相同的，所以，表达式a.equals(b)将返回true。字符串的比较基本上都是使用equals方法。
  如何覆写equals方法：
  
    1) 用==比较两对象    
    2) 判断被比较对象是否为null    
    3) 不为null, 判断被比较对象是不是和比较对象类型相同或其子类，并进行类型转换(因为传进来的都是Object类型)      
    4) 进行属性比较

[具体参考](http://blog.csdn.net/zdp072/article/details/44180301)

9.具体方法有equals()、hashcode、toString、clone、wait/notify/notifyAll、finalize等
[具体参考](http://www.cnblogs.com/binyue/p/3434918.html)

16.
- int 4个字节 8*4位
- long 8个字节 8*8位
- double 8个字节 8*8位
- char 2个字节   2*8位
[具体参考](http://blog.csdn.net/nyistzp/article/details/12029917

>衍生出装包和拆包



26.[参考地址](http://blog.csdn.net/u011301815/article/details/52206997)


27.
    
    - 按流的处理方向：输入流和输出流
    - 按流的处理单位分：字节流和字符流
    - 按功能分：节点流和处理流
   
   jdk提供的流继承了四大类：InputStream(字节输入流)，OutputStream（字节输出流），Reader（字符输入流），Writer（字符输出流）。    
   
   ![image](http://hi.csdn.net/attachment/201203/23/0_13324938595035.gif) 
   
   [详情参考](http://blog.csdn.net/yuebinghaoyuan/article/details/7388059)
    