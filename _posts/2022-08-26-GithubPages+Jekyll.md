---
title: Github Pages+Jekyll 搭建个人博客
layout: post
tags:
- 技术分享
math: true
date: 2022-08-26 15:32
---

```
博主这个个人博客网站完全是免费薅来的，主要是利用Github Pages+Jekyll搭建而成，
这种方式的博客网站适合喜欢折腾的人儿，因为写博客发布是发送到push github上面的，
然后Github会支持Jekyll自动进行解析呈现出来
```
> 下面教大家免费薅一个个人博客、个人网站

**一、Jekyll安装**

首先Jekyll是什么就不在这里赘述了，自行百度
1. 首先点击下载安装[Ruby installer](https://rubyinstaller.org/)

		进去官网点击download即可完成下载，下载后点击安装即可
2. 下载[RubyGems](https://rubygems.org/pages/download)

     进入选择zip压缩包下载即可，下载完成后进行解压，解压后用cmd进入命令端，执行以下语句
		 
		 `ruby setup.rb`
3. 完成以上后继续再命令端中执行以下语句

			`gem install jekyll`
			
4. 安装完成，我们可以用jekyll命令创建一个博客模板,打开命令行执行：

			cd d://随便选择一个放博客位置的木
				jekyll new myblog //执行该命令则创建一个名叫myblog文件夹的博客模板
				cd myblog //进入到上面创建好的模板目录
				jekyll server //cmd进入，命令执行启动
				在浏览器输入http://127.0.0.1:4000 即可浏览刚刚创建的blog
				
**二、Jekyll 主题选择**

官网上提供很多网站模板，大部分是博客模板，可免费选择下载
1. [点击](http://jekyllthemes.org/)进入官网地址选择下载

	点击Homepage可以链接到该blog Github页面，点击download可以下载该博客源码，点击demo可以预览该博客效果

2. 下载好后解压进入目录执行jekyll server即可，效果如下

	
	![]({{ 'image/github+jekyll文章/1.png' | relative_url }})
> *若下载的主题jekyll server执行失败，则用步骤二中创建的myblog目录下的Gemfile，Gemfile.lock文件替换下载的主题里面的该文件，若还不成功，则根据控制台提示的错误，可以百度到解决方案*

**三、部署到github pages**

登录进[github](https://github.com/)官网

1. 创建好仓库 myblog

   *注意：这里创建的仓库必须是public，因为免费的github pages要求仓库必须是public*
2. 进入我们上面创建好的博客模板myblog目录，将代码上传到Git托管
* git init
* git add .
* git commit -m 'first commit'
* git remote add origin https://github.com/yourname/myblog.git
* git push -u origin master（这样就是上传项目到你的main主分支）
3. 开启github pages
  进入myblog仓库的settings,拉到最下面找到Pages，具体如下操作
	![]({{ 'image/github+jekyll文章/2.png' | relative_url }})
4.  访问我们部署好的博客

	 `https://用户名.github.io/仓库名/`

**四、如何写博客和发布**

本地进入以上我们创建的myblog目录下
1. 找到_posts目录，这里面放的是我们写博客的md文件，模板会有一些博文例子在该目录下
2. 新建或复制一篇md文件，打开编辑即可，使用makedown编辑器进行编写

		```
		---
		layout: post
		title: Github Pages+Jekyll 搭建个人博客
		tags: 技术分享
		math: true
		date: 2022-08-26 15:32 
		---
		```

	 *md文章头部会加入如上格式，这里是以我下载的博客模板结构来说的，所以我每篇都会加入这部分文件头，以便jekyll识别*
 
3. 编写好文章后进行push 到远程仓库，这样github pages会自动进行解析发布
4. 以上操作后就完成文章的发布了

**五、jekyll博客模板目录结构分析**


> _posts 博客内容
> 
> _pages 其他需要生成的网页，如About页
> 
> _layouts 网页排版模板
> 
> _includes 被模板包含的HTML片段，可在_config.yml中修改位置
> 
> _assets 辅助资源 css布局 js脚本 图片等
> 
> _data 动态数据
> 
> _sites 最终生成的静态网页
> 
> _config.yml 网站的一些配置信息,配置信息通过“site.xxx”进行访问
> 
> index.html 网站的入口

jekyll语法参考：[文档](https://www.wenjiangs.com/doc/jekyll-variables)
 [官网文档](http://jekyllcn.com/docs/posts/)

**六、利用jekyll-admin插件进行博客管理**

1. 运行命令gem install jekyll-admin进行安装
2. 在_config.yml中添加如下

	`plugins:
		- jekyll-admin
	`
3. 运行命令jekyll server 启动jekyll

		直接访问http://127.0.0.1:4000/admin 就可以看到jekyll-admin的使用界面
		
4. 启动报admin找不到的话可以使用如下命令继续安装

	`bundle add jekyll-admin`
	

文章参考了某博主：[参考文章](https://www.jianshu.com/p/9f71e260925d)
