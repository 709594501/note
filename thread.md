<!--
 * @Descripttion: 
 * @version: 
 * @Author: naxiaozi
 * @Date: 2022-07-04 14:29:32
 * @LastEditors: Please set LastEditors
 * @LastEditTime: 2022-07-04 15:49:26
-->
# 1.进程的概念
## 进程:是对运行时程序的封装，是系统进行资源调度和分配的基本单位，实现了操作系统的并发
## 线程:是进程的子任务，是CPU调度和分派的基本单位，实现了进程内部的并发
### 方便理解：进程就是你开了一把游戏，线程就是游戏里边的英雄或者小兵
# 2.线程调用的两种方式
## 方式1:继承Thread

    public class ThreadTest extends  Thread {
        public  void  run(){
        for(int i=0;i<5;i++){
            System.out.println(getName()+"打了第"+i+"个小兵");
        }
    }
    }    
    //测试类调用
    public class ThreadDemo {
    public  static  void  main(String [] args){
        ThreadTest t1 = new ThreadTest();
        ThreadTest t2 = new ThreadTest();
        ThreadTest t3 = new ThreadTest();
        t1.setName("小明");
        t2.setName("小红");
        t3.setName("xiao");

        t1.start();
        t2.start();
        t3.start();
    }
    }

### 输出结果:
![image](https://user-images.githubusercontent.com/30765850/177102439-fa244266-bdcc-4956-85b8-b5ab8ac4e976.png)    

## 方式2:实现Runnable
    
    public class MyRunnable implements  Runnable {
    @Override
    public void run() {
        for (int i = 0; i < 5; i++) {
            try {//sleep会发生异常要显示处理
                Thread.sleep(20);//暂停20毫秒
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println(Thread.currentThread().getName() + "打了:" + i + "个小兵");
        }
    }
    }
    //具体调用
    public class RunnableTest {
    public  static  void  main(String [] args){
        MyRunnable mr = new MyRunnable();
       Thread t1 = new Thread(mr,"张飞");
        Thread t2 = new Thread(mr,"关羽");
        Thread t3 = new Thread(mr,"刘备");
        t1.start();

        t2.start();
        t3.start();
        }
        }   
### 结果为:   
![image](https://user-images.githubusercontent.com/30765850/177103130-7dfdfb4e-2337-410f-bfb8-f1af03eee037.png)     
#### 两种方式结果是一样的，交替执行
# 4.join 用法    
    
        MyRunnable mr = new MyRunnable();
       Thread t1 = new Thread(mr,"张飞");
        Thread t2 = new Thread(mr,"关羽");
        Thread t3 = new Thread(mr,"刘备");
        t1.start();
        try{
            //等t1执行完毕，才会轮到t2和t3执行
            t1.join();
        }catch (InterruptedException e){
            e.printStackTrace();
        }
        t2.start();
        t3.start();   

### 结果为：
![image](https://user-images.githubusercontent.com/30765850/177104078-cc3677e2-d7f6-4df5-a4bc-e45bbce9ed27.png)    
 > 测试类调用    

 > 测试2       




