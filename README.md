# 简介
VueMarkdownBlog 是基于Vuejs框架及markdown格式的静态博客生成器。超简单配置，通过markdown写作博客。
![VueMarkdownBlog-cover](img/VueMarkdownBlog-cover.jpg)

## 演示

* http://www.jmwjl.com
* http://blog.jmwjl.com 

## 特性
静态站点生成器有很多，如nuxt,vuepress,hexo等。
这类生成器为保证SEO友好，会先将Markdown文件转化成HTML文件再打包发布。

而VueMarkdownBlog不通过打包工具将markdown文件转化成HTML文件。而是通过异步加载markdown文本，通过[vue-showdown](https://vue-showdown.js.org/zh/guide/#npm) 组件将markdown在前端转化成HTML。



VueMarkdownBlog 可直接部署到服务器访问。本地服务器也可以，但通过file://形式访问不行。

> Tip: built files are meant to be served over an HTTP server.
  Opening index.html over file:// won't work.


VueMarkdownBlog 可以对站点信息、分类、及友情链接做配置。如果你想修改博客主题风格或增加功能，可以访问源项目文件，其工程文件在 [VMblog](https://github.com/mzhren/vmblog)。





## 使用
### 写博文
![项目目录](img/projects.png)

#### posts.json
posts.json 文件是项目的本地数据库文件，新写一篇文章需向数据库添加一条记录,如写一篇测试文章，需要在JSON数组里添加以下内容：
```json
{
    "title": "测试一篇新文章",
    "description": "文章内容描述",
    "status": "published",
    "tags": [],
    "date": "",
    "dateModified": "", 
    "coverImage": "",
    "category": "social",
    "slug": "newblog_for_test" 
  }
```
#### 文章内容
根据新建文章的slug,需要在posts目录下新建名为"newblog_for_test"的文件夹，在 newblog_for_test 目录下新建index.md文件。

index.md 的内容将被异步取得转化成html,以博文的形貌呈现。

#### 文章创建时间
可以通过VSCode编辑器自定义用户代码片段，如markdown.json:
```json
{
	"head": {
		"prefix": "head",
		"body": [
			"# $1 ",
			":monkey_face: 狂奔的男尸  :clock1: $CURRENT_YEAR-$CURRENT_MONTH-$CURRENT_DATE $CURRENT_HOUR:$CURRENT_MINUTE:$CURRENT_SECOND  :open_file_folder:  $2 "
		],
		"description": "markdown user post head"
	}
}
```

在md文档中输入`head` + tab 即可得到：
```markdown
#  
:monkey_face: 狂奔的男尸  :clock1: 2020-03-10 16:16:36  :open_file_folder:   
```
其中：
+ :monkey_face: 作者头像
+ :clock1: 时间符号 
+ :open_file_folder: 分类符号
  
效果：
![markdown](img/md_template.png)

## 配置
### 站点配置
site_config.json 文件：
```json
{
    "title": "寂寞我就撸",
    "description": "只要我撸得够快，寂寞就抓不住我",
    "author": "狂奔的男尸",
    "author_link": "http://www.mzh.ren/",
    "copyright": "Copyright © 2020<a href='http://blog.jmwjl.com'>寂寞我就撸</a>  | <a rel='nofollow' target='_blank' href='http://www.beian.miit.gov.cn/'>粤ICP备14094633号</a>"
}
```
### 文章类别设置

category.json
```json
[
    {
        "name": "阅读笔记",
        "slug": "reading-notes"
    },
    {
        "name": "无病呻吟",
        "slug": "shenyin"
    },
    {
        "name": "篮球日记",
        "slug": "basketball"
    },
    {
        "name": "诗词歌赋",
        "slug": "poem"
    },
    {
        "name": "生活随笔",
        "slug": "life"
    },
    {
        "name": "社会观察",
        "slug": "social"
    },
    {
        "name": "影音娱乐",
        "slug": "movie"
    },
    {
        "name": "文艺创作",
        "slug": "write"
    }
]
```
### 友情链接配置
blogroll.json
```json
[
    {
        "site": "码中人",
        "url": "http://www.mzh.ren/",
        "description": "'码中人'是一个帮助开发者成长的社区，技术文章由'码中人社区'的技术大牛和极客共同编辑为你筛选出最优质的干货，其中包括：Android、iOS、前端、后端等方面的内容"
    },
    {
        "site": "大众消弱手册",
        "url": "http://www.dzxfsc.com",
        "description": "「大众消费手册」面向大众生活、是一个汇集广大网友消费经验的平台，提供丰富的优惠信息、特价资讯。"
    }
]
``` 






