---
title: hexo使用Github自动部署
cover: 'https://flie.pigax.cn/2022/09/14/6321c33eee938.jpg'
description: hexo使用Github自动部署
keywords: 花语阁-hexo使用Github自动部署
categories: 爱学习
tags:
  - Hexo
  - Github
abbrlink: 3f376478
date: 2022-09-14 19:06:34
updated: 2022-09-14 19:06:34
---
# 前言

本文章参考

{% link 使用Github Action实现全自动部署, https://akilar.top/posts/f752c86d/, https://assets.akilar.top/image/siteicon/favicon.png %}

在本文的基础上做了些修改，只限Github，其他的可以继续常考

# 开始

> 我们需要的变量名，可以参考糖果屋的文章

| 变量名 | 常亮含义 |
| --- | --- |
| GITHUBUSERNAME | Github用户名 |
| GITHUBEMAIL | Github邮箱 |
| GITHUBTOKEN | Github申请秘钥 |
| SiteBlogRepo | 存放编译好的博客页面的公有仓库名|

# 获取Token

为了确保交由`Github Action`来持续部署时，`Github Action`具备足够的权限来进行`hexo deploy`操作,需要先获取`Token`，博主分别在`Github`处部署了静态页面，所以也就需要获取这一处的`Token`。

访问[Github->头像（右上角）->Settings->Developer Settings->Personal access tokens->](https://github.com/settings/tokens)<kbd>generate new token</kbd>,创建的Token名称随意，但必须勾选repo项和workflows项。

![qq_pic_merged_1663154822829.jpg](https://flie.pigax.cn/2022/09/14/6321bad7d8820.jpg)
![Screenshot_2022-09-14-19-25-15-543-edit_com.android.browser.jpg](https://flie.pigax.cn/2022/09/14/6321bb0455774.jpg)
![qq_pic_merged_1663154795855.jpg](https://flie.pigax.cn/2022/09/14/6321bb1b82d47.jpg)

> `token`只会显示这一次，之后将无法查看，所以务必保证你已经记录下了`Token`。之后如果忘记了就只能重新生成重新配置了。

# 配置Github Action

1. 在`[Blogroot]`新建`.github`文件夹,注意开头是有个`.`的。然后在`.github`内新建`workflows`文件夹，再在`workflows`文件夹内新建`autodeploy.yml`,在`[Blogroot]/.github/workflows/autodeploy.yml`里面输入

```YML

# 当有改动推送到master分支时，启动Action
name: 自动部署

on:
  push:
    branches:
      - master #2020年10月后github新建仓库默认分支改为main，注意更改

  release:
    types:
      - published

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - name: 检查分支
      uses: actions/checkout@v2
      with:
        ref: master #2020年10月后github新建仓库默认分支改为main，注意更改

    - name: 安装 Node
      uses: actions/setup-node@v1
      with:
        node-version: "12.x"

    - name: 安装 Hexo
      run: |
        export TZ='Asia/Shanghai'
        npm install hexo-cli -g

    - name: 缓存 Hexo
      uses: actions/cache@v1
      id: cache
      with:
        path: node_modules
        key: ${{runner.OS}}-${{hashFiles('**/package-lock.json')}}

    - name: 安装依赖
      if: steps.cache.outputs.cache-hit != 'true'
      run: |
        npm install --save

    - name: 生成静态文件
      run: |
        hexo clean
        hexo generate
        gulp

    - name: 部署 #此处master:master 指从本地的master分支提交到远程仓库的master分支，若远程仓库没有对应分支则新建一个。如有其他需要，可以根据自己的需求更改。
      run: |
        cd ./public
        git init
        git config --global user.name '${{ secrets.GITHUBUSERNAME }}'
        git config --global user.email '${{ secrets.GITHUBEMAIL }}'
        git add .
        git commit -m "${{ github.event.head_commit.message }} $(date +"%Z %Y-%m-%d %A %H:%M:%S") Updated By Github Actions"
        git push --force --quiet "https://${{ secrets.GITHUBUSERNAME }}:${{ secrets.GITHUBTOKEN }}@github.com/${{ secrets.GITHUBUSERNAME }}/${{ secrets.SITEUSERNAME }}.git" master:gh-pages        
```

2. 之后需要自己到仓库的`Settings->Secrets->actions` 下添加环境变量，变量名参考脚本中出现的，依次添加。

> 我偷的图

![qq_pic_merged_1663157375130.jpg](https://flie.pigax.cn/2022/09/14/6321c4b2957e9.jpg)

# 重新设置远程仓库和分支

1. 删除或者先把`[Blogroot]/themes/butterfly/.git`移动到非博客文件夹目录下,原因是主题文件夹下的`.git`文件夹的存在会导致其被识别成子项目，从而无法被上传到源码仓库。

2. 在博客根目录`[Blogroot]`路径下运行指令

```BASH
git init #初始化
git remote add origin git@github.com:[GithubUsername]/[SourceRepo].git #[SourceRepo]为存放源码的github私有仓库
git checkout -b master # 切换到master分支，
#2020年10月后github新建仓库默认分支改为main，注意更改
# 如果不是，后面的所有设置的分支记得保持一致
```

3. 添加屏蔽项
因为能够使用指令进行安装的内容不包括在需要提交的源码内，所有我们需要将这些内容添加到屏蔽项，表示不上传到`github`上。这样可以显著减少需要提交的文件量和加快提交速度。
打开`[Blogroot]/.gitignore`,输入以下内容：

```TXT
.DS_Store
Thumbs.db
db.json
*.log
node_modules/
public/
.deploy*/
.deploy_git*/
.idea
themes/butterfly/.git
```

如果不是`butterfly`主题，记得替换最后一行内容为你自己当前使用的主题。

4. 之后再运行`git`提交指令，将博客源码提交到`github`上。

```BASH
git add .
git commit -m "github action update"
git push origin master
#2020年10月后github新建仓库默认分支改为main，注意更改
```

5. 此时你的主题文件夹若已经被正常上传，并且你也添加了主题文件夹下的`.git`文件夹的屏蔽项。那你可以考虑把第二步移走或删除的`.git`放回来，用作以后升级。（不禁怀疑真的有人会去用这个方式来升级吗）

# 查看部署情况

此时，打开`GIthub`存放源码的私有仓库，找到`action`。

![Screenshot_2022-09-14-19-43-18-727-edit_com.android.browser.jpg](https://flie.pigax.cn/2022/09/14/6321be666d43b.jpg)

根据刚刚的`Commit`记录找到相应的任务

![Screenshot_2022-09-14-19-44-06-807-edit_com.android.browser.jpg](https://flie.pigax.cn/2022/09/14/6321be909dd97.jpg)

点击`Deploy`查看部署情况

![Screenshot_2022-09-14-19-44-58-640-edit_com.android.browser.jpg](https://flie.pigax.cn/2022/09/14/6321bec93cc34.jpg)

若全部打钩，恭喜你，你现在可以享受自动部署的快感了。

# 一键部署到私有仓库

我们需要安装一个插件[hexo-git-backup](https://www.npmjs.com/package/hexo-git-backup)

```BASH
npm install hexo-git-backup --save
```

之后我们在`[Blogroot]`根目录下的`_config.yml`中添加以下代码

```YML
backup:
    type: git
    repository:
       github: git@github.com:xxx/xxx.git,branchName
       gitcafe: git@github.com:xxx/xxx.git,branchName
```

> 如果是主分支不需要在后面添加分支

> 如果构建过`.git`文件夹需要删除`[Blog]`根目录下的`.git`文件夹

在`[Blogroot]`根目录下输入以下指令

```BASH
hexo backup

or

hexo b
```

之后我们就可以愉快的使用了