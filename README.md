> 以下是总结java面试中常见的知识点以及碰到的坑等，经历有限，需待练级！ 

# 一、java基础
1. 实例方法和静态方法有什么不一样？

2. Java中的异常有哪几类？分别怎么使用？

3. 常用的集合类有哪些？比如List如何排序？

4. ArrayList和LinkedList内部的实现大致是怎样的？他们之间的区别和各自适应的场景是什么？

5. 内存溢出是怎么回事？

6. ClassLoader有什么用？

7. ==和equals的区别？

8. hashCode方法的作用？

9. Object类中有哪些方法？列举3个以上。

10. NIO是什么？适用于何种场景？

12. HashMap数据结构、扩展策略，Hash冲突攻击如何防范，如何实现线程安全的HashMap？

13. JVM内存结构，GC算法，CMS、G1的原理

14. NIO模型，select/epoll的区别，多路复用的原理

16. Java中一个字符占多少个字节，扩展再问int, long, double占多少字节

17. 创建一个类的实例都有哪些办法？

18. final/finally/finalize的区别？

19. LinkingBlockingQueue与ArrayBlockingQueue的区别，他们的适用场景？

21. String/StringBuffer/StringBuilder的区别，扩展再问他们的实现？

22. HASHTABLE, HASGMAQ，TreeMap区别？

23. ConcurrentMap和HashMap的区别

23. 如何用Java分配一段连续的1G的内存空间？需要注意些什么？

24. Java有自己的内存回收机制，但为什么还存在内存泄露的问题呢？

25. Java里面用对象作为Key需要注意些什么？ 如何实现hashcode？ 

26.  


# 二、算法和数据结构

1. 说一下几种常见的排序算法和分别的复杂度。
3. 如何确认一个链表有环？进一步，确认环的位置。
4. 如何遍历一棵二叉树？
5. 倒排一个LinkedList。  
6. HashSet的实现方式
7. 分治算法
    - http://blog.csdn.net/zolalad/article/details/11393915
8. 动态规划算法
9. 贪心算法
10. 常见智力题
    - http://johnny84.blog.51cto.com/2855387/1180506


# 三、多线程和并发


1. Java中常见的锁，互斥锁，读写锁，信号量
    - http://blog.chinaunix.net/uid-20671208-id-4935154.html

2. 原子Atomic类，如何保证原子性，CAS硬件指令

3. volatile可见性问题的原因，硬件架构，L3 Cache，QPI，乐观锁

4. 如何实现一个线程安全的数据结构
    - http://bbs.csdn.net/topics/390600179?page=1
5. 如何避免死锁

6. 如何解决ABA问题

7. Synchronized关键字的作用？

8. Volatile关键字的作用？


9. Java内存模型是怎样的？


10. HashMap在多线程环境下使用需要注意什么？为什么？


11. Java程序中启动一个线程是用run()还是start()？

12. 什么是守护线程？有什么用？

13. 什么是死锁？如何避免

14. 线程和进程的差别是什么？


15. Java里面的Threadlocal是怎样实现的？


16. ConcurrentHashMap的实现原理是？


17. sleep和wait区别

18. notify和notifyAll区别


19. volatile关键字的作用

20. ThreadLocal的作用与实现

21. 两个线程如何串行执行

22. 上下文切换是什么含义

23. 可以运行时kill掉一个线程吗？

24. 什么是条件锁、读写锁、自旋锁、可重入锁？

25. 什么是协程（用户态线程，减少数据拷贝，降低CPU开销，无callback函数）？

26. 线程池ThreadPoolExecutor的实现原理？


27. 常见类的使用。lock, synchronized， ThreadPool的深入考察； BlockingQueue的使用。（take，poll的区别，put，offer的区别）；原子类的实现。

28. 各种常见锁使用如果上面这些掌握很好，还可以看看更深一点的 False Sharing，Cache Line，可见性与原子性等；
29. 在多线程中主线程怎么控制子线程结束?

# 四、java虚拟机

1. JVM堆的基本结构。


2. JVM的垃圾算法有哪几种？CMS收集算法的流程？


3. JVM有哪些常用启动参数可以调整？

4. 如何查看JVM的内存使用情况？

5. Java程序是否会内存溢出？

6. 你常用的JVM配置和调优参数都有哪些？分别什么作用？

7. Java内存分代模型，GC算法，JVM常见的启动参数； 

8. CMS算法的过程，CMS回收过程中JVM是否需要暂停（这块回答较好，也可以只是看毕玄的Java分布式开发或网上文章的学习， 可以结合JVM启动参数常见配置，jstat等命令，看下动手能力，意愿；以及实际线上问题排查）

9. 什么情况下会出现OOM（堆内存，永久区，堆外区，方法栈）

10. Java内存结构（堆结构，新生代[S0/S1/Elden]，年老代，持久代）

11. 常用的GC策略，什么时候会触发YGC，什么时候触发FGC 


# 五、java web

1. Servlet的生命周期？
2. Session/Cookie的区别？
3. SpringMVC与Struts2的比较
4. 拦截器与过滤器的区别？

# 六、 web容器

# 七、数据库

1. MySQL InnoDB的特点？

2. 乐观锁和悲观锁的区别？

3. 数据库隔离级别是什么？有什么作用？

4. MySQL主备同步的基本原理。

5. 如何从一张表中查出name字段包含“XYZ”的所有行？

6. 索引数据结构（字典+BitTree）

7. 如何优化数据库性能（索引、分库分表、批量操作、分页算法、升级硬盘SSD、业务优化、主从部署）

8. SQL什么情况下不会使用索引（不包含，不等于，函数）

9. 一般在什么字段上建索引（过滤数据最多的字段）

10. 如何从一张表中查出name字段不包含“XYZ”的所有行？

11. MySQL，B+索引实现，行锁实现，SQL优化

12. Redis，RDB和AOF，如何做高可用、集群

13. 如何解决高并发减库存问题

14. mysql存储引擎中索引的实现机制；

15. 数据库事务的几种粒度；

16. 行锁，表锁；乐观锁，悲观锁 

# 八、linux

1. 硬链接和软链接的区别？

2. inode是什么？

3. Linux常用命令有哪些？

4. 怎么看一个Java线程的资源耗用？


5. Load过高的可能性有哪些？


6. /etc/hosts文件什么做用？

7. /etc/resolv.conf文件什么作用？

8. 如何快速的将一个文本中所有“abc”替换为“xyz”？


9. 你常用的Linux下用来进行网络和磁盘IO分析的工具有哪些？


10. 你常用的Linux下用来进行内存和CPU分析的工具有哪些？

11. 发现磁盘空间不够，如何快速找出占用空间最大的文件？

12. Java服务端问题排查（OOM，CPU高，Load高，类冲突）

13. Java常用问题排查工具及用法（top, iostat, vmstat, sar, tcpdump, jvisualvm, jmap, jconsole）

14. Thread dump文件如何分析（Runnable，锁，代码栈，操作系统线程ID关联）

15. grep，awk，sed； 是否自己写过shell脚本；

16. 常见的cpu load过高，us过高，一般是什么问题。引申出是否用过top，jstat，jstack等。

17. 常见的内存问题一般有哪些。 引申出是否用过free，top， jmap等。

# 九、网络编程

# 九、设计模式与重构
1. 说出你知道的设计模式，并说出其中的原理

# 十、分布式相关

- ## 分布式原理
- ## 消息中间件
    - RabbitMQ
    - Kafka
- ## 分布式存储
    - HBase
    - Redis
    - MongoDB
- ## 分布式计算
    - MapReduce
    - Hadoop
    
- ## 分布式监控
    - zookeeper
    - zabbix





# 十一、开源框架

- ## ORM框架
1.mybatis与hibernate的区别

- ## spring&springMVC
- ## Netty
- ## RPC框架  
- ##  

# 十二、项目经验

# 十三、自我提升

# 十四、前端框架
- ## jquery
- ## vue
- ## requireJS
- ## reactJS

# 十五、python系列

- ## leetcode


# 友情链接

[link](http://blog.csdn.net/tzs_1041218129/article/details/52355867)

[java修炼图谱](http://blog.csdn.net/liuxiaoyi216/article/details/43852725)

[hollischuang](http://www.hollischuang.com/archives/1036)