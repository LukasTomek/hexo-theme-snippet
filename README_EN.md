Traslate of original file [README.md](https://github.com/shenliyang/hexo-theme-snippet/blob/master/README.md) by Google
# hexo-theme-snippet

Snippet is simple and not simple, maybe a long-awaited hexo theme.

If this topic is also your favorite dish, please move your finger [Star](https://github.com/shenliyang/hexo-theme-snippet/stargazers) support:pray:

[![Build Status](https://www.travis-ci.org/shenliyang/hexo-theme-snippet.svg?branch=master)](https://www.travis-ci.org/shenliyang/hexo-theme-snippet)
[![Read the Docs](https://img.shields.io/readthedocs/pip/stable.svg)](https://github.com/shenliyang/hexo-theme-snippet/blob/master/README.md)
[![HitCount](http://hits.dwyl.io/shenliyang/hexo-theme-snippet.svg)](http://hits.dwyl.io/shenliyang/hexo-theme-snippet)
[![mnt-image](https://img.shields.io/maintenance/yes/2019.svg)](../../commits/master)
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

> "Subject directory" => `themes\hexo-theme-snippet`, "Hexo root directory" => project home directory;
"Theme configuration" => `themes\hexo-theme-snippet\_config.yml`, "Hexo configuration" => `_config.yml` under the project home directory

### 1.  Environment to build

Need to `Node.js` environment,` Git` environment and `Hexo`, if you have not installed or do not understand` Hexo`, please refer to [official tutorial](https://hexo.io/en/docs/index.html) to understand and install. If you need to build a tool, please install it yourself or use the Gulp method of this topic.


### 2. Download the theme

There are two ways to get this topic - download the `.zip` file and pass the `git` way:

1. Download [Snippet Theme](https://github.com/LukasTomek/hexo-theme-snippet) File decompression placed in the `themes` directory, and the blog in the landscape for the same level directory

2. Git mode, in the Hexo root directory execution:
``` bash
git clone git://github.com/LukasTomek/hexo-theme-snippet.git themes/hexo-theme-snippet
```

### 3. Install theme plugin

Because **hexo-theme-snippet** uses the `ejs` template engine,` Less` CSS precompiled languag0e, and on the basis of official plugins.
To carry out the development of the function, the following is necessary plug-ins:

``` bash
npm i hexo-renderer-ejs hexo-renderer-less hexo-deployer-git -S
```

### 4. Deploy the theme

> If you have not changed the theme source file, you do not need code optimization to skip steps 1, 2, and 3.


1. Gulp package build, copy the `package.json` file in the theme directory to the Hexo root directory, and then install the project development dependencies. [Gulp Getting Started Guide](https://gulpjs.com/docs/en/getting-started/quick-start)
``` bash
npm i //installation project dependencies
```

2. Create a file called gulpfile.js in the Hexo root directory:
``` bash
require('./themes/hexo-theme-snippet/gulpfile');
```

3. Run gulp:
``` bash
gulp or gulp default // perform a package task
```

4. Empty the hexo static file and cache and regenerate
``` bash
hexo clean && hexo g //Clear the cache and generate a static file
```

5. Local preview, there is no problem to publish again
``` bash
hexo s -p 4000 or hexo s //start local service default
```

6. When gulp finishes executing and prompts `please execute: hexo d`, it can be published
``` bash
hexo d or gulp deploy // deployment release
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

## social settings {@name: social tool name, @ icon: social tool icon, @ href: set tool link} [reference icon](http://fontawesome.io/icons/)
social:
 - name: Github
   icon: git
   href: //github.com/shenliyang

## Article classification settings {@cate_config:{@show_count: Whether to display numbers, @ show_current: whether to highlight the current category}}
cate_config:
   show_count: true
   show_current: true

## article archive settings {@arch_config: / * parameter reference: https: //hexo.io/zh-cn/docs/helpers.html#list-archives*/}
## Recommended combination: [{type: 'monthly',format: 'YYYY/MM'}, {type: 'yearly',format: 'YYYY'}]
arch_config:
   type: 'monthly'
   format: 'YYYY/MM'
   show_count: true
   order: -1

## Tag Cloud Settings{/*Parameter Reference: http://www.goat1000.com/tagcanvas-options.php */}
tagcloud:
  tag3d: false //  Whether to enable 3D tag cloud
  textColour: '#444' // font color
  outlineMethod: 'block' //  selected mode (outline|classic|block|colour|size|none)
  outlineColour: '#FFDAB9' // The color of the selected mode
  interval: 30 // The time interval between animation frames, the larger the value, the greater the rotation
  freezeActive: true // Whether the selected label continues to scroll
  frontSelect: true // Do not select the label at the back of the tag cloud
  reverse: true // Whether to trigger in the reverse
  wheelZoom: false // Whether to enable the mouse wheel

## Friends Chain Settings{@Link Name: Link Address{@links:[,,,]}}
links:
  - Hexo official website: https://hexo.io


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

### Valine Review Reference Website: [valine Comments](https://valine.js.org/)
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

## Gitalk Review Reference Site: [A comment plugin based on Github Issue and Preact](https://gitalk.github.io/)
gitalk:
   enable: false
   clientID: "" // Github app ID
   clientSecret: "" // Github application key
   repo: shenliyang.github.io // Github warehouse address
   owner: shenliyang // Github username (Github repository owner)
   admin: shenliyang // The owner and collaborator of the GitHub repository (users with write access to this repository) can have one or more, if more than one can be used, for example: admin: admin1, admin2 configuration
   perPage: 10 //The size of the data loaded each time, up to 100
   distractionFreeMode: true // Whether to enable interference-free mode, similar to the full-screen mask effect of the Facebook comment box

   // The following parameter topics will be processed by default, no configuration required
   language // language type, default is the option in the site configuration
   id // The unique identifier of the page, which has been used to generate a unique id for pathname conversion using md5

## Website Visitor Statistics [No garlic statistics](http://busuanzi.ibruce.info/)
visit_counter:
    site: true // total visits and visitor statistics
    page: true // article reading statistics

## Website Access Statistics

### Net Meng CNZZ statistics Reference Website: [Network alliance CNZZ](http://www.umeng.com/)
Cnzz_anaylytics:

### Baidu Statistics Reference Website: [Baidu Statistics](https://tongji.baidu.com/)
baidu_anaylytics:

### Google Statistics Reference Website: [Google Statistics](https://www.google-analytics.com/)
google_anaylytics:

### Tencent Analysis Reference Website: [Tencent Analysis](http://ta.qq.com/)
tencent_analytics:

### Baidu Site Certification
baidu-site-verification:

### Baidu Auto Push (@baidu_push: Whether to enable Baidu Auto Push) Reference Website: [Baidu Webmaster Resources](https://ziyuan.baidu.com/college/courseinfo?id=267&page=2#h2_article_title18)
baidu_push:

## ICON Configuration (If you don't match, enable Local Font Icon)
fontAwesome: //cdn.bootcss.com/font-awesome/4.7.0/css/font-awesome.min.css

## Website theme configuration
since: 2017 //Building time
robot: 'all' //Controls the crawling and indexing behavior of the search engine. The default is all
version: 1.2.1 //current theme version number
```

### Theme usage tips and function extensions
1. Modify the new article Front-matter template and modify the `post.md` template in the `scaffolds` directory.
> Do not keep the comment part inside the template file. Please use the English colon after the keyword.
``` yml
  ---
  title: {{ title }} // title
  date: {{ date }}   // time
  categories: ['Class 1', 'Class 2'] // Category
  tags: ['tag 1', 'tag 2']           // tag
  comments: false    // Whether to open comments
  img:               // custom thumbnail
   ---
```

2. Enable in-site local search

If you want to use local site search, you must install the plugin hexo-generator-json-content to create a local search json file.
```bash
npm i hexo-generator-json-content@2.2.0 -S
```
Then modify the theme configuration _config.yml file under the `jsonContent` related parameters.

# **Upgrade article**

## 1. Introduction to Travis CI
CI is a continuous integration system. For the individual, just let your code be submitted to the remote (here GitHub), compile automatically, automate testing, auto-deploy, and more.

You don't need to worry about changing your computer. If you can push the article remotely, you can leave it to Travis CI for processing.

## 2. Travis CI use

> The default premise is that you have been authorized to log in to the Travis website via Github and associated the repository and related configuration on GitHub.
1. Copy the `gulpfile.js` `travis.yml` `travis.sh` under the theme to the project root directory.

2. Configure the travis.yml file
``` yml
language: node_js #Use the Node locale
node_js: stable #Install stable version of Node

sudo: false

#cache Enable caching to speed up builds
cache:
  directories:
    - "node_modules"

notifications: #Enable notifications
  email:
    recipients:
      - snippet@91h5.cc # Receive messages for build messages No need to be set to false
    on_success: never # When the deployment is successful, you can set the always never change
    on_failure: always # When the deployment fails, the same as above

# S: Build Lifecycle

before_install:
  - sudo apt-get install libnotify-bin #Support linux desktop reminder library

install:
  - npm install #install dependency

before_script:
  - export TZ='Asia/Shanghai' #Set time zone
  - npm install -g gulp #Global Install Gulp
  - chmod +x _travis.sh #authorize script execution permissions

script:
  - hexo clean && hexo g #clear the cache and generate static files
  - gulp #execute gulp task

after_success: # When the execution is successful (use of extended functions later)

after_script:
  - ./_travis.sh #Execute the deployment script
# E: Build LifeCycle

branches:
  only:
    - dev # needs to listen to the deployed branch
env:
  global:
   - GH_REF: github.com/shenliyang/shenliyang.github.io.git #change to your own git address
```

3. Submit the code to Github for automated deployment
4. When the `.travis.yml` configuration file is modified, submit it to the hexo branch of the remote repository. If the previous configuration is all ok, we should be able to see the automatic in the Travis CI blog project home page. The build is already in progress. The above will show the log information and status during the build process.

## 3. Theme development
Gulp performs the enabled theme development mode
``` bash
gulp dev
```
Will listen for changes in style less or JS files. Then execute the [Subject Release] above.

### Run preview
``` bash
hexo clean && hexo g && hexo s -p 4000
```

Listen to port 4000 and use the browser to open the address `http://localhost:4000` for preview.

# **Other**

## Thank you
Thanks to the design and creativity of many themes and blogs when designing this theme!

## Encourage
**If you feel that this topic is not bad, your support and encouragement is the biggest motivation for subsequent updates, == Welcome [Star](https://github.com/shenliyang/hexo-theme-snippet/stargazers) == **

![Stargazers over time](https://starchart.cc/shenliyang/hexo-theme-snippet.svg)

## Purpose
Theme: ** Dedicated to the theme of simple and lightweight, easy to use out of the box **, the theme of the project will continue to maintain and update, will not run, please feel free to use.

## Contribution
Accept various forms of contributions, including but not limited to submitting questions or requirements, fixing the code.
Welcome to mention either Issue or Pull Request.

> The Hexo framework is fast, simple and efficient. Like beautiful, add a variety of features, toss friends, it is recommended to move to: [wordpress official website](https://wordpress.org/)


## You don’t know the tips of Issues
> It is highly recommended to read ["Wise of Questioning"](https://github.com/ryanhanwu/How-To-Ask-Questions-The-Smart-Way), [How to Ask the Open Source Community](https://github.com/seajs/seajs/issues/545) and [How to Report Bugs Effectively](https://www.chiark.greenend.org.uk/~sgtatham/bugs.html), ["How to submit unanswerable questions to open source projects"](https://zhuanlan.zhihu.com/p/25795393), better questions are easier to get help.

<b>* Read the above article and know that you can </b> [Issues](https://github.com/shenliyang/hexo-theme-snippet/issues/new).


## common problem

#### 1. The search function cannot be used. The content.json file could not be found?

Need to install the hexo-generator-json-content plugin:

``` bash
npm i hexo-generator-json-content@2.2.0 -S
```

#### 2. Google search is not responding?

If you are not responding with Google search, determine if you have been online

#### 3. How to set the home page thumbnail to automatically retrieve the image inside the article?

Home Article Thumbnail Loading Rules: Custom Article Thumbnails > Automatically Retrieve Images in Articles > defaultImgs (Random Access) > No Graph Mode List

In `Front-matter`:
Specify img variable -> for fixed thumbnail
Do not specify the img variable -> automatically retrieve the image in the article


#### 4. Where can I access local static files in the url?

Create a new folder in the theme `source` directory, for example: `static` folder, then add static resources, for example: xxx.pdf file, access: *`http://yoursite.com/static/xxx.pdf`*

#### 5. Does this theme have paging function?

The theme has integrated pagination and is modified in the Hexo configuration

| Parameter | Description | Default |
| ------------- |:-------------:| :-----:|
| per_page | The number of articles displayed per page (0 = Close paging feature) | 10 |
| pagination_dir | Pagination | page |

#### 6. Why are the right gadget titles in English?

Maybe you forgot to preset the website language and enable the default language. Please adjust the language setting in the Hexo configuration first.
``` bash
language: zh-CN
```

#### 7. Disagreement about Hexo labeling and classification methods

> Only articles support categories and labels, which you can set in Front-matter. In other systems, classifications and labels sound similar, but there are significant differences between the two in Hexo: classifications are sequential and hierarchical, meaning that `Foo, Bar` is not equal to `Bar, Foo`; There is no order and hierarchy.

If you have experience with WordPress, it's easy to misunderstand Hexo's classification. WordPress supports setting up multiple categories for an article, and these categories can be siblings or parent-child categories. However, Hexo does not support specifying multiple sibling classifications. The following method is specified:

``` bash
categories:
- Diary
- Life
```

It will make the classified life a sub-category of Diary, not a side-by-side classification. Therefore, it is necessary to choose the most accurate classification possible for your article.

Hexo official document: [differences in classification methods](https://hexo.io/docs/front-matter.html# classification and labeling)

> Didn't find the solution to the problem you need, it is recommended to read ["Issues Tips You Don't Know"](https://github.com/shenliyang/hexo-theme-snippet#I don't know the Issues tips) Issues.


## Version update log

  - Increase the Gitalk comment system
  - Increase the results of blog automation deployment to the mobile phone in real time, and understand the deployment situation in the first time.

  Example of automated deployment result notification:

  [Automatic Deployment Result Notification Example](https://s2.ax1x.com/2019/03/06/kvnejs.jpg)

## License

[MIT License](/LICENSE)
