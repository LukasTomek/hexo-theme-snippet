Traslate of original file [README.md](https://github.com/shenliyang/hexo-theme-snippet/blob/master/README.md) by Google
# hexo-theme-snippet

Snippet is simple and not simple, maybe a long-awaited hexo theme.

If this topic is also your favorite dish, please move your finger [Star](https://github.com/shenliyang/hexo-theme-snippet/stargazers) support:pray:

[![Build Status](https://www.travis-ci.org/shenliyang/hexo-theme-snippet.svg?branch=master)](https://www.travis-ci.org/shenliyang/hexo-theme-snippet)
[![Read the Docs](https://img.shields.io/readthedocs/pip/stable.svg)](https://github.com/shenliyang/hexo-theme-snippet/blob/master/README.md)
[![HitCount](http://hits.dwyl.io/shenliyang/hexo-theme-snippet.svg)](http://hits.dwyl.io/shenliyang/hexo-theme-snippet)
[![codebeat badge](https://codebeat.co/badges/6ef2dcd2-af90-40e0-9628-ac689441f774)](https://codebeat.co/projects/github-com-shenliyang-hexo-theme-snippet-master)
[![GitHub stars](https://img.shields.io/github/stars/shenliyang/hexo-theme-snippet.svg)](https://github.com/shenliyang/hexo-theme-snippet/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/shenliyang/hexo-theme-snippet.svg)](https://github.com/shenliyang/hexo-theme-snippet/network)
[![hexo version](https://img.shields.io/badge/hexo-%3E%3D%203.0-blue.svg)](http://hexo.io)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/shenliyang/hexo-theme-snippet/blob/master/LICENSE)

[Theme Preview Demo](http://shenliyang.github.io?rf=gh-demo)

![hexo-theme-snippet](http://snippet.shenliyang.com/img/snippet-screenshots1000.jpg "Snippet theme")

## Theme Features

- [x] native JavaScript implementation, go to jQuery
- [x] style supports CSS preprocessor Less for easy theme customization
- [x] Article expiration reminder function
- [x] article reading progress bar
- [x] Website announcement function
- [x] Home image lazy loading
- [x] Home article thumbnails automatically retrieve images within articles, support automatic random images
- [x] theme support responsive
- [x] support for 3D cloud tags
- [x] Support article push and article rewards
- [x] Local search and Google search in the station
- [x] Support for multiple third-party commenting systems
- [x] Support website statistics and non-garlic visitor statistics
- [x] Simple design of the mobile side
- [x] Support for code highlighting and support for custom highlight styles
- [x] Support for Shell scripts to automate the deployment of Hexo blogs via Travis CI
- [x] Support Hexo automated deployment results send mail and push to nails in real time


# **Fundamentals**

> If you are using the `Hexo 2.x` version before, in order to avoid unknown errors, please back up your data or create a new blog directory

### 1.  Environment to build

Need to `Node.js` environment,` Git` environment and `Hexo`, if you have not installed or do not understand` Hexo`, please refer to [official tutorial](https://hexo.io/en/docs/index.html) to understand and install. If you need to build a tool, please install it yourself or use the Gulp method of this topic.

> "Subject directory" => `themes\hexo-theme-snippet`, "Hexo root directory" => project home directory;
"Theme configuration" => `themes\hexo-theme-snippet\_config.yml`, "Hexo configuration" => `_config.yml` under the project home directory

### 2. Download the theme

There are two ways to get this topic - download the `.zip` file and pass the `git` way:

1. Download [Snippet Theme](https://github.com/shenliyang/hexo-theme-snippet) File decompression placed in the `themes` directory, and the blog in the landscape for the same level directory

2. Git mode, in the Hexo root directory execution:
``` bash
git clone git://github.com/shenliyang/hexo-theme-snippet.git themes/hexo-theme-snippet
```

### 3. Install theme plugin

Because **hexo-theme-snippet** uses the `ejs` template engine,` Less` CSS precompiled languag0e, and on the basis of official plugins.
To carry out the development of the function, the following is necessary plug-ins:

``` bash
npm i hexo-renderer-ejs hexo-renderer-less hexo-deployer-git -S
```

### 4. Deploy the theme

> If you have not changed the theme source file, you do not need code optimization to skip steps 1, 2, and 3.


1. Gulp package build, copy the `package.json` file in the theme directory to the Hexo root directory, and then install the project development dependencies. [Gulp Getting Started Guide] (http://www.gulpjs.com.cn/docs/getting-started/)
``` bash
Npm i //installation project dependencies
```

2. Create a file called gulpfile.js in the Hexo root directory:
``` bash
Require('./themes/hexo-theme-snippet/gulpfile');
```

3. Run gulp:
``` bash
Gulp or gulp default // perform a package task
```

4. Empty the hexo static file and cache and regenerate
``` bash
Hexo clean && hexo g //Clear the cache and generate a static file
```

5. Local preview, there is no problem to publish again
``` bash
Hexo s -p 4000 or hexo s //start local service default
```

6. When gulp finishes executing and prompts `please execute: hexo d`, it can be published
``` bash
Hexo d or gulp deploy // deployment release
```

### 5. Update the theme

Topics may be updated and updated from time to time, update the subject code:

``` bash
cd themes/hexo-theme-snippet
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
   format: 'YYYY年MM月'
   show_count: true
   order: -1

## Tag Cloud Settings{/*Parameter Reference: http://www.goat1000.com/tagcanvas-options.php */}
tagcloud:
  tag3d: false //  Whether to enable 3D tag cloud
  textColour: '#444' // 字体颜色
  outlineMethod: 'block' //  selected mode (outline|classic|block|colour|size|none)
  outlineColour: '#FFDAB9' // 选中模式的颜色
  interval: 30 // 动画帧之间的时间间隔，值越大，转动幅度越大
  freezeActive: true // 选中的标签是否继续滚动
  frontSelect: true // 不选标签云后部的标签
  reverse: true // 是否反向触发
  wheelZoom: false // 是否启用鼠标滚轮

## Friends Chain Settings{@Link Name: Link Address{@links:[,,,]}}
links:
  - Hexo官网: https://hexo.io/zh-cn/


# Theme customization personalized configuration

## website slogan {@branding: website slogan (do not set to show the local picture)}
branding: Never so simple and funny

## Set banner background image {@img: custom image address (support absolute and relative path), theme default {"static background": "banner.jpg"}, {"dynamic background": "banner2.jpg"}, {"Dynamic Starry Sky Background": "banner3.jpg"}}
## For example: http://snippet.shenliyang.com/img/banner|2|3.jpg, or './img/banner-img.jpg' (relative to local resource address)
banner:
  img: http://snippet.shenliyang.com/img/banner.jpg


## Set carousel{@img: image address, @url: click on the jump link (default: "javascript:")}
carousel:
  img: 'img/head-img.jpg'
  url: 'javascript:'

## Home list bottom panel {@homePanel: Whether to open}
homePanel: true

## Home Article List Thumbnail
### Loading Rules: Custom Article Thumbnails ('img' field added in Front-matter) > Pictures in the article > defaultImgs (randomly available) > No picture mode list

## Customize random images
defaultImgs:
  - http://www.example.jpg // Remote picture link example
  - /img/default-1.jpg // Example of local image link

  ### Article Summary{@Abstract Display Priority: Custom Summary > Automatic Intercept Summary }
  ### Custom summary range {@<!--more-->: Intercept the content before more as a summary}
  ### Automatic Intercept Summary{@excerptLength: How many words before the article are automatically intercepted, no default: 120 words}
excerptLength: 120

## Do you want to open the article directory?
toc: true

## Code Highlighting Configuration{@highlightTheme: Subject Name, (Configuration is temporarily unavailable, follow-up development...)}

highlightTheme: default //TODO

## Article expiration reminder function {@warning:{days: Critical days (default 300 days, set 0 off function), text: reminder text / *%d is the total number of days placeholders */}}
warning:
  days: 300
  text: 'This article was published before %d days, and the content in the article may be outdated.'

## Article declaration {@declaration: {enable: whether to open, title: statement title, tip: prompt content}}
declaration:
  enable: true
  title: 'Reprint statement'
  tip: |-
      For commercial reprint, please contact the author for authorization. For non-commercial reprint, please indicate the source. © <a href="" target="_blank">Snippet</a>

##Article reward {@reward: {alipay: Alipay reward, wepay: WeChat reward, tip: reward tips; links are empty, turn off the reward function}}
reward:
  alipay: ''
  wepay: '../img/reward-wepay.jpg'
  tip: Appreciation is not a rogue encouragement


## Subject review

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

### Will force (default option)
livere:
  enable: true
  livere_uid:

### Friends comments (service is unstable, often unable to load)
uyan:
  enable: false
  uyan_id:

### Disqus reviews (need to overturn the wall or build an agent)
disqus:
  enable: false
  shortname: snippet
  count: false

### Easy comment (requires ICP record)
changyan:
  enable: false
  appid:
  conf:

### Valine Review Reference Website: [valine Comments] (https://valine.js.org/)
valine:
  enable: true
  appId:
  appKey:
  placeholder: say something
  notify: false // E-mail notification
  verify: false // Verification code
  avatar: mm // avatar
  meta: nick,mail // Input box content, optional value nick, mail, link
  pageSize: 10

## Gitalk Review Reference Site: [A comment plugin based on Github Issue and Preact] (https://gitalk.github.io/)
gitalk:
   enable: false
   clientID: "" // Github 应用ID
   clientSecret: "" // Github 应用密钥
   repo: "hexo-theme-snippet" // 存储你评论 issue 的 Github 仓库名（建议直接用 GitHub Page 的仓库名），注：只写仓库名称，不写完整地址，比如：hexo-theme-snippet, 而不是 https://github.com/shenliyang/hexo-theme-snippet
   owner: shenliyang  // Github 用户名(github登录时用的名称)
   admin: shenliyang // 这个仓库的管理员，可以有多个，用数组表示，一般写自己用户名即可
   perPage: 10 //每次加载的数据大小，最多100
   id: "" // 如果为值"location.pathname"不建议填写(除非你有更好的方式)，由于id字段限制长度为50字符，默认为空时主题会进行判断处理。

## 网站访客统计 [不蒜子统计](http://busuanzi.ibruce.info/)
visit_counter:
   site: true // 总访问量和访问人数统计
   page: true // 文章阅读量统计

## 网站访问统计

### 网盟CNZZ统计 参考网站: [网盟CNZZ](http://www.umeng.com/)
cnzz_anaylytics:

### 百度统计 参考网站: [百度统计](https://tongji.baidu.com/)
baidu_anaylytics:

### 谷歌统计 参考网站：[谷歌统计](https://www.google-analytics.com/)
google_anaylytics:

### 腾讯分析 参考网站：[腾讯分析](http://ta.qq.com/)
tencent_analytics:

### 百度站点认证
baidu-site-verification:

### 百度自动推送(@baidu_push: 是否启用百度自动推送)  参考网站: [百度站长资源](https://ziyuan.baidu.com/college/courseinfo?id=267&page=2#h2_article_title18)
baidu_push:

## ICON配置 (不配则启用本地Font Icon)
fontAwesome: //cdn.bootcss.com/font-awesome/4.7.0/css/font-awesome.min.css

## 网站主题配置
since: 2017  //建站时间
robot: 'all'  //控制搜索引擎的抓取和索引编制行为，默认为all
version: 1.2.1  //当前主题版本号
```

### 主题使用技巧及功能扩展
1. 修改新增文章Front-matter模板,修改`scaffolds`目录下的`post.md`模板
> 模板文件内部不要保留注释部分,关键词后面请使用英文冒号
``` yml
  ---
  title: {{ title }} // 标题
  date: {{ date }}   // 时间
  categories: ['分类1','分类2'] // 分类
  tags: ['标签1','标签2']       // 标签
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
4. 当 `.travis.yml `配置文件修改完成后，将其提交到远程仓库的 hexo 分支下，此时如果之前的配置一切ok，我们应该能在 Travis CI 的博客项目主页页面中看到自动构建已经在开始执行了。上面会显示出构建过程中的日志信息及状态等。

## 3. 主题开发
Gulp 执行启用主题开发模式
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
主题宗旨：**致力主题简洁轻量，配置方便开箱即用**，该主题项目会持续维护和更新，不会跑路，请放心使用。

> Hexo框架追求的是快速、简洁，高效。喜欢绚丽，添加各种功能，折腾的朋友，建议移步至：[wordpress官网](https://cn.wordpress.org/)


## 你不知道的提Issues技巧
> 强烈推荐阅读 [《提问的智慧》](https://github.com/ryanhanwu/How-To-Ask-Questions-The-Smart-Way)、[《如何向开源社区提问题》](https://github.com/seajs/seajs/issues/545) 和 [《如何有效地报告 Bug》](http://www.chiark.greenend.org.uk/%7Esgtatham/bugs-cn.html)、[《如何向开源项目提交无法解答的问题》](https://zhuanlan.zhihu.com/p/25795393)，更好的问题更容易获得帮助。

<b>* 已阅读以上文章，并知晓，可以 </b> [提Issues](https://github.com/shenliyang/hexo-theme-snippet/issues/new) 了。


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

在主题 `source` 目录下新建文件夹，例如: `static`文件夹，然后添加静态资源，例如: xxx.pdf文件， 访问：*`http://yoursite.com/static/xxx.pdf`*

#### 5. 这个主题有分页功能吗？

主题已经集成分页功能，在Hexo配置中修改

| 参数       | 描述        | 默认值  |
| ------------- |:-------------:| :-----:|
| per_page     | 每页显示的文章量 (0 = 关闭分页功能) |  10 |
| pagination_dir     | 分页目录      |   page |

#### 6. 为什么右侧小工具标题都为英文呢？

可能是您忘记预设网站语言，而启用默认语言了，请先在Hexo配置中调整 language 设定

``` bash
language: zh-CN
```

#### 7. 关于Hexo标签和分类方法的分歧

> 只有文章支持分类和标签，您可以在 Front-matter 中设置。在其他系统中，分类和标签听起来很接近，但是在 Hexo 中两者有着明显的差别：分类具有顺序性和层次性，也就是说  `Foo, Bar` 不等于 `Bar, Foo`；而标签没有顺序和层次。

如果您有过使用WordPress的经验，就很容易误解Hexo的分类方式。WordPress支持对一篇文章设置多个分类，而且这些分类可以是同级的，也可以是父子分类。但是Hexo不支持指定多个同级分类。下面的指定方法：

``` bash
categories:
- Diary
- Life
```

会使分类Life成为Diary的子分类，而不是并列分类。因此，有必要为您的文章选择尽可能准确的分类。

Hexo官方文档: [分类方法的分歧](https://hexo.io/zh-cn/docs/front-matter#分类和标签)

> 没有找到你需要的问题解决方案，建议阅读[《你不知道的提Issues技巧》](https://github.com/shenliyang/hexo-theme-snippet#你不知道的提Issues技巧) 再提Issues。  


## 版本更新日志

  - 增加Gitalk评论系统
  - 增加博客自动化部署结果实时推送到手机钉钉上，第一时间了解部署情况

  自动化部署结果通知示例：

  ![自动化部署结果通知示例](https://s2.ax1x.com/2019/03/06/kvnejs.jpg)

## License

[MIT License](/LICENSE)
