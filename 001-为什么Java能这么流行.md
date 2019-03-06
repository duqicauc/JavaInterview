> 本文首发于公众号：javaadu

## 典型回答

这种问题比较笼统，如果我遇到这个问题，我会从下面几个点阐述我的观点：
1. Java通过JVM实现了“一次编写，到处运行”的特性，由JVM屏蔽掉了不同平台的差异性，并创建了字节码语言来作为Java代码的“汇编语言”，JVM读取字节码文件、解析字节码文件来运行；
2. JVM提供了垃圾收集器，大部分情况下，程序员不需要自己担心内存的分配和回收；
3. Java在企业级开发领域具备杀手级框架Spring全家桶，让Java在企业服务领域几无敌手；
4. Java在客户端开发领域具备杀手级应用场景——Android开发；
5. Java开发的生态非常丰富和完整，有无数成熟可靠的开源软件；
6. Java是一门面向对象的静态类型语言，面向对象的特性有助于Java构建大型的、复杂的应用，静态类型语言使得Java在运行时的速度远胜于解释性语言，同时使得Java应用在编译期可以发现很多问题，是类型安全的；
7. Java一直在发展和进化，Java 1.5补充了很多有用的特性、Java 1.8开始引入stream、lambda等特性来拥抱函数式编程范式、Java 1.9开始支持模块化等等

## 问题分析

这种问题属于开放式问题，可以考察很多方面的内容，例如面试者的基础知识是否扎实、知识体系是否完整。越是开放的问题，回答越不能发散，要给出系统性、结构性的回答，表现出自己是系统、全面得掌握了Java语言和其所运行的平台的。

## 知识点扩展

### 1、Java知识地图
首先看一张图，是Oracle对Java核心概念的一些总结![Java核心架构.jpeg](https://upload-images.jianshu.io/upload_images/44770-5bcfa63154733cfb.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


这张图看着密密麻麻的，不太好懂，我整理了一份脑图出来，看着更清晰一点（利用虚线框表示包含关系）：![Java核心知识地图.png](https://upload-images.jianshu.io/upload_images/44770-5d5cebd7840974c4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


 1. JVM虚拟机：按照虚拟化里面的概念，JVM虚拟机属于宿主型虚拟机，作为一个虚拟机，最核心的模块是：运行时内存管理、类加载、字节码系统、执行引擎、垃圾收集器等等；
 2. JRE（Java运行时环境）：只有JVM，对于普通的Java开发者来说难度太高了，因此Hotspot的开发者还为普通开发者提供了对应的Java SE API和其他开发者需要的类库，这些API、类库和JVM共同构成了Java运行时环境。
 3. Java语言：JVM之上不仅仅有Java语言长盛不衰，还培育出了丰富的语言生态，例如Scala、Groovy、Kotlin、等新生代的语言。
 4. JDK：JVM、JRE，在加上辅助工具、Java语言，共同构成了JDK。

### 2、应用场景
从Java语言的应用场景和生态看，分为如下几点：
 1. 企业级开发（J2EE）：SSM框架、Spring Boot、Spring Cloud、JPA、缓存、批量处理、定时任务等等；
 2. 客户端开发（J2ME）：安卓开发
 3. 大数据开发：Spark、Hadoop、Hbase、ES等等

### 3、新特性
在将上面的内容讲完后，面试官对你的知识体系的完整性应该会比较满意，接下来还可以谈下Java各个版本的发展，最好能提到某个版本比较重大的新特性，向面试官证明你不仅掌握了基础，还随时跟进Java语言最新的发展。
 1. Java 1.8
 2. Java 1.9
 3. Java 1.11
 
 ## 参考资料
 1. [Description of Java Conceptual Diagram](https://docs.oracle.com/javase/8/docs/technotes/guides/desc_jdk_structure.html)
***
本号专注于后端技术、JVM问题排查和优化、Java面试题、个人成长和自我管理等主题，为读者提供一线开发者的工作和成长经验，期待你能在这里有所收获。
![javaadu](https://upload-images.jianshu.io/upload_images/44770-36c2588dfde08923.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
