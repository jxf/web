webQQ建模
                                                                              
1 设计时间 
2013年5月26日~2013年5月29 日 

2 设计目的 
Webqq，主要用于沟通交流。本次建模主要是为了加深对web应用进行建模的理解。 

3设计任务 
Webqq与qq的功能大致相同，主要用于实现人与人之间的交流，如语音、视频、文件传输等功能，其中用户主要有账户登陆，添加好友，删除好友等功能，管理员主要有登陆，监听用户，冻结用户等功能。 
本次建模以为webqq建立系统模型为基础，给出若干系统的描述，根据给出的系统的基本需求，经过详细需求分析和系统地总体设计与详细设计，画出几种模型图：用例图(要有用例脚本的说明)，类图（初始类图、细化类图），顺序图，活动图。 

4 设计内容 
Webqq使用数据库汇集每个人的发言，然后将数据库中的发言信息显示在页面上，使每一位用户都能看到。 

系统基本需求： 
（1）用户管理：实现用户的注册，登录以及验证功能。 
（2）用户账户管理：用户管理自身基本信息，例如：上一次登录时间，积分等。 
（3）用户显示管理：显示所有的用户，在线用户以红色字体显示其名字，离线用户以灰色字体显示其名字。 
（4）用户发言：用户发言时，可以选择发言的表情（插入表情图片）以及文字的字体属性（字体大小，字体颜色等）；用户也可以选择具体的某一聊友进行单独留言，进行文件传送等；用户发言时，可插入外来图片，设置超级链接等功能。 
（5）显示发言信息：根据用户选择的字体属性显示发言信息。 
（6）管理员：删除某用户的发言信息，监听用户，冻结用户等。

4.1用例图 
以下用例图主要有三个角色，分别为member，user，manager，user主要有注册登录，好友管理，发起聊天，创建群/聊天组，用户设置，文件传输等功能，manager里主要有登陆，监听用户聊天，冻结用户三个功能。
下面是个各个功能的细分：
好友管理：修改好友管理 查找好友 添加好友 删除好友
发起聊天：发起语音聊天 发起视频聊天 发起文本聊天
用户设置：个人信息设置 系统偏好设置
文件传输：离线传输 在线传输
![alt next](http://b228.photo.store.qq.com/psb?/V10ymuAs4OUe9j/9Rli5AKx3MxIOgKSiWyvJio8jVU8C2KcH6Zk9Fs5jNo!/b/dE7J84dyAAAA&bo=IAPWAQAAAAABANM!“用例图”)


4.2类图 
类图主要有manager，user，member，manager options，database, dialog window, friends setting,system setting ,file options，user setting UI，system reaction等对象。
其中manager和user继承member对象；
    friend setting 和 system setting 继承setting type对象。
Manager
属性：manager id    manager keys
方法：manager log in

User 
属性：user name  user keys  user id 
方法：user register  user log in

Management options 
方法：
监听用户聊天 
冻结普通用户账号

Dialog window
方法：
文本聊天 
视频聊天 
语音聊天

File options
方法：
在线发送文件
离线发送文件

Database
属性：database id
方法：
存储数据 
更新数据 
删除数据

Friends setting 
方法：
查找好友 
添加好友 
删除好友
修改好友分组

System setting
方法：
用户信息修改
用户密码修改
系统偏好设置
![alt next](http://b268.photo.store.qq.com/psb?/V10ymuAs4OUe9j/ck2hXIA9GDbxpR1.sAAk*Wy46xSOrfxlEIpRvvipQsI!/b/dFnGxp.iJgAA&bo=IAPRAQAAAAABANQ!类图)
 

 


4.3时序图 
顺序图也称时序图。顺序图的定义是：顺序图是显示对象之间交互的图，这些对象是按时间顺序排序的。特别地，顺序图中显示的是参与交互图中的对象及对象之间消息交互的顺序图
![alt next](http://b228.photo.store.qq.com/psb?/V10ymuAs4OUe9j/UWpAkyptFUj3vmq2JYhrJEqnI4SdBXi6YqUsfZsEl2E!/b/dLHD8IdlAAAA&bo=3QLbAQAAAAABACI!用户注册时序图)
用户注册时序图
![alt next](http://b227.photo.store.qq.com/psb?/V10ymuAs4OUe9j/*nz4o3B*uSDrKafWPubIglqJuzLzHewJeJw5q.ci9aQ!/b/dMWPU4eyJgAA&bo=vALiAQAAAAABAHo!用户登陆时序图)
用户登录时序图

![alt next](http://b228.photo.store.qq.com/psb?/V10ymuAs4OUe9j/BeupxWqp37ZZAOScfsp6Gy2ENic0YGQuwtKZ9ADYoaI!/b/dJfs.YdjAAAA&bo=FAPiAQAAAAABANM!删除好友时序图) 
删除好友时序图

![alt next](http://b268.photo.store.qq.com/psb?/V10ymuAs4OUe9j/XqudC6Qw3xZ*KAunPmt1JGu7869*3kkK9QrcTvH8fDw!/b/dIJQyJ.ZJgAA&bo=IAP0AQAAAAABAPE!添加好友时序图)
添加好友时序图

![alt next](http://b268.photo.store.qq.com/psb?/V10ymuAs4OUe9j/npgHdHbYZEnpUxK5j0v3EhnYDxqzmYA5sk4wlM0edQw!/b/dIc3wp.cJgAA&bo=NwK9AQAAAAABAK4!文本聊天时序图)
文本聊天时序图


4.4活动图 
活动表示的是某流程中的任务的执行，它可以表示某算法工程中的语句的执行。 在活动图中需要注意区分动作状态和活动状态这两个概念。 
活动状态是原子的，不能被分解，没有内部转移，没有内部活动，动作状态的工作所占用的时间是可以忽略的。动作状态的目的是执行进入动作，然后转向另一个状态。 
活动状态是可分解的，不是原子的，其工作的完成需要一定的时间。可以把动作状态看作活动状态的特例。 
活动图对表示并发行为很有用，其应用非常广泛。一般活动图可以对系统的工作流程建模，即对系统的业务过程建模，也可以对具体的操作建模，用于描述计算过程的细节。在结构化分析和设计中，开发人员往往用流程图来描述一个算法。在UML中你没有流程图的概念，从某种意义上说，活动图的功能已包含了流程图。
![alt next](http://b268.photo.store.qq.com/psb?/V10ymuAs4OUe9j/qvE.eK0KqZEDR9Yu1V0U59PQRSjec3aPRiJokqeSOAc!/b/dL3Dw5.ZJgAA&bo=RgL7AAAAAAABAJg!用户登陆活动图)
                              用户登录活动图
![alt next](http://b228.photo.store.qq.com/psb?/V10ymuAs4OUe9j/qj8xBNKPDtBaz.5.MJzgnk1z5pdrTJG761mEORJRb5c!/b/dANO9YdtAAAA&bo=fgLfAAAAAAABAIQ!好友管理活动图)
                              好友管理活动图     
![alt next](http://b228.photo.store.qq.com/psb?/V10ymuAs4OUe9j/A9eM1lK7vdYWO4xe*VOeLFDLDXPZkD0245qXpFYvHHE!/b/dJjt.YdsAAAA&bo=EAM6AQAAAAABAA8!用户聊天活动图)    
                              用户聊天活动图
![alt next](http://b266.photo.store.qq.com/psb?/V10ymuAs4OUe9j/S8wEGtgVfGDUD.PeGjUmbphkNVnLSK2g35i86Ju40Pw!/b/dMmMj574LAAA&bo=AQL5AQAAAAABANw!具体文本聊天活动图) 
                             用户具体文本聊天活动图
5 总结与展望
通过这次设计使用UML对webqq进行建模，加深了对UML建模基础理论的理解，对web应用建模的基本过程有了更深的认识。这次设计还使用rational rose这个面向对象的设计软件，初步了解面向对象的工具，为以后的发展做了个良好的铺垫。在技术高速发展的时代，设计模式不断的更新，但设计思想不容易改变，所以加深对单一设计的技能训练，会达到触类旁通的效果。 
在实践中体会理论，在理论中理解实践。上课的时候认真听老师讲解，一些概念知识慢慢去理解，课后多做练习，熟能生巧，哪怕是你的记性再好，课后不去强化练习也没用，只有多练了，当你在做项目设计时你才能很熟练的写出你想要设计。平日在练习时若遇到不会的题目或是在项目中遇到解决不了的问题，首先不要急着去问老师，或是急着上百度搜答案，那样即使你得到了正确答案，以后在其它地方遇到同样的问题，你还是不知道怎么解决！所以说，在遇到问题时，自己先想想要怎么解决，回顾一下老师上课的内容，如果自己还是想不出什么好方法的话，也可以向同学请教请教，自己不懂的地方其他同学可能知道。如果还是没能解决，那只有问老师或是上网搜索查找相应的解决方法了。好好理解其解决思路。
