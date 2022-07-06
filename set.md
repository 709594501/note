<!--
 * @Descripttion: 
 * @version: 
 * @Author: naxiaozi
 * @Date: 2022-07-04 10:18:05
 * @LastEditors: Please set LastEditors
 * @LastEditTime: 2022-07-05 17:06:44
-->
# 1.集合框架
![image](https://user-images.githubusercontent.com/30765850/177070250-ee55cc92-e058-4d02-8663-330f930ca28c.png)    
# 2.集合框架的基本使用    
    
        //1.数组 只能添加整型，浮点型会报错
		int [] arr = {1,2,4.9};
		//2.集合 可以添加不同数据类型
		List list = new ArrayList();
		list.add(1);
		list.add("haha");
		System.out.println(list);
		//3.泛型 添加其他类型会报错
		List<String> list2 = new ArrayList<>();
		list2.add("123");
		list2.add(1);
# 3.集合总结
![image](https://user-images.githubusercontent.com/30765850/177070376-7865e061-ef33-4cea-9885-e320d631bcc7.png)
# 4.set用法
## 定义:set是无序的，且不可以重复，只允许一个null，具有良好的查找存取和查找性能
### set的简单使用     
		    
		Set set = new HashSet();
		set.add("black");
		set.add("red");
		set.add("pink");
		set.add("pink2");
		//迭代器
		Iterator it = set.iterator();
		while(it.hasNext()) {
			System.out.print(it.next()+" ");
		}
		System.out.println("");
		//插入重复数据,不会报错
		set.add("pink2");
		Iterator it2 = set.iterator();
		//输出的结果为：
		System.out.println("输出的结果为:");
		while(it2.hasNext()) {
			System.out.print(it2.next()+" ");
		}
    
	//对象的set的使用***********************************************
	// TODO Auto-generated method stub
		Cat huahua = new Cat("花花",10,"英国");
		Cat fanfan = new Cat("凡凡",3,"美国");
		//放入set中
		Set set = new HashSet();
		set.add(huahua);
		set.add(fanfan);
		//展示数据
		Iterator it = set.iterator();
		while(it.hasNext()) {
			System.out.println(it.next());
		}
	//定义Cat类
	package com.imooc.set;
	public class Cat {
	private String name;
	private int month;
	private String species;
	public Cat(String name, int month, String species) {
		super();
		this.name = name;
		this.month = month;
		this.species = species;
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
	public String getSpecies() {
		return species;
	}
	public void setSpecies(String species) {
		this.species = species;
	}
	@Override
	public String toString() {
		return "[名字=" + name + ", 月份=" + month + ", 品种=" + species + "]";
	}
	}
# 5.hashCode和equals的用途 
> hashCode 用来计算数据放置的位置,equals用来判断值是否相等    
## 例子
	import java.util.Set;
	import java.util.Iterator;
	import java.util.HashSet;
	package com.imooc.set;
	public class CatTest {
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Cat huahua = new Cat("花花",10,"英国");
		Cat fanfan = new Cat("凡凡",3,"美国");
		//放入set中
		Set set = new HashSet();
		set.add(huahua);
		set.add(fanfan);
		//展示数据
		Iterator it = set.iterator();
		while(it.hasNext()) {
			System.out.println(it.next());
		}
		//添加重复数据
		System.out.println("添加之后的数据");
		Cat huahua01 = new Cat("花花",10,"英国");
		set.add(huahua01);
		it = set.iterator();
		while(it.hasNext()) {
			System.out.println(it.next());
		}	
	}
	}

	public class Cat {
	private String name;
	private int month;
	private String species;
	public Cat(String name, int month, String species) {
		super();
		this.name = name;
		this.month = month;
		this.species = species;
	}	public String getName() {
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
	public String getSpecies() {
		return species;
	}public void setSpecies(String species) {
		this.species = species;
	}
	@Override
	public String toString() {
		return "[名字=" + name + ", 月份=" + month + ", 品种=" + species + "]";
	}
	@Override
	public int hashCode() {
		final int prime = 31;
		int result = 1;
		result = prime * result + month;
		result = prime * result + ((name == null) ? 0 : name.hashCode());
		result = prime * result + ((species == null) ? 0 : species.hashCode());
		return result;
	}
	@Override
	public boolean equals(Object obj) {
		
		if (this == obj)
			return true;
		if (obj == null)
			return false;
		if (getClass() != obj.getClass())
			return false;
		Cat other = (Cat) obj;
		if (month != other.month)
			return false;
		if (name == null) {
			if (other.name != null)
				return false;
		} else if (!name.equals(other.name))
			return false;
		if (species == null) {
			if (other.species != null)
				return false;
		} else if (!species.equals(other.species))
			return false;
		return true;
	}
	} 
# 6.查找指定的对象是否存在，查找指定的属性是否存在    
	 if(set.contains(xiaohua)){
            System.out.println("找到了");
            System.out.print(xiaohua);
        }else{
            System.out.println("未找到");
        }

		//查找指定名字************************************
        Cat c =null;
        boolean flag = false;
        while (it.hasNext()){
             c = (Cat) it.next();
            if(c.getName().equals("maomao1")){
                flag = true;
				break;
            }
        }
        if(flag==true){
            System.out.print("找到了");
            System.out.println(c);
        }else{
            System.out.println("未找到");
        }
# 7.删除set中的元素    

	boolean  flag = set.remove(maomao2);	
	//批量删除
	 Cat xiaohua = new Cat(10,"xiaohua","france");
        Cat maomao = new Cat(4,"maomao","china");
        Cat maomao2 = new Cat(3,"maomao2","china");
		//泛型
        Set<Cat> set = new HashSet<Cat>();
        set.add(xiaohua);
        set.add(maomao);
        set.add(maomao2);
        Iterator it = set.iterator();
        System.out.println("删除之前的元素");
        while (it.hasNext()){
            System.out.println(it.next());
        }
        //符合条件的先查找出来
        Set ids = new HashSet();
        for(Cat cat:set){
            if(cat.getMonth()<5){
                ids.add(cat);
            }
        }
        System.out.println("符合条件的有：");
        Iterator ids2 = ids.iterator();
        while (ids2.hasNext()){
            System.out.println(ids2.next());
        }
        set.removeAll(ids);
        //
       it = set.iterator();
        System.out.println("删除之后的元素");
        while (it.hasNext()){
            System.out.println(it.next());
        }




		


		