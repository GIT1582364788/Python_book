# 第3节：队列 queue
## 概述
queue模式实现了多生产者多消费者队列，当必须在多个线程之间安全地交换信息时，它在线程编程中特别有用。
## 常用组件
```
class queue.Queue(maxsize=0)
class queue.LifoQueue(maxsize=0)        LIFO队列
class queue.PriorityQueue(maxsize=0)    优先级队列
class queue.SimpleQueue                 无界的FIFO队列
exception queue.Empty          对象为空时，调用get()get_nowait()
exception queue.Full           对象为满时，调用put()get_put()
```
## Queue  
## LifoQueue        
## PriorityQueue
### 常用方法
* qusize() 返回队列大小
* empty() 队列是否为空
* full() 队列是否为满
* put(item,block=Ture,timeout=None)  
 （将item 放入队列block 设置是否阻塞，一般为Ture timeout 超时）
* get(block=True,time=None) 从队列中获取并删除元素
* get_nowait()  相当于get(False)
### 提供了两种方法来支持跟踪已加入队列的任务是否已被守护进程使用者线程完全处理。
* task_done()
```
在完成一项工作后，Queue.task_done() 函数向任务已经完成的队列发送一个通知
```
* join()
```
实际上意味着等到队列为空，再执行别的操作
```
## SimpleQueue 常用方法同上
