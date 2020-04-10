





------

1. HashSet的建立

------

建立hash链表要解决的问题：

- hash函数   每个值对应唯一的散列值

- 冲突处理  (多个A映射到相同B)

     单独链表法： 一个值对应一个桶，每个桶相互独立。如LinkedList

     开放地址法： 每当有碰撞，根据探查策略找到一个空槽为止。

     双散列法：   使用两个hash函数，选择碰撞更少的地址。

```
单独链表法：
	一个链表数组，每个不同的A  对应不同下标的链表，即桶.
	class MyHashSet {
    	private Bucket[] hashset;
    	private int len = 769;
    }
	class Bucket{
     private LinkedList<Integer> list;
     // insert remove isExist....
    }
```

