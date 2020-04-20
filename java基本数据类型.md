![Javaæ°æ®ç±»ååå](https://img-blog.csdn.net/20161017084238660)

![img](https://pics1.baidu.com/feed/bf096b63f6246b6015db52b41e227f48530fa27c.jpeg?token=11ed133dbdb289d94fde6686ca284a2f&s=BDA87C339F0B604B4ADD45DB000080B1)

https://baijiahao.baidu.com/s?id=1625866229204840473&wfr=spider&for=pc

1个字节 byte  boolean   
2个字节short  char
4个字节 int  float
8个字节long double



向下转型  **自动类型转换**   小型变大型

![img](https://pics6.baidu.com/feed/35a85edf8db1cb1386727f68288e334a93584b95.jpeg?token=39c0ab14aee65ad7a297a2c92c9f2571&s=0AA47C22B7C940E2544101C40000B0B0)

​			1
​			2	
1，2，4，8
​			4 ，8



向上转型**强制数据转换** 大变小

​	

**数据类型自动提升**  两个数之和 其中有1个是double，都会转为double，

```java
		System.out.println("\nstart - Main.test");


        String str = "123";

        byte b = 1;   short s = 2;  int i = 3;  long l = 4L; // 1,2,4,8 字节
        boolean bool = false;   char ch = 'c';  float f = 1.2f;   double d = 1.2; // 1,2,4,8 字节

        long x = l+i+s+b;  System.out.println("x = " + x);
        int y = (int)l+i+s+b;  System.out.println("y = " + y);
        short z = (short) (l+i+s+b);  System.out.println("z = " + z);
        byte a = (byte) (l+i+s+b);  System.out.println("a = " + a);

        Byte byt = new Byte(b); // 要么是byte类型，要么是String类型
        Short sht = new Short(s);
        Integer integer = new Integer(0); // 要么是int类型，要么是String类型
        Long lg = new Long(b);

        Boolean bol = new Boolean(bool);
        Character character = new Character(ch);// 只有一个ch,没有String
        Float flot = new Float(f);// float double String都行
        Double doub = new Double(d); //double,String
        //只要能向下自动转型都可以直接放入构造函数中。
        System.out.println("Math.pow(new Double(\"12\"),new Integer(\"1\")) = " + Math.pow(new Double("12"), new Integer("1")));

        byte tem = byt; // 如果要比较拆箱后比较。用 == 是否比较相等。
        System.out.println("byt==tem = " + (byt==tem)); //两个对象用equals，若其中一个为

        System.out.println("byt.intValue() = " + byt.intValue());
        System.out.println("String.valueOf(flot.intValue()) = " + String.valueOf(flot.intValue()));

        //如何拆箱 ?
        short i1 = sht.shortValue();
        byte b1 = byt.byteValue();
        char c = character.charValue();
        boolean b2 = bol.booleanValue();

        //装箱？
        Float aFloat = Float.valueOf(f);
        String.valueOf(sht.shortValue());
            

        // 拆箱问题
        Integer n1 = 123; Integer n2 = 123;
        Integer n3 = 128;   Integer n4 = 128;
        Integer n1x = Integer.valueOf(123); Integer n2x = Integer.valueOf("123");
        Integer n3x = Integer.valueOf(128); Integer n4x = Integer.valueOf("128");
        // 把-128~127的数字缓存起来了，用于提升性能和节省内存。所以这个范围内的自动装箱（相当于调用valueOf(int i)方法）的数字都会从缓存中获取，返回同一个数字
        // 用new Integer就不会。一般用
        System.out.println("(n1x == n1) = " + (n1x == n1)); //(n1x == n1) = true
        System.out.println("(n2x == n1) = " + (n2x == n1)); // (n2x == n1) = true
        System.out.println("(n3x == n3) = " + (n3x == n3)); // (n3x == n3) = false
        System.out.println("(n4x == n3) = " + (n4x == n3)); // (n4x == n3) = false
        System.out.println(n1 == n2);  //true
        System.out.println(n3 == n4);  //false
        System.out.println("end - Main.test\n");
```

