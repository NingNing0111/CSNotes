# Markdown文本转换为网页并部署到GitHub

## 安装Python

> Python版本尽量选择3.8以上，此处以3.10.5为例。

### 下载Python

[官网下载地址](https://www.python.org/)

此处使用的python安装包：

![](imags/2.png)

### 安装Python

![](imags/1.png)

#### 安装配置

> 若想使用程序的默认配置，可以跳过这步

![](imags/3.png)

![](imags/4.png)

选择安装路径

> 尽量不安装在C盘下，电脑性能非常好的请随意。

![](imags/5.png)

![](imags/6.png)

> 安装完成后，点击“close”即可。

### 配置环境变量

> 找到python的安装路径--"D:\Python\PythonTools\python3.10.5",并复制该路径。

![](imags/7.png)

> 回退桌面，找到"此电脑"---右键"属性" --- 打开"高级系统设置"

![](imags/8.png)

> 选择"环境变量"

![](imags/9.png)

> 找到Path，点击编辑

![](imags/10.png)

> 点击新建，将我们刚刚复制的python的安装路径粘贴进去，然后点击上移(若系统本身没有两个python环境，可以不用上移，它自上而下的顺序是程序优先级从高到低的排序)，最后保存。

![](imags/11.png)

> Windows的环境变量配置基本和python的环境变量配置一致，类似的Java、Anaconda的环境变量配置也是如此，只是有一点点不同。

### 测试

> Windows + R 输入 “cmd” 调出Windows终端窗口，输入:

```python
python --version
```

若出现Python的版本信息，则说明环境配置成功。

![](imags/12.png)

也可以输入 "python"，若正常进入python的交互界面(输入1+1回车可以得到2)，也可以说明环境配置成功。

> 在python的交互界面中，输入 " exit() " 可以退出。

## 安装Git

### 下载Git

[Git下载地址](http://git-scm.com/downloads)

> 此处都以Windows平台为例

### 安装Git

![](imags/13.png)

![](imags/14.png)

> 除了安装目录可能需要有所修改外，请无脑点击“next”。

### 测试

> Windows + R 调出 Windows终端窗口，输入"git -v"查看git版本，若正常显示，则说明git环境正常，若没有，请按照Python的环境配置过程对Git进行相同的配置

![](imags/15.png)

## Pycharm安装

> 请安装Pycharm的付费版本，即专业版。网上教程很多，请自行解决。

## 正文

### 创建GitHub项目

> 如下图，可以在左边直接new一个项目或点击个人信息进入个人仓库进行创建。注意：所有的操作的前提是：你注册了GitHub账号并且登录了自己的账号。

![](imags/16.png)


![](imags/17.png)

> 进入如下界面：

![](imags/18.png)

> 可以记录下GitHub仓库地址

![](imags/19.png)

### 创建本地项目

> 项目名建议与GitHub上的项目名称一致，点击"create"进行创建。

![](imags/20.png)

> 删除多余的main文件（这个main文件可以在创建项目的时候取消创建）

![](imags/21.png)

### 安装依赖包

依赖包有：

- mkdocs

> 安装命令：pip install mkdocs

- mkdocs-material

> 安装pip install mkdocs-material

![](imags/22.png)

打开Pycharm终端，输入上述命令。

![](imags/23.png)

> 若出现如下警告，可以顺便复制引号中的命令对pip工具进行升级。

![](imags/24.png)

> 若安装过程比较缓慢，可能是下载源在国外造成的。可以在每个安装命令的后面添加如下参数指定下载源进行下载或者使用全局代理。

```python
pip install mkdocs -i https://pypi.tuna.tsinghua.edu.cn/simple

pip install mkdocs-material -i https://pypi.tuna.tsinghua.edu.cn/simple  
```

### 创建mkdocs项目

在终端中输入如下指令。格式如下：

- mkdocs new 项目名称

> 项目名称建议与GitHub项目保持一致。

```
mkdocs new mkdocs-study
```

控制台信息：

![](imags/25.png)

创建成功后，本地项目会多出mkdocs项目文件

![](imags/26.png)

### 添加markdown文件

- 所有的mkdocs文件均要放在docs目录下
- docs目录下必须存在index.md文件，这是整个网页的首页面
- mkdocs网页的所有配置都在mkdocs.yml文件中进行配置

为了便于理解，此处不添加额外的markdown，就在原index.md文件进行修改。

### 构建网页进行在线浏览



控制台中输入命令：

```shell
cd mkdocs项目名 # 进入mkdocs项目目录中，所在位置与配置文件同级 

mkdocs serve # 构建网页并在线浏览
```

![](imags/27.png)

> 点击访问地址，即可浏览网页

### 配置文件

[可参考这篇博客](https://www.cnblogs.com/Wcowin/p/17062095.html)

个人使用的配置：

```yml
site_name: 网站名称
site_author: 网站作者
site_url: 网站地址(https://GitHub用户名.github.io/项目名)

theme:
  name: material
  # custom_dir: overrrides
  font:
    text: Bitter
  icon:
    logo: material/library-shelves
    admonition:
      <type>: material/file-alert-outline

  favicon: imags/favicon.ico
  # img/11.ico
  palette:
    - primary: blue grey

    - media: "(prefers-color-scheme: light)"
      scheme: default # 日间模式
      primary: blue grey # 上方的
      accent: cyan # 链接等可交互元件的高亮色
      toggle:
        icon: material/weather-night # 图标
        name: 切换至夜间模式 # 鼠标悬浮提示
    - media: "(prefers-color-scheme: dark)"
      scheme: slate # 夜间模式
      primary: black
      accent: cyan
      toggle:
        icon: material/weather-sunny
        name: 切换至日间模式
  features:
    - navigation.instant #- header.autohide  #自动隐藏
    - announce.dismiss #呈现可标记为由用户读取的临时公告，可以包含一个用于取消当前公告的按钮
    - navigation.tracking #地址栏中的 URL 将自动更新为在目录中突出显示的活动锚点
#    - navigation.tabs #顶级部分将呈现在上面视口标题下方的菜单层中，但在移动设备上保持原样
    #- navigation.tabs.sticky  #启用粘性选项卡后，导航选项卡将锁定在标题下方，并在向下滚动时始终保持可见
    - navigation.sections #启用部分后，顶级部分在边栏中呈现为1220px以上视口的组，但在移动设备上保持原样
    - navigation.top # 返回顶部的按钮 在上滑时出现
    - search.suggest # 搜索输入一些字母时推荐补全整个单词
    - search.highlight # 搜索出的文章关键词加入高亮
    - navigation.expand # 打开Tab时左侧目录全部展开
    - navigation.indexes #启用节索引页后，可以将文档直接附加到节
    - search.share #搜索分享按钮
    - content.tabs.link
  language: zh # 一些提示性的文字会变成中文
  icon:
    repo: fontawesome/brands/github #右上角图标
repo_url: https://github.com/NingNing0111/MySQLNote # 右上角点击跳转的链接
repo_name: GitHub项目地址 # 右上角的名字

nav:
    - "文章栏一": "index.md"
    - "文章栏二":
        - "文章一": "文章一的markdown路径，以docs为根目录"
        - "文章二": "文章二的markdown路径，以docs为根目录"
    - "文章栏三": "文章三的markdown路径，以docs为根目录"

# 目录结构大致如上，它可以不断往下进行细分。


plugins:
  - search



markdown_extensions:
  - abbr
  - attr_list
  - admonition
  - def_list
  - footnotes
  - md_in_html
  # - meta # 支持Markdown文件上方自定义标题标签等
  - pymdownx.caret
  - pymdownx.critic
  - pymdownx.details
  - pymdownx.inlinehilite
  - pymdownx.keys
  - pymdownx.mark
  - pymdownx.snippets
  - pymdownx.smartsymbols
  - pymdownx.tilde
  - pymdownx.superfences:
      custom_fences:
        - name: mermaid
          class: mermaid
          format: !!python/name:pymdownx.superfences.fence_code_format # 代码块高亮插件
  - pymdownx.arithmatex:  # latex支持
      generic: true
  - toc:
      permalink: true # 固定标题位置为当前位置
  - pymdownx.highlight: # 代码块高亮
      anchor_linenums: true
      linenums: true # 显示行号
      # auto_title: true # 显示编程语言名称
  - pymdownx.emoji:
      emoji_index: !!python/name:materialx.emoji.twemoji
      emoji_generator: !!python/name:materialx.emoji.to_svg
  - pymdownx.tabbed:
      alternate_style: true
  - pymdownx.tasklist:
      custom_checkbox: true
  - markdown.extensions.toc:
      slugify: !!python/object/apply:pymdownx.slugs.slugify {kwds: {case: lower}}
      permalink: "\ue157"

extra_javascript:
  - js/extra.js 
  - js/mathjax.js
  - mathjax-config.js # 这三个js文件需要自行下载，放在docs目录中
  - https://polyfill.io/v3/polyfill.min.js?features=es6
  - https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js

extra_css:
  - css/extra.css
  - css/video.css # 这两个css文件需要自行下载，放在docs目录中
```

### 将网页部署到GitHub

#### GitHub账号与Pycharm进行绑定

这步分为GitHub上的操作和Pycharm上的操作

##### Github上的操作

点击个人头像 -- Settings

![](imags/28.png)

点击“开发者设置”

![](imags/29.png)

点击“令牌”

![](imags/30.png)

创建新的"令牌"

![](imags/31.png)

输入GitHub账号的密码后，进入如下界面

![](imags/32.png)

设置令牌信息

> 若自己的GitHub账号不担心被他人使用的话，可以将下面的框框都勾选上，避免令牌的权限不足。

![](imags/33.png)

生成

![](imags/34.png)

复制令牌

> 若该令牌需要在其它地方使用，可以记录下密钥值，密钥值只会显示一次。否则就需要重新生成。

![](imags/35.png)

##### Pycharm上的操作

返回Pycharm，依次点击file-settings-version control-Github

![](imags/36.png)

我们通过token进行GitHub账号绑定

![](imags/37.png)

绑定后

![](imags/38.png)

> 添加账户时，若出现如下报错信息，则需要使用代理进行账户关联。

![](imags/39.png)

具体操作如下：

> settings中搜索proxy

![](imags/40.png)

> pycharm默认不使用代理。我们对其进行相关配置即可。
> 注意：大多数情况下，代理配置就是科学上网，你的科学上网工具一般会有相关的本地端口号信息。
> 我的端口信息是10809，因此代理配置信息如图所示。

![](imags/41.png)

配置完成后，在正常进行绑定即可。

> 若还出现问题，可能是本身所连接的网络有限制，最简单的办法就是使用手机热点（手机请开流量）。

#### 构建本地git仓库

在Pycharm终端输入命令：

```
git init
```

或直接通过Pycharm进行构建，下述均以Pycharm上的操作为例

![](imags/42.png)

创建完成后，将文件提交到本地仓库

![](imags/43.png)

#### 共享到GitHub仓库

添加完成后，将本地仓库共享到我们的GitHub仓库

![](imags/44.png)

选择push

![](imags/45.png)

填写我们GitHub项目的仓库地址

![](imags/46.png)

![](imags/47.png)

点击 “push”

![](imags/48.png)

> 若提交不成功，出现如下错误：

![](imags/49.png)

> 就需要先将Pycharm的代理关闭

![](imags/50.png)

#### 网站自动化部署

在Pycharm终端输入命令

```shell
mkdocs gh-deploy
```

命令执行过程中，会弹出一个GitHub登录窗口，我们用任意方式(账号密码、token等)登录GitHub即可。终端日志如下：

![](imags/52.png)

网页部署到GitHub需要一段时间，具体时间依据需要部署的网页大小。

### 网站优化与维护

第一次提交后，后续的提交就不需要怎么麻烦了。一般流程如下：

- 将需要添加的markdown文件添加到docs目录下
- 对mkdocs.yml配置文件进行配置
- 共享到GitHub仓库
- 网站自动化部署

## 其它

个人使用mkdocs做的笔记项目: [CSNotes](https://github.com/NingNing0111/CSNotes)







