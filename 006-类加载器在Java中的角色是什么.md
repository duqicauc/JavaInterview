> 本文首发于公众号：javaadu

### 典型答案 

类加载器属于JVM的类加载子系统，常见的类加载器有：Bootstrap classloader、ExtClassloader、AppClassloader，还有用户自定义的类加载器。Bootstrap classloader是C++编写的启动类加载器，负责加载`java.lang.*`开头的类；ExtClassloader是扩展类加载器，负责加载JVM扩展类,比如swing系列、xml解析器等等，这些库的的jar包位于*JAVA_HOME/lib/ext*目录下。 

类加载器负责将.class格式的字节码文件或来自网络上的字节码流读取到内存中。类加载的过程是按需加载的，因为Java是一门动态编译语言，所谓动态编译语言指的是不需要在开始运行前就构成一个完整的可执行文件。 

- C/C++属于静态编译语言，需要将程序中所有的子模块都打包在一起构成一个可执行文件。将不同模块的代码合并到一个可执行文件的过程指的是**链接**。 

- Java代码执行的过程也跟C/C++不同，在Java中，源代码会被javac编译为.class文件，在被加载到JVM中之前都不会进行链接——也就是说，Java程序的链接是在JVM里运行时进行的。Java应用运行的时候，会按照需要加载对应的类——如果一个类依赖于另一个类，则在加载这个类之前要先加载它依赖的那个类（这个按需加载的过程就是动态编译）。 

### 问题分析 

这个问题的关键点有二：（1）类加载的定义是什么；（2）类加载器的作用是什么。 

如果能回答清楚这两个点，面试官如果想考察你对JVM的理解的深度，就会从这里开始，展开进一步的追问，例如：（1）所谓的双亲委派机制是什么意思？（2）是否了解线程上下文加载器？（3）描述下一个类的加载过程；（4）一个类在被加载到JVM后，还有机会被改变吗？（5）是否在生产中遇到过类加载相关的问题，是怎么排查、分析和解决的？ 如果能够在接下来的这几个问题中侃侃而谈，那么说明候选人对类加载器这块的知识的掌握深度是过关的。

### 知识点梳理 

关于类加载器，有几个关键的知识点需要掌握（在此不做展开，有一篇相关的文章正在过程中，大家敬请期待）。 

1. 类加载的过程 

2. 类加载器的类型 

3. 双亲委派机制 

4. 线程上下文加载器（打破双亲委派机制） 

5. 类加载在java agent中的应用 

6. osgi和模块化 

### 参考资料 

1. [https://stackoverflow.com/questions/2424604/what-is-a-java-classloader](https://stackoverflow.com/questions/2424604/what-is-a-java-classloader) 
2. [https://docs.oracle.com/javase/specs/jvms/se11/html/jvms-5.html](https://docs.oracle.com/javase/specs/jvms/se11/html/jvms-5.html) 
3. 《深入理解JVM虚拟机》 
