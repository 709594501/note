<!--
 * @Descripttion: 
 * @version: 
 * @Author: naxiaozi
 * @Date: 2022-07-04 10:18:05
 * @LastEditors: Please set LastEditors
 * @LastEditTime: 2022-07-04 10:21:06
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