---
title: 使用hexo搭建团队博客
date: 2016-08-06
writer: 陈慢慢
categories: jser
comments: true
thumbnail:
  - http://litterfox.github.io/images/hexo_img.jpg
tags:
      - hexo

---
技术选型：hexo + hueman 主题(其他的主题也可以尝试，当然也可以基于hueman主题进行修改)。

另一方面,代码在github上，由组内成员一同维护。

## 申请团队的github账号

   邮箱：waitforarain@126.com

   密码：*******

   github账号：注册邮箱，waitforarain@126.com 密码，*******


## 项目搭建以及使用

### a.项目的初始化

  这一步的是我建立项目的步骤，我这边大致做了一些笔记。

  mac 环境下(node,git,hexo环境已有) ，在桌面建立一个文件夹 team/hexo

  npm install hexo-cli -g

  hexo init /Users/chenyazheng/desktop/team/hexo

  cd hexo

  npm install

  hexo server

  主题的切换：

  git clone https://github.com/ppoffice/hexo-theme-hueman.git themes/hueman

  注:mac 的console中会记住，github的账号密码，切换账号时需要在钥匙串中进行修改

### b.提交项目到github上


  通过 github desktop工具不是很好用，所以，我还是通过console控制台提交了

  几个命令:git status ,git add * ,git commit -a "fir " ,git push

  提交代码的时候需要删除部分文件中的.git之类的文件

### c.在windonw环境下配置开发环境，以及获取代码

  node: 安装exe文件

  git环境: 执行git的安装文件就可以,之后的操作文件的下载上上传都是通过git shell进行就可以

  hexo环境: 从github上拉取代码,https://github.com/litterFox/hexoblog.git

  注意的几个hexo的命令：

``` bash

  hexo clean 清除本地数据

  hexo g 通过模板，生成静态文件

  hexo s 部署到本地 ，默认访问地址是 localhost:4000

  hexo deploy 将本地的静态文件上传到github上去，部署成功之后，我们就可以通过litterFox.github.io访问了

  hexo new " test post" 生成新的博客文章，博客文章都是通过markdown语法来编写的，这边生成的是.md源文件

```
  至此：在windows上的基本操作，已经没有问题。

### d.团队使用的方法

  团队成员使用同一份hexo基础工程, hexo new "new post"之后，会在source中生成"new post"这样的一个文件，之后需要通过git shell将文件提交上去。

  特别需要注意的是：在修改之前，一定要获取一次最新的代码，git pull操作，修改之后，先本地跑一遍，没有问题的情况下，将代码提交到github上，提交的关键是在于，那先博文的.md文件。

  因为代码共享，所以组内的每一个人都有获取，提交，部署的权限。此外，要注意的是数据的备份，以及提交的时候，需要谨慎一些。

## 关于hueman的主题的修改

  一开始的时候，hueman主题给我们的感觉的还不是很完善，并不是十分的满足我们的需求，于是，就针对hueman进行了部分的配置和修改。

### a.修改导航栏

  吐槽：hueman的样式配置目前来看不如next的配置方便 这边的导航条的配置我仿照了淘宝FED的模块设置做了修改。

``` bash

  Home: /

  category_jser: /categories/jser

  category_conser: /categories/conser

  category_other: /categories/other

  about: /about

```
### b.添加关于我们这一页

  添加了团队介绍，以及版本的介绍。

### c.添加评论

  多说：http://litterfox.duoshuo.com  (多说域名)

  duoshuo短语: litterfox

### d.添加第三方统计

  使用的是百度统计：账号,litterfox 密码,123456all!

  百度统计：

``` bash

  <script>
  var _hmt = _hmt || [];
  (function() {
  var hm = document.createElement("script");
  hm.src = "//hm.baidu.com/hm.js?69740646c0e72f33a470f1da53da89bc";
  var s = document.getElementsByTagName("script")[0];
  s.parentNode.insertBefore(hm, s);
  })();
  </script>
  
```
