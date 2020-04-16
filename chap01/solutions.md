# Chapter 01 -- Introduction

**1. What are the two main functions of an operating system?**

> 1. 从上往下视角：
>     * 提供一个可扩展的机器：Extended Machine
> 2. 从下往上视角：
>     * 管理IO等系统资源：Resource Manager


**2. In Section 1.4, nine different types of operating systems are described. Give a list of applications for each of these systems (one per operating systems type).**

> 1. 大型机OS：
>     * 航班预订系统
> 2. 服务器OS：
>     * 语音识别转文字，如Siri
> 3. 多处理器OS：
>     * 视频处理与渲染
> 4. 个人计算机OS：
>     * 文字处理
> 5. 掌上计算机OS：
>     * 手机App，如微信（还可通过定位功能查看附近的人）
> 6. 嵌入式OS：
>     * 数码相机系统
> 7. 传感器节点OS：
>     * 物联网系统，如远程监控
> 8. 实时OS：
>     * 远程手术、操作机器
> 9. 智能卡OS：
>     * 电子支付芯片

**3. What is the difference between timesharing and multiprogramming systems?**

>1. 多道程序系统：允许用户同时允许多个**程序**
>2. 分时系统：允许多个**用户**通过终端同时访问和使用计算机
>3. 分时系统一定是多道程序系统，反之不一定，即多道程序系统不一定是分时系统（如一台计算机只允许一个用户使用）

**4. To use cache memory, main memory is divided into cache lines, typically 32 or 64 bytes long. An entire cache line is cached at once. What is the advantage of caching an entire line instead of a single byte or word at a time?**

>1. 经验证明，内存访问符合**访问局部性原则**（principle of locality of reference），即对某已访问内存附近位置的访问概率也很高，特别是对其后续内存。所以缓存整行可大大提高对其后续内存的**高速缓存命中**（cache hit）的概率。
>2. 其次，相比单个字节或字，现代计算机硬件能更快地将内存块转换为32或64字节的**高速缓存行**（cache line）。

**5. On early computers, every byte of data read or written was handled by the CPU (i.e., there was no DMA). What implications does this have for multiprogramming?**
>1. 多道程序设计的目的本就是为了当等待IO完成的时候，让CPU去做其他（除了IO以外）的事情，如果没有DMA，CPU会处理IO，从而CPU就会处于100%利用的状态，这样多道程序设计也就失去了意义。
>2. 这里（多道程序设计）假定了等待数据被复制的时间构成主要的延迟（事实上也是如此），因此多道程序设计的好处就是，CPU可以在IO因为各种原因（比如等待数据传输至串口）变得很慢时可以去做其他的事。

**6. Instructions related to accessing I/O devices are typically privileged instructions, that is, they can be executed in kernel mode but not in user mode. Give a reason why these instructions are privileged.**
>用户对IO的权限不一，要保证正在进行IO的用户（程序）不被其他的用户干扰。

**7. The family-of-computers idea was introduced in the 1960s with the IBM System/360 mainframes. Is this idea now dead as a doornail or does it live on?**
>存在。如英特尔酷睿系列处理器，使用一致架构，区别在于价格和性能。

**8. One reason GUIs were initially slow to be adopted was the cost of the hardware need- ed to support them. How much video RAM is needed to support a 25-line × 80-row character monochrome text screen? How much for a 1200 × 900-pixel 24-bit color bit- map? What was the cost of this RAM at 1980 prices ($5/KB)? How much is it now?**
>1. $25\times80=2000$ 字节
>2. $1024\times768\times24=2359296$ 字节
>3. $2359296\div1000\div5=472$ 美元 $\approx3336$ RMB
>4. $0.0885$ RMB

**9. There are several design goals in building an operating system, for example, resource utilization, timeliness, robustness, and so on. Give an example of two design goals that may contradict one another.**
>* 公平性与实时性：
>   * 公平性要求系统资源公平分配
>   * 实时性则按进程完成执行的时间分配，这就导致了不均。

**10. What is the difference between kernel and user mode? Explain how having two distinct modes aids in designing an operating system.**
>* 内核态：OS对硬件有完全访问权，能利用硬件的所有功能，CPU能执行指令集中的每条指令
>* 用户态：只能使用机器指令的一个子集。
>* 用户程序运行在用户态可以防止其访问那些影响机器控制或IO操作的指令。
>

**11. A 255-GB disk has 65,536 cylinders with 255 sectors per track and 512 bytes per sec- tor. How many platters and heads does this disk have? Assuming an average cylinder seek time of 11 ms, average rotational delay of 7 msec and reading rate of 100 MB/sec, calculate the average time it will take to read 400 KB from one sector.**
>* 磁头：$255\times2^{30}\div(255\times512\times65536\times2)=16$
>* 盘片：$16\div2=8$
>* $11+7+400\div100=22 ms$

**12. Which of the following instructions should be allowed only in kernel mode?
(a) Disable all interrupts.
(b) Read the time-of-day clock.
(c) Set the time-of-day clock. 
(d) Change the memory map.**
>(a), (c), (d).




