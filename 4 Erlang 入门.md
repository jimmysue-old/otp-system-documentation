# 4 Erlang入门
## 4.1 引言
### 4.1.1 引言
这是一个让你快速入门的Erlang教程。教程将带你领略Erlang神奇的地方，而所有这些也仅仅是Erlang的一小部分。例如，我教你Erlang最简单的语法形式，而不会涉及那些复杂的用法。与“参考手册”比起来，本文进行了很多简化。所以更多的内容只是可以参考[Erlang参考手册](./Erlang\ 参考手册.md)。

阅读本文需要你具有一定的编程基础，但不需要你具有资深经验。

### 4.1.2 不涉及的内容

本章将不涉及如下内容：
- 引用(References)
- 异常处理
- 单向连接,进程监视(monitor)
- 二进制处理(binaries / bit syntax)
- 列表解析
- 与其它语言的程序通讯。这部分内容有专门的教程[集成交互指导](集成交互指导.md).
- 几乎不涉及Erlang的库(例如文件处理)
- 跳过OTP 和 Mnesia数据库
- Erlang的哈兮表(ETS)
- 线上系统的代码变更升级

## 4.2 顺序编程
### 4.2.1 Erlang命令行
大部分操作系统都会有命令解释器或者说外壳——Unix和Linux有多个，Windows系统则会有一个命令行工具。Erang有自己的命令行，你可以在上面直接编写代码并执行，看看运行的结果(参考`shell(3)`)。在Linux或Unix系统中的启动外壳程序，键入`erl`便可启动Erlang命令行。启动后你将看到如下界面。

	% erl
	Erlang R15B (erts-5.9.1) [source] [smp:8:8] [rq:8] [async-threads:0] [hipe] [kernel-poll:false]
	Eshell V5.9.1
	1>

现在输入"2+5."，回车后结果如下

	1> 2 + 5.
	7
	2>

Windows系统下直接双击Erlang的图标便可以启动Erlang命令行。

你会发现，Erlang命令行为输入的行进行了编号(如 1> 2>),并且给出了式子2+5的正确答案：7！同时你在输入代码是必须显式地以一个英文句点"."结束，代码完成后必须回车。当然如果你不小心输错了，可以退格删除重新输入。还有许多其它的编辑命令，具体可以参考"ERTS User's Guide"的"tty - A command line interface"章节。

(注意：本教程的Erlang命令示例的行号并不保证连续，因为它们是在不同的命令行会话中测试的)

现在让我们试试更复杂的计算

	2> (42 + 77) * 66 / 3.
	2618.0

这里用到了括号，乘号"\*"和除号"/"，他们与数学的用法一样。(参考 `Erlang 参考手册`的 "数学表达式"章节。)

关闭命令行，输入 Control-C ,输出如下：

	BREAK: (a)bort (c)ontinue (p)roc info (i)nfo (l)oaded
	(v)ersion (k)ill (D)b-tables (d)istribution
	a
	%

输入"a" 推出Erlang系统

另一种推出Erlang系统的方法是输入`halt()`：

	3> halt().
	%

### 4.2.2 模块和函数





