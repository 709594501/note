<!--
 * @Descripttion: 
 * @version: 
 * @Author: naxiaozi
 * @Date: 2022-06-23 14:35:29
 * @LastEditors: Please set LastEditors
 * @LastEditTime: 2022-06-23 17:19:20
-->
# 包装类
## 1. 包装类分类    
   Java有八种基本数据类型：byte、short、int、long、float、double、boolean、char    
   Java为其提供了8种对应的包装类：Byte、Short、Integer、Long、Float、Double、Boolean、Character
## 2.包装类和基本数据类型的区别
因为Java种创建的对象都是存储在堆里的，使用的时候需要通过栈中的引用，所以常用的基本数据类型，不需要使用new在堆上创建，而是直接在栈内存中存储不创建对象，就会比较高效。   
## 3. 基本数据类型和字符串之间的转换    
        public  static  void  main(String[] args){
        //1.基本数据类型包装类和字符串之间的转换
        Integer t1 =10;
        String t2 = Integer.toString(t1);
        System.out.println("基本数据类型包装类t1转换为字符串："+t2);
        //2.字符串包装类转换为基本数据类型  
        int t3 = Integer.parseInt(t2);
        int t4 = Integer.valueOf(t2);
        System.out.println("方式1：字符串包装类t2转换为基本数据类型："+t3);
        System.out.println("方式2：字符串包装类t2转换为基本数据类型："+t4);
        } 
           
###    输出结果:    
>            
        基本数据类型包装类t1转换为字符串：10    
        方式1：字符串包装类t2转换为基本数据类型：10    
        方式2：字符串包装类t2转换为基本数据类型：10        
## 4. 普通类对象属性的默认值和包装类默认值区别
        Cat类:    
        public class Cat {
            String name;
            int month;
            double weight;
            //定义整型包装类Integer monney;
        }
        
        实例化类：
        Cat one = new Cat();
        //整型的默认值为0
        System.out.println("月份默认值:"+one.month);
        //字符串的默认值为null
        System.out.println("名字默认值:"+one.name);
        //整型包装类输出值
        System.out.print("包装类为整型金额字段默认值："+one.monney);    
### 输出结果：
>   
        月份默认值:0   
        名字默认值:null   
        包装类为整型金额字段默认值：null    
>    结论：包装类被封装为对象了，所以默认值为null
## 5. 包装类比较注意点
        Integer t1 =100;
        Integer t2 =100;
        //包装类参数值在 -128<=参数值<=127 存在，直接从缓存区（对象池）取出，没有的话，就直接实例化 Integer
        Integer t3 = 128;
        Integer t4 = 128;
        System.out.println("t1和t2比较："+(t1==t2));
        System.out.println("t3和t4比较："+(t3==t4));    

### 输出结果:
>    
    t1和t2比较：true    
    t3和t4比较：false    
## 6. 拆箱和装箱
>    装箱就是自动将基本数据类型转换为包装器类型    
>    拆箱就是自动将包装器类型转换为基本数据类型

    public static void main(String[] args) {
	// TODO Auto-generated method stub
	//自动装箱
	int t1 = 1;
	Integer t2 = t1;
	System.out.println("t2自动装箱："+t2);
	//手动装箱
	Integer t3 = new Integer(5);
	System.out.println("t3手动装箱："+t3);
	//自动拆箱
	int t4 =t1;
	System.out.println("t4自动拆箱："+t4);
	//手动拆箱
	int t5 = t2.intValue();
	System.out.print("t2手动拆箱："+t5);
    }
>    ### 输出结果:
![alt 属性文本](https://user-images.githubusercontent.com/30765850/174935040-ce1566da-a810-49fe-a6bb-1758d5ee49ff.png)
## 7. 内存空间
![alt 属性文本](https://user-images.githubusercontent.com/30765850/174936972-8c9e6107-e91c-4288-b369-5477e50d61c0.png)



