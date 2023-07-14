# 数据学院暑期夏令营实践项目————基于 GitHub 的Hexo博客网站

## 部署博客
本次实验需要部署一个静态网页博客，我选择了Hexo主题，部署过程
1. 环境准备
首先需要安装node.js和Git，这两项我之前已经安装过，所以直接跳过。
2. 安装Hexo
在Git中输入安装命令、初始化hexo（myblog是我新建的文件夹）
``` bash
npm install -g hexo-cli
hexo init myblog
cd myblog
npm install
```
启动服务站点
``` bash
hexo g 
hexo server
```
成功访问http://localhost:4000/ 
3. github建站访问
github新建仓库15110211.github.io（名称为用户名+.github.io），然后在_config.yml中更改deploy
``` bash
deploy:
  type: git
  repo: https://github.com/15110211/151102111.github.io.git
  branch: master
```
然后依次运行下方命令即可通过https://15110211.github.io 访问我的博客
``` bash
npm install hexo-deployer-git --save
hexo clean
hexo generate
hexo deploy
```

## 主题选取

本次博客选取了Hexo的white主题。选择原因如下：
* 刚接触hexo，想用一个简单的主题来练手，white页面极简且结构清晰易懂
* white整体简洁大方，符合我的审美
* white的基本功能完善，可以在此基础上添加别的功能

## 页面布局

本次博客菜单含有四个界面：
* Home：主页面
* Blog：博客页面，介绍多部我喜欢的动画片
* Summmary： 本次作业总结与反思
* About： 关于我


## 遇到的问题及其解决方法
### 问题

![avatar](../pic/error.png)

### 原因

运行hexo d命令时报错，原因是因为hexo d的时候改变了一些.deploy_git文件下的内容。

### 解决

1. 删除.deploy_git文件夹;
2. 输入以下命令：git config --global core.autocrlf false
3. 再重新执行：

``` bash
$ hexo clean
$ hexo g
$ hexo d
```

More info: [Deployment](https://hexo.io/docs/one-command-deployment.html)
