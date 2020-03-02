# 简介
VueMarkdownBlog 是基于Vuejs框架及markdown格式的静态博客生成器。超简单配置，通过markdown写作博客。
![aaa](http://img.mzh.ren/jmwjl-responsive.png)

## 特性
静态站点生成器有很多，如nuxt,vuepress,hexo等。
这类生成器为保证SEO友好，会先将Markdown文件转化成HTML文件再打包发布。

而VueMarkdownBlog不通过打包工具将markdown文件转化成HTML文件。而是通过异步加载markdown文本，通过[vue-showdown](https://vue-showdown.js.org/zh/guide/#npm) 组件将markdown在前端转化成HTML。

VueMarkdownBlog可直接部署使用，源工程文件在 [VMblog](https://github.com/mzhren/vmblog)。


## 演示

* http://www.jmwjl.com
* http://blog.jmwjl.com 


## 使用
### 写博文
![项目目录](http://img.mzh.ren/截图_20200302112954.png)

#### posts.json
posts.json 文件是项目的本地数据库文件，新写一篇文章需向数据库添加一条记录,如写一篇测试文章，需要在JSON数组里添加以下内容：
```json
{
    // 文章标题
    "title": "测试一篇新文章",
    // 文章内容描述
    "description": "文章内容描述",
    // 是否发布（默认都发布）
    "status": "published",
    // 标签列表
    "tags": [],
    // 创建时间
    "date": "",
    // 修改时间
    "dateModified": "", 
    // 缩略图
    "coverImage": "",
    // 文章类别（见 category.json)
    "category": "social",
    // 唯一标识
    "slug": "newblogfortest" 
  }
```
#### 文章内容
根据新建文章的slug,需要在posts目录下新建名为"newblogfortest"的文件夹，在newblogfortest目录下新建index.md文件。

index.md 的内容将被异步取得转化成html,以博文的形貌呈现。




