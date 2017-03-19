1. 简单的流程：servlet类加载--->实例化--->服务--->销毁
具体分析：
   - 流程图
   
   - servlet和HttpServlet的交互流程：
   
   ![image](http://static.oschina.net/uploads/space/2015/0403/101033_7Q9m_120166.jpg)
   
   >Servlet的框架由两个Java包组成的：javax.servlet与javax.servlet.http。在javax.servlet包中定义了所有的Servlet类都必须实现或者扩展的通用接口和类。在javax.servlet.http包中定义了采用Http协议通信的HttpServlet类。Servlet的框架的核心是javax.servlet.Servlet接口，所有的Servlet都必须实现这个接口。在Servlet接口中定义了5个方法，其中3个方法代表了Servlet的生命周期：
    init(ServletConfig)方法：负责初始化Servlet对象，在Servlet的生命周期中，该方法执行一次；该方法执行在单线程的环境下，因此开发者不用考虑线程安全的问题；
    service(ServletRequest req,ServletResponse res)方法：负责响应客户的请求；为了提高效率，Servlet规范要求一个Servlet实例必须能够同时服务于多个客户端请求，即service()方法运行在多线程的环境下，Servlet开发者必须保证该方法的线程安全性；
    destroy()方法：当Servlet对象退出生命周期时，负责释放占用的资源；
    
    - 注意事项
    
    1.Servlet的init()方法是工作在单线程的环境下，开发者不必考虑任何线程安全的问题。
    
    2.多个线程同时执行同一个Servlet实例的service()方法，因此必须考虑线程安全的问题。
    
    3.service()方法运行在多线程的环境下，并不一定要同步该方法。而是要看这个方法在执行过程中访问的资源类型及对资源的访问方式。分析如下：
    >如果service()方法没有访问Servlet的成员变量也没有访问全局的资源比如静态变量、文件、数据库连接等，而是只使用了当前线程自己的资源，比如非指向全局资源的临时变量、request和response对象等。该方法本身就是线程安全的，不必进行任何的同步控制。
     如果service()方法访问了Servlet的成员变量，但是对该变量的操作是只读操作，该方法本身就是线程安全的，不必进行任何的同步控制。
     如果service()方法访问了Servlet的成员变量，并且对该变量的操作既有读又有写，通常需要加上同步控制语句。
     如果service()方法访问了全局的静态变量，如果同一时刻系统中也可能有其它线程访问该静态变量，如果既有读也有写的操作，通常需要加上同步控制语句。
     如果service()方法访问了全局的资源，比如文件、数据库连接等，通常需要加上同步控制语句。
     
     - 创建Servlet时机
        
     - 销毁Servlet时机
     
        >Servlet容器停止或者重新启动：Servlet容器调用Servlet对象的destroy方法来释放资源。
     
     - Servlet的工作原理     
     
     - Servlet什么周期UML图
     
     ![image](http://static.oschina.net/uploads/space/2015/0403/112707_yOnu_120166.jpg)
     
2. Struts2是类级别的拦截，一个类对应一个请求；SpringMVC是方法级别的拦截，
   
   Struts2比SpringMVC更耗费内存。
   
   拦截器实现机制不同：Struts2有自己的Interceptor机制，SpringMVC采用独立AOP的方式
   
   SpringMVC的入口是Servlet，Struts2是Filter
   
   SpringMVC更容易集成Ajax
   
   SpringMVC的开发效率和性能高于Struts2:可实现零配置
   
3. Filter是基于函数回调，Interceptor是基于java反射机制
   
   Filter依赖于Servlet容器，没有Servlet容器，则无法回调doFilter方法，Interceptor与Servlet无关
   
   在Action什么周期中，拦截器可以被多次调用，而过滤器只能在容器初始化时被调用一次
   
   filter的过滤范围比interceptor大
    
   [参考地址](http://www.i3geek.com/archives/870) 