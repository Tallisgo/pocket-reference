# Linux bash 

## 基本规则

1. bash 脚本里要么全是大写，要么全是小写；



## 指定参数

1. 位置参数

按顺序参数参数

```bash
#! /bin/bash

echo "第一个参数: $1"
echo "第二个参数: $2"
```

```bash
run.sh "v1" "v2" "v3"
```


2. 默认值和参数检查

```bash

#!/bin/bash

arg1=${1:-"default1"}  # 如果 $1 未设置，使用 "default1"
arg2=${2:-"default2"}

echo "参数 1: $arg1"
echo "参数 2: $arg2"


```


运行方式：
```bash
./script.sh

./script.sh foo bar
```


3. 环境变量传参数

通过 `export` 设置环境变量，脚本中直接读取

```bash

#!/bin/bash

echo "用户名: $USERNAME"
echo "端口号: $PORT"


```

运行方式:

```bash

export USERNAME="admin"
export PORT="8080"
./script.sh
```


4. env 指定环境变量

```bash
.env:

LOCAL=Fla
REMOTE=Bud

```

运行方式:

```bash

. .env || exit 1
echo $LOCAL

echo $REMOTE

```


## shellcheck

ShellCheck 是一个静态分析工具，用于检查 Bash/Shell 脚本 中的语法错误、潜在问题和不规范写法。它可以帮助你：

* 发现常见的 Shell 脚本错误（如未引用的变量、错误的比较操作）。

* 提供修复建议，提高脚本的健壮性和可移植性。

* 适用于 Bash、sh、dash、ksh 等 Shell 脚本。


1. 安装

```bash

sudo apt install shellcheck
```

2. 用法

* 检查单个脚本

```bash

shellcheck script.sh

```


* 检查目录下所有脚本

```bash
shellcheck *.sh

shellcheck **/*.sh
```
