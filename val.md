<!--
 * @Descripttion: 
 * @version: 
 * @Author: naxiaozi
 * @Date: 2022-06-23 14:33:31
 * @LastEditors: Please set LastEditors
 * @LastEditTime: 2022-06-24 15:46:28
-->
# 变量
变量有四种:局部变量 成员变量 静态变量 常量
## 局部变量
定义:定义在方法内部的变量
## 成员变量
定义:定义在类内部,方法外部的变量
## 静态变量
定义:静态变量在类中以 static 关键字声明，但必须在方法构造方法和语句块之外    
静态变量的声明和使用:

    public class Test {
    //定义静态变量number
    static int number =10;
    public  static  void  main(String [] args){
        //访问静态变量,可使用 类名.静态变量名
        System.out.println(Test.number);
    }
    }
## 常量
定义:在Java中,有些数据是不会经常改变的，我们把它设置成常量，如final double PI=3.141492655

    public class Test {
    static final  double PI = 3.14;
    static int number =10;
    public  static  void  main(String [] args){

        System.out.println(Test.number); //输出10
        System.out.println(PI);//输出3.14
    }
    }