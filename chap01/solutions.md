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



