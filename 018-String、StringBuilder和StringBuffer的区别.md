> 本文首发于公众号：javaadu

## 参考回答
Java中的String对象是不可变对象，针对字符串对象的操作（例如subString、contact、replace）都会生成一个新的String对象，如果应用中有大量这样的操作，就会产生大量的临时String对象，会影响Java应用运行的性能。

为了解决上面这个问题，JDK 1.0中提供了StringBuffer类，这个类的对象是可变对象，它的原理是申请一个缓冲区来存放字符串，可以避免产生新的字符串对象。但是StringBuffer是线程安全的，它的方法都被`synchronized`关键字修饰，导致它的性能不太好。

为了解决StringBuffer的性能问题，JDK1.5提供了一个非线程安全的StringBuilder类，现在很多字符操作的底层都是根据StringBuilder实现的，例如"+"操作、StringJoiner等等。

关于StringBuilder和StringBuffer的选择：我们在编写并发程序的时候，什么时候需要两个线程共享同一个字符串对象呢？我目前没有遇到过。

## 知识点梳理
1. Java中String对象是不可变的
2. Java支持通过构造方法或字面常量构建字符串
3. 字符串对象存放的位置可能在堆内存，也可能在字符串常量池。使用构造方法构建的字符串对象一定在堆内存，如果堆该字符串对象调用String.intern()方法，则可以将该字符串移入字符串常量池。
4. 字符串常量池在JVM底层本质上是一个Hashtable
5. 字符串上支持很多操作API，例如字符串连接、截取字符串、trim、替换字符等等，这些操作看似是写操作，实际上都会返回一个新的字符串
6. 字符串的连接操作有几种方式：“+”运算符重载，底层是依靠StringBuilder实现的；String.contact()方法，底层是依赖Array.copy实现的；StringBuilder，通过预先分配一个字符缓冲区来进行字符串的连接，适合大批量字符串连接的情况
7. String、StringBuilder和StringBuffer的底层数据结构都是char[]数组，不同的是String将该char数组设置成了不可变的（final），通过这个关键字实现了不可变对象。
8. StringBuilder是JDK1.5提供的，目的是补充StringBuffer用在单线程环境下——不必要且性能低的不足。

## 参考资料
1. [https://www.journaldev.com/538/string-vs-stringbuffer-vs-stringbuilder](https://www.journaldev.com/538/string-vs-stringbuffer-vs-stringbuilder)
