**一旦Jekyll安装成功后，搭建一个Jekyll站点通常包括下面几步：**  

1. 设定站点的基本结构，使用HTML和Liquid模板语言创建网页布局。  
2. 创建一些帖子，或者从你以前的博客平台导入。  
3. 在本地测试站点，查看效果。  
4. 部署你的网站。  

**一个典型的Jekyll站点通常具有如下结构：**   

	.
	|-- _config.yml
	|-- _includes
	|-- _layouts
	|   |-- default.html
	|   `-- post.html
	|-- _posts
	|   |-- 2007-10-29-why-every-programmer-should-play-nethack.textile
	|   `-- 2009-04-26-barcamp-boston-4-roundup.textile
	|-- _site
	`-- index.html   

_config.yml  
保存Jekyll配置的文件。虽然绝大部分选项可以通过命令行参数指定，但将它们写入配置文件可以使你在每次执行时不必记住它们。  

_includes/  
该目录存放可以与_layouts和_posts混合、匹配并重用的文件。Liquid标签{% include file.ext %}可以用于嵌入文件_includes/file.ext。  

_layouts/  
该目录存放用来插入帖子的网页布局模板。页面布局基于类似博客平台的“一个帖子接一个帖子”的原则，通过YAML前置数据定义。Liquid标签用于在页面上插入帖子的文本内容。  

_posts/  
该目录下存放的可以说成是你的“动态内容”。这些文件的格式很重要，它们的命名模式必须遵循 YEAR-MONTH-DATE-title.MARKUP 。每一个帖子的固定链接URL可以作弹性的调整，但帖子的发布日期和转换所使用的标记语言会根据且仅根据文件名中的相应部分来识别。  

_site/  
这里是Jekyll用以存放最终生成站点的根路径位置。也许把它加到你的 .gitignore 列表中会是个不错的主意。  

**运行Jekyll**  

	$ jekyll --server  

然后在浏览器中访问 http://localhost:4000 或 http://0.0.0.0:4000 。  

**创建一篇日志**   

发布日志前,先在配置文件_config.yml中设置URL格式  

	$permalink: /:year/:month/:title.html   

	$rake post title="xxxxxxxxxxxxxx" //这个名字将会在url中呈现，所以尽量短些好  
	Creating new post: ./_posts/yyyy-mm-dd-xxxxxxxxxxxx.md   
 
**创建一个页面**  

	Creating new page: ./about.md
	$rake page name="about.md"  

**创建一个嵌套的页面**  

	$rake page name="pages/about.md"
	Creating new page: ./pages/about.md

**创建一个路径页面**  

	$rake page name="pages/about"
	Creating new page: ./pages/about/index.html  

