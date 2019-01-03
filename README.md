Traslate of original file [README.md](https://github.com/shenliyang/hexo-theme-snippet/blob/master/README.md) by Google
# hexo-theme-snippet

Snippet is simple and not simple, maybe a long-awaited hexo theme.

If this topic is also your favorite dish, please move your finger [Star](https://github.com/shenliyang/hexo-theme-snippet/stargazers) support:pray:

[![Build Status](https://www.travis-ci.org/shenliyang/hexo-theme-snippet.svg?branch=master)](https://www.travis-ci.org/shenliyang/hexo-theme-snippet)
[![Read the Docs](https://img.shields.io/readthedocs/pip/stable.svg)](https://github.com/shenliyang/hexo-theme-snippet/blob/master/README.md)
[![codebeat badge](https://codebeat.co/badges/6ef2dcd2-af90-40e0-9628-ac689441f774)](https://codebeat.co/projects/github-com-shenliyang-hexo-theme-snippet-master)
[![mnt-image](https://img.shields.io/maintenance/yes/2018.svg)](../../commits/master)
[![ImgBot](https://img.shields.io/badge/ImgBot-build-brightgreen.svg)]()
[![hexo version](https://img.shields.io/badge/hexo-%3E%3D%203.0-blue.svg)](http://hexo.io)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/shenliyang/hexo-theme-snippet/blob/master/LICENSE)

[Theme Preview Demo](http://shenliyang.github.io)

![hexo-theme-snippet](http://7xpw2b.com1.z0.glb.clouddn.com/hexo-sinppet/img/snippet-screenshots1000.jpg "Snippet theme")

## Theme Features

- [x] native JavaScript implementation
- [x] style support CSS preprocessor Less, custom theme customization
- [x] article expiration reminder function
- [x] article reading progress bar
- [x] website announcement function
- [x] Home Image lazy loading
- [x] Home article thumbnails Automatically retrieve pictures within the article, support automatic random images
- [x] supports response
- [x] detection and warning of IE
- [x] comment system support friendly and Gitment
- [x] copyright information can be configured
- [x] support site statistics and article push
- [x] Simple design of the mobile side
- [x] supports code highlighting and supports custom highlight styles
- [x] support shell script One key to use Travis CI to continuously deploy Hexo blog


# **Fundamentals**

> If you are using the `Hexo 2.x` version before, in order to avoid unknown errors, please back up your data or create a new blog directory

### 1.  Environment to build

Need to `Node.js` environment,` Git` environment and `Hexo`, if you have not installed or do not understand` Hexo`, please refer to [official tutorial](https://hexo.io/en/docs/index.html) to understand and install. If you need to build a tool, please install it yourself or use the Gulp method of this topic.


### 2. Download the theme

There are two ways to get this topic - download the `.zip` file and pass the `git` way:

1. Download [Snippet Theme](https://github.com/shenliyang/hexo-theme-snippet) File decompression placed in the `themes` directory, and the blog in the landscape for the same level directory

2. Git mode, in the Hexo root directory execution:
``` bash
    git clone https://github.com/shenliyang/hexo-theme-snippet.git themes/snippet
```

### 3. Install the plugin

Because **hexo-theme-snippet** uses the `ejs` template engine,` Less` CSS precompiled languag0e, and on the basis of official plugins.
To carry out the development of the function, the following is necessary plug-ins:

``` bash
npm i hexo-renderer-ejs hexo-renderer-less hexo-deployer-git -S
```

### 4. Deploy the theme

> If you have not changed the theme source file you can skip step 1 or 2


1. Gulp package build, compression optimization pre-deployment code.  [Gulp Getting Started Guide](http://www.gulpjs.com.cn/docs/getting-started/)
``` bash
    npm install   // install project dependencies
```

2. Copy the gulpfile.js file to the project root directory (non-thematic directory)
``` bash
    gulp or gulp default // perform the packing task
```

3. Empty hexo static files and cache and rebuild them
``` bash
    hexo clean && hexo g // clear the cache and generate a static file
```

4. Local preview, there is no problem before the release
``` bash
     hexo s -p 4000 or hexo s // start local service default
```

5. When gulp is finished and prompts `please execute: hexo d`, it can be published
``` bash
    hexo d or gulp deploy // deployment release
```


### 5. Update the theme

Topics may be updated and updated from time to time, update the subject code:

``` bash
    cd themes/snippet
    git pull
```

# **Theme**

### 1. Theme configuration

``` yaml

# layout - layout related
# language: en default language

## menu - navigation menu display {[@page: name, @ url: address, @ icon: icon]}
menu:
- page: home
  url: /
  icon: fa-home

## favicon - site icon location {@favicon}
favicon: /favicon.ico

## rss --rss file location {@rss}
rss: /atom.xml


# Set the gadgets

## widgets - 6 left widgets {@widgets: [notification, category, archive, tagcloud, friends]}
widgets:
- search
- notification
- social
- category
- archive
- tagcloud
- friends

# Set the gadgets

## Hledání
jsonContent:
  searchLocal: true // Enable local search
  searchGoogle: true // Enable Google search
  posts:
    title: true
    text: true
    content: true
    categories: false
    tags: false


## notification config - website announcement settings, support html and plain text
notification: |-
            <p>The theme is online! Welcome to download or update ~ <br/>
            Theme download: <a href="https://github.com/shenliyang/hexo-theme-snippet" title="fork me" target="_blank">Snippet theme</a> <br/>
            <hr/>Acceptance of contributions, including not limited to submission of questions and requirements, repair code. Welcome to Pull Request.<br/> Support topic: <a href="https://github.com/shenliyang/hexo-theme-snippet/stargazers">Star一about</a></p>

## social settings {@name: social tool name, @ icon: social tool icon, @ href: set tool link} [reference icon] (http://fontawesome.io/icons/)
social:
 - name: Github
   icon: git
   href: //github.com/shenliyang

## Article classification settings {@cate_config:{@show_count: Whether to display numbers, @ show_current: whether to highlight the current category}}
cate_config:
   show_count: true
   show_current: true

## article archive settings {@arch_config: / * parameter reference: https: //hexo.io/zh-cn/docs/helpers.html#list-archives*/}
arch_config:
   type: 'monthly'
   show_count: true
   order: -1

## friend chain settings {@ link name: link address {@links: [,,,]}}
links:
    - 主题作者: http://www.shenliyang.com


# Theme customization personalized configuration

## website slogan {@branding: website slogan (do not set to show the local picture)}
branding: Never so simple and funny

## lazy loading image placeholders
placeholder: ./img/loading.gif // For friendliness, no changes are recommended

## Home article list thumbnails
### loading rules: custom article thumbnails ('img' fields added in Front-matter>> pictures in articles> defaultImgs (random access)> no graph mode list

## Customize random images
defaultImgs:
  - http://www.example.jpg // Remote picture link example
  - /img/default-1.jpg // Example of local image link

## Intercept articles Home Description Word Count
excerptLength: 120

## When there is no directory when the display text, the default is 'no'
noCategoryText: 'no'

## Code Highlight Configuration {@highlightTheme: Topic Name (default is default)}
Topic name：[Reference site](https://cdnjs.com/libraries/highlight.js)
## Commonly configurable name[default,github,foundation,googlecode,monokai-sublime,monokai,monokai,xcode,vs2015,tomorrow,hybrid]

highlightTheme: default

## Article expiration reminder function {@warning:{days:临界天数(默认300天,设置0关闭功能),text:提醒文字/*%d为过期总天数占位符*/}}
warning:
  days: 300
  text: '本文于%d天之前发表，文中内容可能已经过时。'

## 文章内声明{@declaration: {enable:是否开启,title:声明标题,tip:提示内容}}
declaration:
  enable: true
  title: '转载声明'
  tip: |-
      商业转载请联系作者获得授权,非商业转载请注明出处 © <a href="" target="_blank">Snippet</a>


## 主题评论

### gitment
gitment:
  enable: false
  owner:
  repo:
  client_id:
  client_secret:
  labels:
  perPage:
  maxCommentHeight:

### 来必力(默认选项)
livere:
  enable: true
  livere_uid:

### 友言评论(服务不稳定，经常无法加载)
uyan:
  enable: false
  uyan_id:

### Disqus评论(需要翻墙，或者搭建代理)
disqus:
  enable: false
  shortname: snippet
  count: false

### 畅言评论(需要ICP备案)
changyan:
  enable: false
  appid:
  conf:

### Valine评论 参考网站: [valine评论](https://valine.js.org/)
  valine:
   enable: true
   appId:
   appKey:
   placeholder: 说点什么吧
   notify: false // 邮件通知
   verify: false // 验证码
   avatar: mm // avatar头像
   meta: nick,mail // 输入框内容，可选值nick,mail,link
   pageSize: 10


## 网站访问统计

### 网盟CNZZ统计 参考网站: [网盟CNZZ](http://www.umeng.com/)
cnzz_anaylytics:

### 百度统计 参考网站: [百度统计](https://tongji.baidu.com/)
baidu_anaylytics:

### 百度文章推送  参考网站: [百度站长](http://zhanzhang.baidu.com/)
baidu_push:

### 谷歌统计 参考网站：[谷歌统计](https://www.google-analytics.com/)
google_anaylytics:

### 腾讯分析 参考网站：[腾讯分析](http://ta.qq.com/)
tencent_analytics:

## ICON配置 (不配则启用本地Font Icon)
fontAwesome: //cdn.bootcss.com/font-awesome/4.7.0/css/font-awesome.min.css

## 网站主题配置
since: 2017  //建站时间
robot: 'all'  //控制搜索引擎的抓取和索引编制行为，默认为all
version: 1.2.1  //当前主题版本号
```

### 主题使用技巧及功能扩展
1. 修改新增文章Front-matter模板,修改`scaffolds`目录下的`post.md`模板
``` yml
---
title: {{ title }} // 标题
date: {{ date }}   // 时间
categories:        // 分类
tags:              // 标签
comments: false    // 是否开启评论
img:               // 自定义缩略图
---
```

2. 启用站内本地搜索功能

如果要使用本地站点搜索，必须安装插件hexo-generator-json-content来创建本地搜索json文件
```bash
    npm i hexo-generator-json-content@2.2.0 -S
```
然后修改主题配置_config.yml文件下`jsonContent`相关参数。

# **提升篇**

## 1. Travis CI 介绍
CI即持续集成系统。对个人而言，就是让你的代码在提交到远程(这里是GitHub)，立即自动编译，自动化测试、自动部署等。

不需要在担心更换电脑时，还要从新部署环境的问题，只要你能向远程推送文章，其他的事情就都可以交给Travis CI处理就ok了。

## 2. Travis CI 使用

> 默认前提是已经通过Github进行授权登录Travis网站，并关联了GitHub上的仓库和相关配置。
1. 拷贝主题下的`gulpfile.js` `travis.yml` `travis.sh` 到项目根目录

2. 配置travis.yml 文件
``` yml
language: node_js #使用Node语言环境
node_js: stable #安装稳定版Node

sudo: false

#cache 启用缓存，加快构建速度
cache:
  directories:
    - "node_modules"

notifications: #启用通知
  email:
    recipients:
      - snippet@91h5.cc #接收构建消息的邮件 不需要可设置为false
    on_success: never #部署成功时，可设置alway never change
    on_failure: always #部署失败时，同上

# S: Build Lifecycle
install:
  - npm install  #安装依赖

before_script:
  - export TZ='Asia/Shanghai' #设置时区
  - npm install -g gulp  #全局安装Gulp
  - chmod +x _travis.sh  #授权脚本执行权限

script:
  - hexo clean && hexo g #清除缓存并生成静态文件
  - gulp #执行gulp任务

after_success: #执行成功时(以后扩展功能使用)

after_script:
  - ./_travis.sh #执行部署脚本
# E: Build LifeCycle

branches:
  only:
    - dev #需要监听部署的分支
env:
 global:
   - GH_REF: github.com/shenliyang/shenliyang.github.io.git #更改为自己git地址
```

3. 提交代码到Github，实现自动部署
4. 当 .travis.yml 配置文件修改完成后，将其提交到远程仓库的 hexo 分支下，此时如果之前的配置一切ok，我们应该能在 Travis CI 的博客项目主页页面中看到自动构建已经在开始执行了。上面会显示出构建过程中的日志信息及状态等。

## 3. 主题开发
Gulp 执行启用主题二次开发模式
``` bash
    gulp dev
```
会监听样式less或者JS文件的变动。然后执行上面的【主题发布】即可。

### 运行预览
``` bash
    hexo clean && hexo g && hexo s -p 4000
```

监听4000端口，使用浏览器打开地址`http://localhost:4000`进行预览。


# **其他**

## 感谢

在设计这款主题的时候参考了好多主题和博客的设计和创意，深表感谢！

## 贡献
接受各种形式的贡献，包括但不限于提交问题或需求，修复代码。
欢迎大家提Issue或者Pull Request。

如果觉得本主题还不错，== 欢迎  [Star](https://github.com/shenliyang/hexo-theme-snippet/stargazers)下 ==，您的支持和鼓励才是后续更新最大的动力

## 宗旨
主题宗旨：**致力主题简洁轻量，配置方便开箱即用**

> Hexo框架追求的是快速、简洁，高效。喜欢绚丽，添加各种功能，折腾的朋友，建议移步至：[wordpress官网](https://cn.wordpress.org/) | [dayup主题](http://www.shenliyang.com/dayup)

## 常见问题

#### 1. 搜索功能不能用，content.json文件找不到？

需要安装hexo-generator-json-content插件：

``` bash
npm i hexo-generator-json-content@2.2.0 -S
```

#### 2. 谷歌搜索没有响应？

如果使用谷歌搜索没有响应，确定是否已经科学上网

#### 3. 怎么设置首页文章缩略图自动检索文章内图片？

首页文章缩略图加载规则: 自定义文章缩略图 > 自动检索文章内的图片 > defaultImgs(随机获取) > 无图模式列表

在`Front-matter`中：
指定img变量 -> 为固定缩略图
不指定img变量 -> 自动检索文章内的图片


#### 4. 在url哪里可以访问到本地静态文件吗？

在主题 `source` 目录下新建文件夹，例如:  `static`文件夹，然后添加静态资源，例如: xxx.pdf文件， 访问：*`http://yoursite.com/static/xxx.pdf`*

#### 5. 这个主题有分页功能吗？

主题已经集成分页功能，在Hexo根目录下修改 _config.yml 的配置

| 参数       | 描述        | 默认值  |
| ------------- |:-------------:| :-----:|
| per_page     | 每页显示的文章量 (0 = 关闭分页功能) |  10 |
| pagination_dir     | 分页目录      |   page |

#### 6. 为什么右侧小工具标题都为英文呢？

可能是您忘记预设网站语言，而启用默认语言了，请先在 _config.yml (注意：为hexo的_config.yml配置文件，与themes在同级目录下，不是主题的配置文件!!!) 中调整 language 设定

``` bash
language: zh-CN
```

> 没有找到我需要的问题： [提Issues](https://github.com/shenliyang/hexo-theme-snippet/issues/new)


## 版本更新日志

- 增加Valine评论

## License

[MIT License](/LICENSE)
