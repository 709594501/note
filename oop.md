<!--
 * @Descripttion: 
 * @version: 
 * @Author: naxiaozi
 * @Date: 2022-06-24 14:42:17
 * @LastEditors: Please set LastEditors
 * @LastEditTime: 2022-06-24 15:21:38
-->
# 面向对象
## 面向过程和面向对象的区别
面向过程侧重的是过程，一步一步去处理不同的业务，面向对象，侧重于结果。举个简单的例子，小明要去北京，目前有两张方案。   
方案1:先做在家门口公交车，再转地铁，再打车到北京中关村;    
方案2:直接包车，同样也可以到达中关村。    
虽然两种方式都到达了目的地，但是中途的过程是不一样的。
## 类的组成部分
一个类，基本组成部分为(方法+属性+构造方法)    
    
    public class Human {
    //一个普通的类构成，定义了名字，年龄，和体重字段，这些是类的属性
    String name;
    int age;
    float weight;
    //定义了eat(),sleep(),run()三个方法
    public  void eat(){
        System.out.println("hello");
    }
    public  void sleep(){
        System.out.println("睡觉");
    }
    public  void run(){
        System.out.println("跑步");
    }
    public Human(){

    }
    //状态，每个类都有一个默认的构造方法，如果没有定义，则默认不展示
    }     
## 类实例化    
    使用关键字new来初始化    
    Human obj = new Human();    
    //调用对应的吃饭方法    
    obj.eat();    

## 类实例化空间
    类的实例化实在堆中占用内存空间
## 多态
定义一个父类    
 
    public class Sharpe {
    public  void draw(){
        System.out.println("父类的画图的方法");
    }
    }
定义子类Line    

    public class Line extends  Sharpe {
    public void draw() {
        System.out.println("画线");
    }
    }


定义子类Circle    
    
    public class Circle extends Sharpe {
    public void draw() {
        System.out.println("画圆");
    }
    }
调用对应的子类    
    
    public  static  void  main(String [] args){
        Circle obj = new Circle();
        obj.draw();
        Line obj2 = new Line();
        obj2.draw();
    }
### 输出结果为：
    画圆 画线


    
