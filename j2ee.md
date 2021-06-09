1. **什么是Spring中的Bean**
    * Bean是Spring中被管理的对象

2. **对比Bean的生命周期**
    * 若bean标签的scope="singleton"，那么该Bean与容器同生共死，即与容器的生命周期一致。具体讲就是：容器创建时该Bean"诞生"，容器销毁时同时将该Bean销毁
    * 若bean标签的scope="prototype"，那么在容器创建时该Bean并没有"诞生"，而是在首次被使用时才"诞生"；该Bean的"死亡时间"与容器的销毁时间并不同步，Bean的销毁不由容器负责，而是由JVM的垃圾回收器负责。

3. **Bean基于xml，对比设值注入，构造注入的区别**
    * 设值注入：先通过无参数的构造函数创建一个Bean实例，然后调用对应的setter方法注入依赖关系
    * 构造注入：直接调用有参数的构造器，当bean实例创建完成后，已经完成了依赖关系的注入

4. **什么是AOP思想**
    * 面向切面编程，通过预编译方式和运行期动态代理实现程序功能的统一维护的一种技术。
    * AOP是OOP的延续，是软件开发中的一个热点，也是Spring框架中的一个重要内容，是函数式编程的一种衍生范型。
    * 利用AOP可以对业务逻辑的各个部分进行隔离，从而使得业务逻辑各部分之间的耦合度降低，提高程序的可重用性，同时提高了开发的效率。

5. **什么是声明式事物管理**
    * Spring的声明式事务顾名思义就是采用声明的方式来处理事务。这里所说的声明，就是指在配置文件中申明。
    * 用在Spring配置文件中声明式的处理事务来代替代码式的处理事务。

6. **MyBatis的工作原理（8个）**
    1. 加载mybatis全局配置文件（数据源、mapper映射文件等），解析配置文件，MyBatis基于XML配置文件生成Configuration，和一个个MappedStatement（包括了参数映射配置、动态SQL语句、结果映射配置），其对应着<select | update | delete | insert>标签项。
    2. SqlSessionFactoryBuilder通过Configuration对象生成SqlSessionFactory，用来开启SqlSession。
    3. SqlSession对象完成和数据库的交互：
    4. 用户程序调用mybatis接口层api（即Mapper接口中的方法）
    5. SqlSession通过调用api的Statement ID找到对应的MappedStatement对象
    6. 通过Executor（负责动态SQL的生成和查询缓存的维护）将MappedStatement对象进行解析，sql参数转化. 动态sql拼接，生成jdbc Statement对象
    7. JDBC执行sql。
    8. 借助MappedStatement中的结果映射关系，将返回结果转化成HashMap、JavaBean等存储结构并返回。

7. **什么是ORM**
    * MVC框架中重要的一部分就是ORM，实现了数据模型与数据库的解耦，即数据模型不需要依赖于特定的数据库，通过简单的配置就可以轻松更换数据库。
    * ORM是对象关系映射的简称，主要任务是：
　　        根据对象的类型生成表结构将对象、列表操作，转换成SQL语句（或其他数据库的语句）将SQL查询到的结果转换为对象、列表

8. **MVC的含义和作用**
    * 是一种软件架构模式，把软件系统分为三个基本部分：模型（Model）、视图（View）和控制器（Controller）。
    * 实现一种动态的程序设计，使后续对程序的修改和扩展简化，并且使程序某一部分的重复利用成为可能。除此之外，此模式通过对复杂度的简化，使程序结构更加直观。

9. **写出Spring MVC的优点**
    1. SpringMVC框架提供了一整套完善的组件。
    2. SpringMVC是以强大的Spring容器为基础的框架。
    3. 框架的配置简单又不失灵活性。
    4. 代码的可重用性很高。
    5. 可扩展性好。

10. **为什么进行自定义数据绑定**
        因为正常情况下基本数据类型已经能满足需求，但是有些特殊情况的参数是无法在后台进行直接转换的，但也有些特殊数据类型无法直接进行数据绑定，必须先经过数据转换。

11. **Converter，formatter的区别**
    * Converter可以从任意源类型，转换为任意目标类型。
    * Formatter则是从String类型转换为任务目标类型，
        