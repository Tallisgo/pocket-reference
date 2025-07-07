# rsync


## 场景

有这样一个需求: 两台机器分别运行不同的服务，需要在两台机器上互相备份数据库文件


## 介绍


rsync 是一个快速而多功能的命令行工具，用于在不同的文件系统之间同步和传输文件。它是类Unix系统上常用的工具，但也可以在Windows上使用，通常通过Cygwin或WSL（Windows Subsystem for Linux）来实现。以下是一些rsync的关键功能和特点：

1. 高效的数据传输: rsync 采用一种快速的增量传输方法，只传输源和目标之间有变化的数据块，从而减少了数据传输的时间和带宽的使用。

2. 保持文件属性: 它可以选择性地保留文件的权限、时间戳、符号链接等属性，以确保同步后的文件与源文件完全一致。

3. 远程同步: rsync 支持通过SSH协议进行远程文件同步，这意味着可以在网络上的两台机器之间轻松传输文件。

4. 灵活性: 具有大量的选项和标志，允许用户根据需要定制rsync的行为，例如只同步某一类型的文件、排除某些文件或目录等。

5. 可靠的错误处理: rsync 提供详细的输出和日志，帮助用户了解同步过程中的情况，同时具备良好的错误处理能力。

6. 可用作备份工具: 由于其高效增量传输的特性，rsync 经常被用于制作文件或系统的备份。



## 用法

```bash

rsync [options] source destination

```

`source` 和 `destination` 既可以是本地路径，也可以是远程路径

常用选项：

* 



### 示例

1. 本地同步两个目录

```bash
rsync -av /path/to/source /path/to/destination/

```

2. 将本地目录同步到远程服务器

```bash
rsync -avz /path/to/source user:remote_host:/path/to/destination/

```

3. 同步时排除某些文件

```bash

rsync -av --exclude='*.bak' /path/to/source /path/to/destination

```


## 补充

* rsync 本来就不会传同步的，只传差异部分，不会传同样的