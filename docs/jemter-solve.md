### 如何利用jmeter进行压测 
### 我的服务配置较低大数据量请在自己的服务器上搞下不然就崩了
    有问题或者宝贵意见联系我的QQ,非常希望你的加入！
    
>目标 （希望大家仔细研究redis.conf配置文件-本文很多基础的一带而过）

    1.如何对秒杀生成大数据量对应的用户id和token来进行压测
    2.利用jmeter进行接口压测
    
    我这个版
    在后端写模拟前端请求计算出不同的用户对应的token ， 在UserUtil类里面
    
    生成文件格式：
   ![整体流程](https://raw.githubusercontent.com/qiurunze123/imageall/master/jmeter4.png)
   
    代码类：
   ![整体流程](https://raw.githubusercontent.com/qiurunze123/imageall/master/jmeter2.png)

   ![整体流程](https://raw.githubusercontent.com/qiurunze123/imageall/master/jmeter3.png)

    利用这个类可以生成大数据量的userId和token当前也可以自己改装生成你想要的


 **利用jmeter进行接口压测**
 
    1.点击右键生成线程组一类的 
   ![整体流程](https://raw.githubusercontent.com/qiurunze123/imageall/master/jmeter5.png)
   
    2.右键线程组选择配置原件并定义http默认值
   ![整体流程](https://raw.githubusercontent.com/qiurunze123/imageall/master/jmeter6.png)
   
    3.右键监听器可以生成聚合报告等一类的
   ![整体流程](https://raw.githubusercontent.com/qiurunze123/imageall/master/jmeter7.png)
   
    4.右键线程组添加sampler 添加请求http请求具体情况更具实际的来
   ![整体流程](https://raw.githubusercontent.com/qiurunze123/imageall/master/jmeter9.png)
   
    5.右键线程组添加CSV DATA Set Config  设置用户参数和token 把生成的路径引进来
   ![整体流程](https://raw.githubusercontent.com/qiurunze123/imageall/master/jmeter8.png)

