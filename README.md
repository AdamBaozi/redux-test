# redux-test
一、项目来源于：https://segmentfault.com/a/1190000004355491?_ea=661485
在将项目在本地实现的过程中，出现了一些问题，于是在原项目的基础上相应地做了改动。
1.bebel-loader版本不匹配的问题
详细是TypeError: Cannot read property 'babel' of undefined
解决办法参考：TypeError: Cannot read property 'babel' of undefined
2.
babel-loader jsx SyntaxError: Unexpected token [duplicate]
解决办法参考：https://stackoverflow.com/questions/33460420/babel-loader-jsx-syntaxerror-unexpected-token

这样之后，通过键入命令： webpack  => 成功将项目打包至bundle.js

二、将项目部署到服务器
参考：https://segmentfault.com/a/1190000006670084
主要步骤是：
1.修改package.json文件，添加如下：
"scripts": {
    "dev": "webpack-dev-server --devtool eval-source-map --progress --colors --hot --inline --content-base ./",
    "build": "webpack --progress --colors"
  },
  
--content-base path: 需要特别注意，path主要是指index.html相对于根目录的位置，在本项目中，index.html处于一个路径下，所以path描述为./即可
 2.输入npm run dev
 3.在浏览器中打开localhost:8080/index.html
 
 还有将项目提交到远程分支
1.首先在本地的项目文件下，把目录变成git可以管理的库
git init
2.然后在远程的github网站上新建仓库——这个仓库主要是用来同步本地的目录库
直接在网站上new repository -》 文件名和本地的文件名一致
3.在本地的终端建立和远程仓库的联系
git remote add origin git@github.com:AdamBaozi/redux-test.git
添加改变
git add .
提交改变
git commit -m 'xxxxxx'
把本地库推到远程库
git push -u origin master
由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，
还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。
错误：ssh的协议有问题，ssh: connect to host github.com port 22: Connection timed out
参考此网站，顺利解决：https://blog.csdn.net/okokyu/article/details/99681636
