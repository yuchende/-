// 数组 转换 成 列表，集合 等

```java
//数组转化为列表
int[] src = {1,2,3,4,5,6,7,8,9,10};
List<Integer> list = Arrays.stream( src ).boxed().collect(Collectors.toList());
https://www.cnblogs.com/ainsliaea/p/11366481.html

对于 Integer 数组，可以使用 Arrays.asList、Arrays.stream、Collections.addAll 或者 Stream.of 进行转换：
但是 Arrays.asList 返回的是只读的 List 不支持 add 和 remove 的操作，如果往里 add 会报 UnsupportedOperationException

Integer[] arr2 = {234, 2, 23, 777, 2};

List<Integer> list = new ArrayList<>(arr2.length);
Collections.addAll(list, arr2);

List<Integer> list1 = Stream.of(arr2).collect(Collectors.toList());
List<Integer> list2 = Arrays.stream(arr2).collect(Collectors.toList());
List<Integer> list3 = Arrays.asList(arr2);



```

//  String类的函数,    StringBuilder,StringBuffer,String

```java
//字符数组,各种类型转换成String
char[] ch=new char[10];
String str = String.valueOf(ch);//将字符数组 直接转换成字符串
int a=0;
String str = String.valueOf(a);


//定位某字符,字符串的位置
str.charAt(i); str.indexOf(String str)  str.lastIndexOf()
//切割
str.substring(int from,int to)//to取不到
//替换
str.replace()
    
//速度 StringBuilder> StringBuffer >String
    //StringBuffer线程安全，StringBuilder线程不安全
    //StringBuffer很多方法有synchronized关键字
    
```

//HashSet  无序不重复集合,   HashMap<K，V> 

```java
HashSet<Integer> result=new HashSet<>();//构造函数参数还可有Collection<? extends E> c
//即List,Set,Queue

	    add(Object obj)
boolean contains(Object obj)
int     size()  //返回大小  
for(Integer i:result){ //便利数组
    
}
HashMap<Character,Integer> hash =new HashMap<>();
        hash.put(key,value);
        value hash.get(key);
            replace(key,new_value);

        hash.containsKey(obj)  hash.containsValue(obj)


        Set  hash.keySet()
        Set  hash.values()
```

//List 链表     LinkedList

```java
//将数组转换成链表
// array list set 互相转换
List<T> list = Arrays.asList(T..a)
//https://www.cnblogs.com/yysbolg/p/9977365.html
    
    
LinkedList
LinkedList<int[]> list=new LinkedList<>();
list.add(intervals[i]);
result[i]=list.removeFirst(); 
list.size();
list.isEmpty()//遍历集合
```

//数组，一维数组，二维数组

```java
//二维数组

    //1.二维数组按找第n列排序，行内顺序不变，行号由当前列的数组的大小决定
    Arrays.parallelSort(array, Comparator.comparingInt(x -> x[n]));

    //2.将某一个一维数组赋值给二维数组的某一行。二维数组每行的数据不一定相同。
    arrayp[i] = new int[10]{1,2,2,3,3,4} 


//一维数组

    //1.值替换
    public static void fill(int[] a, start, end, int var)
    // from 包括，end不包括，var 替换的值

	//2.区间拷贝，扩容
	int[] arr = new int[10];
	arr= Arrays.copyOfRange(arr, 0, arr.length*2);
	// 第三个参数 to<arr.length  拷贝[from,to) 返回新数组
	// to>array.length时候在当前arr长度下,扩容.新长度就是to的值
	int[] Arrays.copyOf(int[] array,int newLength);//newLength扩容后的数组	

	//3.排序
	Arrays.sort(int[] arr),//或double
	Arrays.sort(char[] chs),
	
	

```

//队列，栈

```java
Queue<Integer> queue = new LinkedList<>();
queue.offer(Obj)//队尾插入元素
queue.poll()  //返回队列头部元素,并删除
queue.peek()  //返回队头，不删除
queue.isEmpty() //是否为空
    
Stack<Integer> stack = new Stack<>();
stack.peek() //返回栈顶，不
stack.push()
stack.pop()
stack.empty()
```



##### 1...排序：整数数组排序

ArrayList<Integer> list=new ArrayList<Integer>();
        list.sort(new Comparator<Integer>() {
			@Override
			public int compare(Integer o1, Integer o2) {
				retrun o1.intValue-o2.intValue;
			}});

Arrays.sort();

```java
int[] a=new int[5];
a[0]=n;
a[1]=b;
a[2]=c;
a[3]=d;
a[4]=e;  
Arrays.sort(a);//a中double类型的，各种类型的都可以。
//Arrays.sort(a, fromIndex, toIndex);
```

Collections.sort(list);

##### 2...输入输出示例



```java
示例1： 
输入：
1 2 3
2 3
		int n=in.nextInt();   nextInt()//遇到空格或回车，视为下一个输入。
        int b=in.nextInt();
        int c=in.nextInt();
        int d=in.nextInt();
        int e=in.nextInt();	
输入：
2 3 4 1 3  //用上述均可

示例2： 输入一行字符串
next()//结束的标志是空格，回车，tab键
nextLine()//结束的标志回车

```



##### 3...字符串的分割，字符的定位，字符的去除，更改，插入

String str="12,12,44,55,5";

```java
				String s1=reader.next();//1,22,33,44,55,77
                System.out.println("字符串的分割，按照 ，");
                String[] str=s1.split(","); //分割字符串
                for(int i=0;i<str.length;i++) {
                	System.out.print(str[i]+" ");
                }
                System.out.println();
                
                StringBuffer sb=new StringBuffer(s1);
                System.out.println("初始字符串str="+sb.toString());
                
                System.out.println("定位第一个字符，char0="+sb.charAt(0));
                
                sb.deleteCharAt(0);//删除第一个字符
                System.out.println("删除第一个字符后，str="+sb.toString());
                sb.delete(0,1);
                System.out.println("删除0,1的字符，str="+sb.toString());
                
                sb.setCharAt(sb.length()-1,'a');//将最后一个设置成a
                System.out.println("最后一个设置成a后 ,str="+sb.toString());
                
                sb.insert(1, 'b');
                System.out.println("在index=1的地方插入b后, str="+sb.toString());
                
                sb.insert(3, " hello ");
                System.out.println("将index=3的位置处插入 hello  后，str="+sb.toString());
                
                sb.replace(4, 6, "jj");
                System.out.println("replace 4,6 jj, str="+sb.toString());

//执行结果
1,22,33,44,55,77
字符串的分割，按照 ，
1 22 33 44 55 77 
初始字符串str=1,22,33,44,55,77
定位第一个字符，char0=1
删除第一个字符后，str=,22,33,44,55,77
删除0,1的字符，str=22,33,44,55,77
最后一个设置成a后 ,str=22,33,44,55,7a
在index=1的地方插入b后, str=2b2,33,44,55,7a
将index=3的位置处插入 hello  后，str=2b2 hello ,33,44,55,7a
replace 4,6 jj, str=2b2 jjllo ,33,44,55,7a 
replace 4,6 jj, str=2b2 jjjllo ,33,44,55,7a 若4-6
```

StringBuffer的函数：

//定位
char CharAt(int index): //定位哪一个位置上的char
int lastIndexOf(String str);
//删除
delete(int start,int end):
deleteCharAt(int index):
//更新
setCharAt(int off,char ch):
//插入
insert(1,'a');
insert(2,"aabbcc");
//替换
replace(int off,int end,String newElement);从off开始替换，newElement的长度可以不为,|off-end|

//获取某一段串
String subString(int begin,int end);