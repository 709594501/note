<!--
 * @Descripttion: 
 * @version: 
 * @Author: naxiaozi
 * @Date: 2022-06-28 09:00:00
 * @LastEditors: Please set LastEditors
 * @LastEditTime: 2022-07-04 10:16:14
-->
# String字符串使用
## 定义字符串的两种方式

        //方式1
        String s1 = "Hello";
        //方式2
        String s2 = new String("test");
## 几个常用的方法
1.字符串长度    

    String s1 = "Hello";
    System.out.println(s1.length()); //输出5     
2.取出指定位置的字符    

    String s1 = "Hello";
    System.out.println(s1.charAt(2)); //输出l    
3.取出子字符串    

    //取出子字符
    String s1 = "Hello";
    System.out.println(s1.substring(2));//输出llo  
    //取出子字符,从指定位置开始，指定位置结束
    String s1 = "Hello";
    System.out.println(s1.substring(1,3));//输出 el    
4.查找字符出现的位置    

    //查找字符串出现的位置
    String s1 = "Hello";
    System.out.println(s1.indexOf("l"));//返回2
    //查找字符串出现的位置,从指定位置开始
    String s1 = "Hello ollo";
    System.out.println(s1.indexOf("l",4)); //输出7    
5.查找字符串最后出现的位置    

    //查找字符串最后出现的位置
    String s1 = "Hello ollo";
       System.out.println(s1.lastIndexOf("l")); //输出8
6.字符串和字节流转换
    
        String str = new String("java测试");
        //字符串转字节
        byte [] arrs = str.getBytes();
        for (int i=0;i<arrs.length;i++){
            System.out.println(arrs[i]);
        }
        //字节转字符串
        String str2 = new String(arrs);
        System.out.print(str2);
输出的结果为:
    
106 97
118
97
-26
-75
-117
-24
-81
-107
java测试

7.String 在内存空间的表示
#### 定义变量为    
 String str1 = "imooc"     
 String str3 = new String("imooc");    
 我们看看内存空间的变化    
 ![alt](https://user-images.githubusercontent.com/30765850/177068091-4794daaf-035b-453c-a929-e296f90d6be2.png)
 ![image](https://user-images.githubusercontent.com/30765850/177069708-560e1475-be46-4979-bd83-83deff0aea72.png)    
 
 产生了内存浪费    

 ![image](https://user-images.githubusercontent.com/30765850/177069764-a9327d9a-9f11-4b31-bb8c-09d2ca4bb6b1.png)

     
8.equals和==的区别    
==比较的是地址,equals比较的字符串
    
        String str1 = "hello";
        String str4 = "hello";
        String str2 = new String("hello");
        String str3 = new String("hello");
        System.out.println("str1和str2地址是否相等:"+(str1==str2));
        System.out.println("str2和str3地址是否相等:"+(str2==str3));
        System.out.println("str1和str2是否相等:"+str1.equals(str2));
        System.out.println("str1和str4地址是否相等:"+(str1==str4));

结果为：    
![image](https://user-images.githubusercontent.com/30765850/177069216-8d3e457c-9df1-4eb5-a963-bb1116f042d5.png)    
9.StringBuilder用法

    //append的用法
        StringBuilder str = new StringBuilder("hello");
        System.out.println(str.append(",你好"));
        System.out.println(str);
        //字符串替换 hello,你好 替换为 厦门,你好
        //System.out.println("替换后:"+str.delete(0, 5).insert(0, "厦门"));
        System.out.println("替换后:"+str.replace(0, 5, "厦门"));
        //将字符串取出 厦门
        System.out.println(str.substring(0,2));         
    
     