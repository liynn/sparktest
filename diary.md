## TODO LIST

 - [x] 为什么存在RDD
 - [x] [RDD与闭包](https://github.com/SunnyZWQ/sparktest/blob/master/%E9%97%AD%E5%8C%85%E4%B8%8ERDD%E7%9A%84%E5%85%B3%E7%B3%BB.md)
 - [x] spark如何把数据从硬盘加载到内存
 - [x] spark如何从hdfs及其他的文件系统获取数据
 - [x] spark streaming工作流程，如何进行组件之间的关联
 - [ ] spark与Hadoop的其他组件之间如何连接
 - [x] RDD的用处有一条是“分布式文件系统将文件存储在硬盘里，这会拖慢运算速度（I/O，复制，序列化），所以我们需要RDD”。关于这个提出问题：存储在hdfs上的数据是什么时候加载到内存中的，RDD对于这个过程起到了什么作用
 - [x] spark examples 学习

----

- [x] pro4新建虚拟机（快照：JDK1.8）（新建路由器）
- [ ] ambari环境搭建
- [x] win上的虚拟机安装Git
- [x] win上的虚拟机的scrapy代码push到Git中
- [x] pro4上的毕设虚拟机git clone scrapy代码
- [ ] 将之前翻译的ambari文档使用rst格式整理
- [ ] 完善spark_to_all
- [x] 整理streaming笔记

----
streaming笔记输出

- [ ] receiver和processor的具体的交互过程
- [ ] block, interval, batch
- [ ] streaming如何实现实时交互
- [ ] update streaming application时需要注意什么
- [ ] kafka, flume之类的组件起到了什么作用
- [ ] 如果没有window，那么输入流和输出流的工作流程是怎样的
- [ ] window的应用场景


----
## 2018.03.08
- [RDD与闭包](https://github.com/SunnyZWQ/sparktest/blob/master/%E9%97%AD%E5%8C%85%E4%B8%8ERDD%E7%9A%84%E5%85%B3%E7%B3%BB.md)
- [RDD的意义](https://github.com/SunnyZWQ/sparktest/blob/master/RDD%E7%9A%84%E6%84%8F%E4%B9%89.md)
- [spark的容错机制](https://github.com/SunnyZWQ/sparktest/blob/master/spark%E7%9A%84%E5%AE%B9%E9%94%99%E6%9C%BA%E5%88%B6.md)



## 2018.03.17
- [x] 把翻译好的文档用rst格式输出
- [x] 查看uos clone包

----

## 2018.04.12

- [ ] spark sql 和 hive 对比——速度、hive的查询原理（内存or硬盘）
- [ ] 关于spark DStream 了解原理，简单介绍
- [ ] spark ml 库 介绍
- [ ] spark core —— 画图说明原理
- [ ] storm和spark实现实时处理的原理——基于内存、秒级or毫秒级、算子

----

## 2018-09-03


- python中的set类，用来构建和操作无序元素的集合，其中每个元素都是唯一的。常用法：membership testing，移除重复元素，在set上计算标准数学操作（交集、并集、区别、对称区别）

#### rotate错误答案

    class Solution(object):
        def rotate(self, nums, k):
            """
            :type nums: List[int]
            :type k: int
            :rtype: void Do not return anything, modify nums in-place instead.
            """
            i = 0
            for i in (0,k+1):
                temp = nums[len(nums)-1]
                for j in (0,len(nums)):
                    nums[len(nums)-1]=nums[len(nums)-2]
                    nums[0] = temp
                print nums
            print('最终结果')
            print nums
            return nums    
            

#### rotate正确答案

    class Solution(object):
        
        def rotate(self, nums, k):
            """
            :type nums: List[int]
            :type k: int
            :rtype: void Do not return anything, modify nums in-place instead.
            """
            k = k % len(nums)
            self.reverse(nums,0,len(nums)-1)
            self.reverse(nums,0,k-1)
            self.reverse(nums,k,len(nums)-1)
            # return nums       
            
        def reverse(self, nums, start, end):
            while(start<end):
                temp = nums[start]
                nums[start] = nums[end]
                nums[end] = temp
                start = start + 1
                end = end - 1
    








































