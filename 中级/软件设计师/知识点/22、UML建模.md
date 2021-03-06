[TOC]

# UML
![[Pasted image 20220427211502.png]]

![[Pasted image 20220524203656.png]]

 [万字多图|UML入门指南](https://www.baidu.com/link?url=yhGvxDkSe0utlDiFF0fkh27q5XDQ-GfkUYmVFwYe-ShSlmkukUFEUhlSXkcP5KPXtTjS3gdZN9_83Ap_bYiOMzxSa_MwTZJhVFXUJ19W79W&wd=&eqid=ad109381000295dd0000000662694251)
[产品经理的思考利器UML](https://www.baidu.com/link?url=Db4-kESutMQPDEvAuesFJpsrq6Cs750karOzrnPPwoQ31rgTuz4XQiLGnHGA0tCtqOJZ9TuEacpHPEj6FRwYPVd6gvCwXhT

## 四种关系
1. 依赖
2. 关联
3. 泛化
4. 实现

## 结构视图

静态元素
| 图的类型 | 描述                                                                         |
| -------- | ---------------------------------------------------------------------------- |
| 类图     |                                                                              |
| 对象图   | 系统某个时间段内，存在一些对象，                                             |
| 包图     | 将建模元素有序地组织起来（比如项目结构中的包，包含了好几个类）               |
| 组件图   | 组织几个普通包，有特定功能；按功能分为：模块、子系统、库、可执行文件和程序包 |
| 部署图         | 在物理系统上运行的结构，包括硬件分布、软件部署到硬件的方式                                                                             |

## 行为视图
基于[[#结构视图]]这些静态元素，产生的行为
| 图的类型 | 描述 |
| -------- | ---- |
|          |      |


# 用例图
* **包含关系**
inlcude关键字，虚线箭头
使用某个实例A前的前提实例B：**A指向B**

* **扩展关系**
extend关键字，虚线箭头，延伸
由某个实例A，产生另一个实例B：**B指向A，B由A延伸而来**

* **泛化关系**
继承关系，带三角的实线
实例B继承实例A：**B指向A**

![[Pasted image 20220503181333.png]]


# 类图与对象图
[[重点]] 考察多个类图和关系，判断他们的类名是什么、属性是什么、填多重度

* **对象图，xxx:XXX，左边为对象名，右边为类名**

* ****

![[Pasted image 20220503185004.png]]

## 多重度
描述的是当前类是几个对象，而对方是1个对象：一个对象对应多少个当前对象的关系
![[Pasted image 20220503182127.png]]

## 关系
![[Pasted image 20220503182545.png]]

1. 泛化关系
针对类的继承

2. 实现关系
针对接口

# 顺序图
[[重点]] 补充消息中的对象

![[Pasted image 20220503214804.png]]

* **调用的时间顺序**
* **动态图，对象之间的交互关系**

# 活动图
![[Pasted image 20220503215558.png]]

![[Pasted image 20220503215604.png]]

* **粗线代表并行线程和结束并发、汇合**
* **活动图还分泳道活动图**

# 状态图
> 也叫动态图

![[Pasted image 20220504111821.png]]

箭头是触发事件，某个状态因为某个触发事件，导致状态的变迁


# 通信图
协作图
顺序图的另一种表示方式，[[重点]] 与顺序图的差异：顺序图着重的是时间的先后

![[Pasted image 20220505201256.png]]

#  构件图
由构件和接口组成；
哪些可以成为构件：可复用的封装模块、类、对象、源代码、命令、脚本、数据库等可提供接口的所有物体

# 案例分析

## 案例一

* **题目**
![[Pasted image 20220505225600.png]]

![[Pasted image 20220505225620.png]]

* **第一题**
![[Pasted image 20220505213222.png]]
> 利用对象之间的关系标识图来获知对应哪个类

![[Pasted image 20220505211004.png]]

A：艺术家
B：歌曲
C：乐队
D：歌手
E：音轨
F：唱片
(1)：0..*
(2)：2..*
(3)：0..1
(4)：1..*
(5)：1..*
(6)：1

* **第二题**
![[Pasted image 20220505213206.png]]

当前音轨得知道上一条音轨和下一条音轨
所以关联是本身之间
多重度都是0..*

* **第三题**
![[Pasted image 20220505213352.png]]

![[Pasted image 20220505213530.png]]

很简单，考察经过的几种状态，找到最快一条即可
关闭->按任意键->选择歌曲->播放



## 案例二
* **题目一**
![[Pasted image 20220505225826.png]]

![[Pasted image 20220505225837.png]]

* **第一题**
![[Pasted image 20220505225857.png]]

* **第二题**
![[Pasted image 20220505225949.png]]
设计模式：状态模式
结合CFrequentFlyer和CLevel的关系（是组合关系），所以对象是CLevel对象（负责状态变迁）
travel方法：计算飞行的旅程数，判断是否需要调整当前会员的级别