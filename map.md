<!--
 * @Descripttion: 
 * @version: 
 * @Author: naxiaozi
 * @Date: 2022-07-06 09:29:34
 * @LastEditors: Please set LastEditors
 * @LastEditTime: 2022-07-06 10:28:55
-->
# 1.Map 采用key-value的格式 无序的，key重复会覆盖前值 
## 例子    
    
    package com.imooc.cat;
    import java.util.*;
    public class MapDemo {
    public  static void  main(String [] args){
        Map<String,String> animal = new HashMap<String,String>();
        Scanner  console = new Scanner(System.in);
        int i=0;
        while (i<2){
            System.out.println("请输入key:");
            String key =console.next();
            System.out.println("请输入value");
            String value = console.next();
            animal.put(key,value);
            i++;
        }
        //展示输入的所有数据,使用迭代器
        System.out.println("使用迭代器输出");
        Iterator<String> it=  animal.values().iterator();
        while (it.hasNext()){
            System.out.println(it.next());
        }
        //使用entrySet
        System.out.println("使用entrySet");
       Set<Map.Entry<String, String>> entrySet = animal.entrySet();
       for(Map.Entry<String, String> entryset:entrySet){
           System.out.println("key:"+entryset.getKey()+" value:"+entryset.getValue());
       }
       //查找key
        System.out.println("请输入要查找的key");
       String searchWord = console.next();
       Set<String> keys= animal.keySet();
       boolean flag = false;
       for (String key:keys){
           if(key.equals(searchWord)){
               flag = true;
               System.out.println("找到了"+key+"value值为"+animal.get(key));
               break;
           }
       }
       if(flag==false){
           System.out.println("未找到");
       }

    }
    }
 # 2.map遍历的两种方式    

    package com.imooc.cat;
    import java.util.HashMap;
    import java.util.Map;
    import java.util.Set;
    public class MapDemo {
    public  static void  main(String [] args){
        Map<String,String> fruit = new HashMap<String,String>();
        fruit.put("apple","苹果");
        fruit.put("orange","橘子");
        fruit.put("banala","香蕉");
        //展示map数据的几种方式
        showKeyValueData(fruit);
        showValue(fruit);
    }
    public static void showKeyValueData(Map<String,String> fruit ){
        System.out.println("1.展示key和value值");
        Set<Map.Entry<String, String>> entryset = fruit.entrySet();
        for(Map.Entry<String, String> entry:entryset){
            System.out.println("key="+entry.getKey()+" value="+entry.getValue());
        }

    }
    //只展示value
    public  static  void showValue(Map<String,String> fruit){
        System.out.println("2.展示value");
        Set<String> values = fruit.keySet();
        for(String value:values){
            System.out.println("value="+value);
        }
    }
    }
# 综合例子    

    package com.imooc.cat;
    import java.util.*;
    public class GoodsTest {
    public static  void  main(String [] args){
        Map<String,Goods>  obj = new HashMap<String,Goods>();
        int i =0;
        while (i<2){
            System.out.println("请输入商品编号");
            Scanner console = new Scanner(System.in);
            String goodsId = console.next();
            //判断key是否存在
            if(obj.containsKey(goodsId)){
                System.out.println("商品编号存在");
                continue;
            }
            System.out.println("请输入商品名称");
            String name = console.next();
            System.out.println("请输入商品价格");
            double price =0;
            try {
                 price = console.nextDouble();
            }catch (InputMismatchException e){
                System.out.print("价格格式异常，请重新输入");
                continue;
            }
            Goods goods = new Goods(goodsId,name,price);
            obj.put(goodsId,goods);
            i++;
        }
        //对象形式的map
        Iterator<Goods>  goods=  obj.values().iterator();
        while (goods.hasNext()){
            System.out.println(goods.next());
        }

    }
}
    
    
