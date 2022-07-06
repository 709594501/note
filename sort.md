<!--
 * @Descripttion: 
 * @version: 
 * @Author: naxiaozi
 * @Date: 2022-07-06 14:34:59
 * @LastEditors: Please set LastEditors
 * @LastEditTime: 2022-07-06 17:05:38
-->
# 1.排序
### 1.1 整型排序    
     //普通数组的排序
        int[] a = {1,3,4,12,2};
        Arrays.sort(a);
        for(int item:a){
            System.out.println(item); //输出 1 2 3 4 12
        }
        List<Integer> list = new ArrayList<Integer>();
        list.add(2);
        list.add(5);
        list.add(1);
        System.out.println("排序前");
        for(int i:list){
            System.out.println(i); //输出 2 5 1
        }
        System.out.println("排序后");
        Collections.sort(list);
        for(int j:list){
            System.out.println(j); //输出 1 2 3
        }
### 1.2 字符串排序         
     List<String> list = new ArrayList<String >();
       list.add("hallo");
       list.add("ello");
       list.add("a");
       System.out.println("排序前");
       for (String i:list){
           System.out.println(i); //输出 hallo ello a
       }
       Collections.sort(list);
       System.out.println("排序后");
       for (String j:list){
           System.out.println(j); //输出 a ello hallo
       }   
## 2.自定义排序
### 定义类    
    package com.imooc.cat;
    public class Cat {
    private  int id;
    private  String name;
    private  int month;
    public Cat(int id,String name,int month){
        this.id= id ;
        this.name = name;
        this.month = month;
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getMonth() {
        return month;
    }

    public void setMonth(int month) {
        this.month = month;
    }

    @Override
    public String toString() {
        return "Cat{" +
                "id=" + id +
                ", name='" + name + '\'' +
                ", month=" + month +
                '}';
    }
    }

### 主方法     
   
   

     List<Cat> catList = new ArrayList<Cat>();
        Cat fanfan = new Cat(1,"aanfan",2);
        Cat huahua = new Cat(2,"cuahua",5);
        Cat maomao = new Cat(3,"baomao",20);
        catList.add(fanfan);
        catList.add(huahua);
        catList.add(maomao);
        System.out.println("排序前");
        for(Cat cat:catList){
            System.out.println(cat);
        }
        System.out.println("排序后");
        //调用比较器
        Collections.sort(catList,new NameComparation());
        for(Cat cat:catList){
            System.out.println(cat);
        }
        System.out.println("按照年龄降序排序");
        //根据年龄排序
        Collections.sort(catList,new AgeComparation());
        for(Cat cat:catList){
            System.out.println(cat);
        }

## 实现比较器1    
    package com.imooc.cat;
    import java.util.Comparator;
    public class NameComparation implements Comparator<Cat> {
    @Override
    public int compare(Cat o1, Cat o2) {
        String name1 = o1.getName();
        String name2 = o2.getName();
        int n = (name1.compareTo(name2));
        return n;
    }
    }
## 比较器2    
    package com.imooc.cat;

    import java.util.Comparator;

    public class AgeComparation implements Comparator<Cat> {
    @Override
    public int compare(Cat o1, Cat o2) {
        int age1 = o1.getMonth();
        int age2 = o2.getMonth();
        return  age2-age1;//负数 表示降序 正数表示升序
    }
    }

### 输出的结果为

    排序前
    Cat{id=1, name='aanfan', month=2}
    Cat{id=2, name='cuahua', month=5}
    Cat{id=3, name='baomao', month=20}
    排序后
    Cat{id=1, name='aanfan', month=2}
    Cat{id=3, name='baomao', month=20}
    Cat{id=2, name='cuahua', month=5} 
    按照年龄降序排序
    Cat{id=3, name='baomao', month=20}
    Cat{id=2, name='cuahua', month=5}
    Cat{id=1, name='aanfan', month=2}   
# 另外一种排序
## Goods类    
    package compartion;

    public class Goods implements Comparable<Goods> {
    private  String goodsId;
    private  double price;
    private  String name;

    public String getGoodsId() {
        return goodsId;
    }

    public void setGoodsId(String goodsId) {
        this.goodsId = goodsId;
    }

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        this.price = price;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public Goods(String goodsId, double price, String name) {
        this.goodsId = goodsId;
        this.price = price;
        this.name = name;
    }

    @Override
    public String toString() {
        return "Goods{" +
                "goodsId='" + goodsId + '\'' +
                ", price=" + price +
                ", name='" + name + '\'' +
                '}';
    }

    @Override
    public int compareTo(Goods o) {
        double price1 = this.getPrice();
        double price2 = o.getPrice();
        int n = new Double(price1-price2).intValue();
        return  n;
    }
    }
## GoodsTest类    
    package compartion;
    import java.util.ArrayList;
    import java.util.Collections;
    import java.util.List;
    public class GoodsTest {
    public  static void main(String [] args){
        Goods g1 = new Goods("sn001",15,"冰箱");
        Goods g2 = new Goods("sn002",100,"电视");
        Goods g3 = new Goods("sn003",6,"手机");
        List<Goods> goodsList = new ArrayList<Goods>();
        goodsList.add(g1);
        goodsList.add(g2);
        goodsList.add(g3);
        System.out.println("排序前");
        for(Goods goodsItem:goodsList){
            System.out.println(goodsItem);
        }
        Collections.sort(goodsList);
        System.out.println("按照价格升序");
        for(Goods goodsItem:goodsList){
            System.out.println(goodsItem);
        }

    }
    }
### 返回结果:
排序前    
Goods{goodsId='sn001', price=15.0, name='冰箱'}
Goods{goodsId='sn002', price=100.0, name='电视'}
Goods{goodsId='sn003', price=6.0, name='手机'}   
排序后     
Goods{goodsId='sn002', price=100.0, name='电视'}
Goods{goodsId='sn001', price=15.0, name='冰箱'}
Goods{goodsId='sn003', price=6.0, name='手机'}
    
    
    
               