# 进程和线程


## 进程

- 进程就是上下文切换之间的程序执行的部分。是运行中的程序的描述，也是对应于该段CPU执行时间的描述
- 在软件编码方面，我们说的进程，其实是稍不同的，编程语言中创建的进程是一个无限loop，对应的是tcb块。这个是操作系统进行调度的单位。所以和上面的cpu执行时间段还是不同的
- 进程，与之相关的东东有寻址空间，寄存器组，堆栈空间等。即不同的进程，这些东东都不同，从而能相互区别

## 线程

线程是共享了进程的上下文环境，的更为细小的CPU时间段。线程主要共享的是进程的地址空间

