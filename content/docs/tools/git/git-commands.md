---
title: "Git常用指令"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

* 添加与取消代理(局部)

  ```bash
  # 添加代理 其中7890是clash对外暴露的端口
  git config http.proxy http://127.0.0.1:7890
  git config https.proxy https://127.0.0.1:7890
  
  # 去掉代理
  git config --unset http.proxy
  git config --unset https.proxy
  ```

* 添加与取消代理(全局)

  ```bash
  # 添加代理
  git config --global http.proxy http://127.0.0.1:7890
  git config --global https.proxy https://127.0.0.1:7890
  
  # 去掉代理
  git config --global --unset http.proxy
  git config --global --unset https.proxy
  ```

* `git`添加别名

  在Windows系统中需要在`$PWD/etc/bash.bashrc`的尾部添加类似如下内容

  ```bash
  alias git-log="git log --abbrev-commit --pretty=oneline --graph"
  alias git-logs="git log --pretty=format:%h%x09%an%x09%ad%x09%s --graph --date=format:'%Y-%m-%d %H:%M:%S'"
  ```

  