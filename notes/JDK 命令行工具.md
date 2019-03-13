---
title: JDK 命令行工具
created: '2019-03-13T08:13:14.233Z'
modified: '2019-03-13T09:37:20.251Z'
tags: [Java]
---

# JDK 命令行工具

## jps

显示指定系统内所有HotSpot虚拟机进程：
- `-q`：只输出 `vmid`；
- `-m`：输出主类入参；
- `-l`：输出主类名；
- `-v`：输出 `JVM` 参数。

## jstat

虚拟机统计信息监控工具：`jstat -<option> [-t] [-h<lines>] <vmid> [<interval> [<count>]]`。

- 可以用 `-options` 查看统计信息的选项，`-<option>` 是下面其中一项：
  * `-class`：监视类装载、卸载数量、总空间及类装载所耗费的时间；
  * `-gc`：监视堆状况，包括 Eden 区、2 个 Survivor 区、老年代、永久代等的容量；
  * `-gccapacity`：监视内容与 `-gc` 基本相同，但输出主要关注Java堆各个区域使用到的最大和最小空间；
  * `-gcutil`：监视内容与 `-gc` 基本相同，但输出主要关注已使用空间占总空间的百分比；
  * `-gccause`：监视内容与 `-gc` 基本相同，但输出主要关注已使用空间占总空间的百分比；
  * `-gcnew`：监视新生代GC的状况；
  * `-gcnewcapacity`：监视内容与 `-gcnew` 基本相同，输出主要关注使用到的最大和最小空间；
  * `-gcold`：监视老年代GC的状况；
  * `-gcoldcapacity`：监视内容与 `-gcold` 基本相同，输出主要关注使用到的最大和最小空间
  * `-gcpermcapacity`：输出永久代使用到的最大和最小空间；
  * `-compiler`：输出JIT编译器编译过的方法、耗时等信息；
  * `-printcompilation`：输出已经被JIT编译的方法。
- vmid：JVM id；
- interval：监视时间间隔；
- count：监视次数。

## jinfo

实时地查看和调整虚拟机的各项参数：`jinfo [option] <pid>`。

- `[option]` 是下面其中一项： 
  * `-flag <name>`：查看 JVM 参数的值；
  * `-flag [+|-]<name>`：启用禁用参数；
  * `-flag <name>=<value>`：设置参数的值；
  * `-flags`：打印所有 JVM 参数；
  * `-sysprops`：打印 JVM 系统属性。
  
## jmap

查看堆转储快照：`jmap [option] <pid>`。

`[option]` 是下面其中一项：
- `-heap`：打印堆的存储快照；
- `-clstats`：打印类加载器信息；
- `-finalizerinfo`：打印等待终结的对象信息；
- `-J<flag>`：直接传递给运行 jmap 的 JVM 参数（Passes <flag> to the Java virtual machine on which jmap is run.）；
- `-histo[:live]`：打印堆中对象的统计信息（`[:live]` 是可选的，加上会触发 GC）；
- `-dump:<dump-options>`：dump Java 堆，例如：`jmap -dump:live,file=eclipse1.bin 88962`
  <dump-options> 是下面其中一个：
  * `live`：存活的对象；
  * `format=b`：二进制文件；
  * `file=<file>`：dump 到文件。

## jhat

分析 jmap 导出的堆存储快照工具，会生成一个小型网站。

## jstack

生成虚拟机当前时刻的线程快照，主要目的是定位线程出现长时间停顿的原因：`jstack -F [-m] [-l] <pid>`。

- `-F`：当正常输出的请求不被响应时，强制输出线程堆栈；
- `-l`：除堆栈外，显示关于锁的附加信息；
- `-m`：如果调用到本地方法的话，可以显示C/C++的堆栈。
