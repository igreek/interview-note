26.明白ThreadPoolExecutor、AbstractExecutorService、ExecutorService和Executor的关系    
    [具体参考](http://www.cnblogs.com/exe19/p/5359885.html)

30.原理形象图

![image](http://dl.iteye.com/upload/attachment/0067/4942/98c5de19-da53-37f4-8816-b215e051e02f.jpg)

Thread和Runnable是2中完全不同的实现多线程方式，前者是多个线程分别完成自己的任务；后者是多个线程共同完成任务
>大多数情况下，如果只想重写 run() 方法，而不重写其他 Thread 方法，那么应使用 Runnable 接口

