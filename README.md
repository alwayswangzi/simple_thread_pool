# simple_thread_pool
基于Linux/C++实现的简单线程池

该线程池主要包括以下4个组成部分

1. 线程管理器：用于创建并管理线程池。
2. 工作线程：线程池中实际执行任务的线程。在初始化线程时会预先创建好固定数目的线程在池中，这些初始化的线程一般处于空闲状态。
3. 任务接口：每个任务必须实现的接口。当线程池的任务队列中有可执行任务时，被空间的工作线程调去执行（线程的闲与忙的状态是通过互斥量实现的），把任务抽象出来形成一个接口，可以做到线程池与具体的任务无关。
4. 任务队列：用来存放没有处理的任务。提供一种缓冲机制。实现这种结构有很多方法，常用的有队列和链表结构。

流程图如下
![](./thread_pool.jpg.jpg)
