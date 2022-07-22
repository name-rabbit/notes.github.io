Docsify笔记搭建步骤

安装node，然后建议全局安装docsify-cli

```kotlin
npm i docsify-cli -g
```

使用init命令初始化

```kotlin
docsify init ./docs
```

生成docs文件夹

![image-20220722082944458](D:%5Cmy-project%5Cnotes.github.io%5Cdocs%5Cjavase%5Cimg%5Cimage-20220722082944458.png)

在本地运行然后在浏览器中打开 [http://localhost:3000](http://localhost:3000/)

![image-20220722083218007](D:%5Cmy-project%5Cnotes.github.io%5Cdocs%5Cjavase%5Cimg%5Cimage-20220722083218007.png)

在git上初始化(先克隆)，直接部署到github

```
git clone https://github.com/taoGod/extraordinarywen.git (仓库地址)
```

![image-20220722084423544](D:%5Cmy-project%5Cnotes.github.io%5Cdocs%5Cjavase%5Cimg%5Cimage-20220722084423544.png)

- 进入本地仓库，初始化docsify：`docsify init ./docs`

后面直接使用vscode提交，推送，拉取

![image-20220722084935898](D:%5Cmy-project%5Cnotes.github.io%5Cdocs%5Cjavase%5Cimg%5Cimage-20220722084935898.png)