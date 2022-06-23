<!--
 * @Descripttion: 
 * @version: 
 * @Author: naxiaozi
 * @Date: 2022-06-23 16:34:46
 * @LastEditors: Please set LastEditors
 * @LastEditTime: 2022-06-23 16:55:52
-->
# 命名规范
## 1. 包的命名(package)      
    包的命名应该遵守以下规则:       
   * 应该全部是小写字母
   * 点分隔符之间有且仅有一个自然语义的英语单词
   * 包名统一使用单数形式，比如说 com.abc.student 不能是 com.abc.students
   * 由于互联网上的域名是不会重复的，所以多数开发人员采用自己公司（或者个人博客）在互联网上的域名称作为包的唯一前缀
## 2. 类的命名(class)      
   类的命名应该遵守以下规则：   

   * 必须以大写字母开头
   * 最好是一个名词，比如说 System
   * 类名使用 UpperCamelCase（驼峰式命名）风格
   * 尽量不要省略成单词的首字母，但以下情形例外：DO/BO/DTO/VO/AO/ PO / UID 等
## 3. 字段（field）和变量（variable）   

   字段和变量的命名应该遵守以下规则：
   * 必须以小写字母开头
   * 可以包含多个单词，第一个单词的首字母小写，其他的单词首字母大写，比如说 firstNode
   * 最好不要使用单个字符，比如说 int a，除非是局部变量
## 4. 常量（constant）    
   常量的命名应该遵守以下规则：
   * 应该全部是大写字母
   * 可以包含多个单词，单词之间使用“_”连接，比如说 MAX_PRIORITY，力求语义表达完整清楚，不要嫌名字长
   * 可以包含数字，但不能以数字开头
## 5. 方法（method）    
   方法的命名应该遵守以下规则：
   * 必须以小写字母开头
   * 最好是一个动词，比如说 print()
   * 可以包含多个单词，第一个单词的首字母小写，其他的单词首字母大写，比如说 actionPerformed()    
  #### Service/DAO 层的方法命名规约：
  * 获取单个对象的方法用 get 做前缀
  * 获取多个对象的方法用 list 做前缀，复数结尾，如：listObjects
  * 获取统计值的方法用 count 做前缀
  * 插入的方法用 save/insert 做前缀
  * 删除的方法用 remove/delete 做前缀
  * 修改的方法用 update 做前缀
