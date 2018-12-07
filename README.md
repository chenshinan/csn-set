# Set相关实现类的源码解析

## Set的架构图

![Set的架构图](https://images0.cnblogs.com/blog/497634/201309/09223827-04741ce6b3f84b3ab76cee8dd316b403.jpg)

## Set相关

* Set 是继承于Collection的接口。它是一个不允许有重复元素的集合

* Set不支持快速获取，只能通过迭代器进行遍历

## HashSet

* 继承关系：HashSet -> AbstractSet 实现 Set接口

* HashSet实现Set接口，由哈希表（实际上是一个HashMap实例）支持。它`不保证set 的迭代顺序`；特别是它不保证该顺序恒久不变。此类`允许使用null元素`。

* HashSet的`元素都存到HashMap键值对的Key上面`，而Value时有一个统一的值`private static final Object PRESENT = new Object();`

* HashSet的实现

对于HashSet而言，它是基于HashMap实现的，HashSet底层使用HashMap来保存所有元素，因此HashSet 的实现比较简单，相关HashSet的操作，基本上都是直接调用底层HashMap的相关方法来完成， HashSet的源代码如下

## TreeSet

* 继承关系：TreeSet -> AbstractSet 实现 Set接口

* TreeSet的本质是一个`"有序的，并且没有重复元素"`的集合，它是通过TreeMap实现的。TreeSet中含有一个`"NavigableMap类型的成员变量"`m，而m实际上是`"TreeMap的实例"`

参考文献：
- [Java 集合系列教程](http://www.cnblogs.com/skywang12345/p/3323085.html)