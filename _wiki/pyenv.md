---
layout: wiki
title: Python/pyenv
categories: python
description: pyenv。
keywords: Linux centos python pyenv
---

## 环境
centos

## 安装

1.安装依赖

```bash
$ sudo yum install zlib-devel bzip2 bzip2-devel readline-devel sqlite sqlite-devel openssl-devel xz xz-devel libffi-devel
```

2.安装pyenv

```bash
# reference https://github.com/pyenv/pyenv#installation
$ curl -L https://github.com/pyenv/pyenv-installer/raw/master/bin/pyenv-installer | bash
# 把 pyenv root/bin 加到path
```

> 如果文件下载失败，就直接浏览器打开 https://github.com/pyenv/pyenv-installer/raw/master/bin/pyenv-installer 把内容复制黏贴到文件，用bash执行脚本

3.安装pyenv-virtualwrrap

```bash
# reference https://github.com/pyenv/pyenv-virtualenvwrapper
$ git clone https://github.com/pyenv/pyenv-virtualenvwrapper.git $(pyenv root)/plugins/pyenv-virtualenvwrapper
```

4.常用命令

- 查看可以安装的版本 `$ pyenv install --list`
- 安装一个版本的python `$ pyenv install 3.8.7`
- 查看当前使用的python版本 `$ pyenv version`
- 查看已经安装的python版本和当前使用的版本 `$ pyenv versions`
- 使用一个 python 版本作为全局的默认 python`$ pyenv global 3.8.7`
- 使用一个 python 版本作为当前目录的默认 python，会覆盖 global的 `$ pyenv local 3.8.7`

5.国内下载python慢解决办法

```bash
v=3.8.7;p="https://npm.taobao.org/mirrors/python";wget $p/$v/Python-$v.tar.xz -P ~/.pyenv/cache/;pyenv install -v $v
```

6.异常解决
- Q: `pyenv global x.x.x` 没有生效
- A: 在~/.bashrc 后面加入 `eval "$(pyenv init -)"` [参考](https://github.com/pyenv/pyenv/issues/849)

- 有疑问可联系 972237007@qq.com

## reference

- [pyenv 安装](https://github.com/pyenv/pyenv#installation)
- [pyenv 命令参考](https://github.com/pyenv/pyenv/blob/master/COMMANDS.md#pyenv-commands)
- [pyenv-virtualenvwrapper 安装](https://github.com/pyenv/pyenv-virtualenvwrapper)
- [venv, pyvenv, pyenv, virtualenv, virtualenvwrapper, pipenv 的区别](https://stackoverflow.com/questions/41573587/what-is-the-difference-between-venv-pyvenv-pyenv-virtualenv-virtualenvwrappe)
- [使用国内python镜像安装python](https://my.oschina.net/u/2266513/blog/4916984)
