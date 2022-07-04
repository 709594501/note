<!--
 * @Descripttion: 
 * @version: 
 * @Author: naxiaozi
 * @Date: 2022-06-24 16:09:00
 * @LastEditors: Please set LastEditors
 * @LastEditTime: 2022-06-24 16:13:29
-->
# 抽象方法
定义:没有方法体的方法，称为抽象方法    

    abstract  class Abusruct 
    {
        abstract void eat();
    }
# 抽象方法的重写
一个类继承抽象类，必须重写父类的抽象方法    
    
    public class MyAbsDemo extends  Abusruct {

    @Override
    void eat() {
        System.out.print("重写父类方法");
    }
    public static void main(String[] args){
        Abusruct ab = new MyAbsDemo() ;
        ab.eat();
    }
    }
### 运行结果
输出：重写父类方法

